---
layout: post
title: How to Implement Search Keyword In Spring
categories : Spring
---

## 1. First, Make PostSearchDto
~~~ java
public class PostSearchDto {

    private Long id;
    private String title;
    private String contents;

    private String author;

    public PostSearchDto(PostEntity entity) {
        this.id = entity.getId();
        this.title = entity.getTitle();
        this.contents = entity.getContents();
        this.author = entity.getAuthor();
    }
}
~~~

## 2. Repository
- I wrote Query in postRepository  

~~~ java
public interface PostRepository extends CrudRepository<PostEntity, Long> {
    @Query("SELECT p FROM PostEntity p WHERE p.title = :title ORDER BY p.id ASC")
    List<PostEntity> findByTitle(@Param("title") String title);

    @Query("SELECT p FROM PostEntity p WHERE p.contents LIKE %:contents% ORDER BY p.id ASC") 
    List<PostEntity> findByContentsContaining(@Param("contents") String contents);

    @Query("SELECT p FROM PostEntity p WHERE p.author = :author ORDER BY p.id ASC")
    List<PostEntity> findByAuthor(@Param("author") String author);
}
~~~


- **LIKE** 
     - to know wheter it contains the contents
     - Parameter should be start and end with **%**

## Service

~~~ java
@Transactional
    @Override
    public List<PostSearchDto> getSearchList(String type, String keyword){
        if(type.equals("title")==true)
        {
            return postRepository.findByTitle(keyword).stream().map(PostSearchDto::new).collect(Collectors.toList());
        }
        else if(type.equals("contents")==true)
        {
            return postRepository.findByContentsContaining(keyword).stream().map(PostSearchDto::new).collect(Collectors.toList());
        }
        else // author
        {
          return  postRepository.findByAuthor(keyword).stream().map(PostSearchDto::new).collect(Collectors.toList());
        }
    }
~~~

## Controller
~~~ java
@GetMapping("/showSearchList/{type}/{keyword}")
    public String getSearchList(@PathVariable String type,@PathVariable String keyword,@LoginUser SessionUser user,Model model) throws Exception{
       
        if (user != null) {
            model.addAttribute("userName", user.getName());
        }
        List<PostSearchDto> plist = postService.getSearchList(type, keyword);
        model.addAttribute("SearchList", plist);
        return "showSearchList";
    }
~~~
