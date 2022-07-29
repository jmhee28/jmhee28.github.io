---
layout: post
title: Corona-Board-3rd
categories : Corona-Board-Nodejs
---
# 웹페이지 크롤링을 위한 배경 지식
## 1.  웹페이지와 DOM 
### 웹페이지  

-  HTML 형식으로 제공되는 일종의 문서  

- 웹브라우저로 웹페 이지에 접근한다는 것은, 간단히 말해 서버로부터 해당 주소에서 제공하는 HTML 문서를 HTTP 통신으로 전달받는 것을 의미  

- 전달받은 HTML 문서는 단순 텍스트 형태이기 때문에 프 로그램에서 사용하기 좋은 데이터 구조로 표현해야 하는데, 이 구조를 DOM이라고 부릅니다.  

### DOM(Document Object Model)  

- 최상위 노드node와 여러 단계의 자식 노드들로 구성된 트리tree 구조
- 원하는 노드를 쉽게 찾아서 수정/삭제하거나 원하는 위치에 새로운 노드를 추가할 수 있습니다.   

![_config.yml]({{ site.baseurl }}/images/DOM_tree.jpg)   



웹브라우저는 HTML을 DOM으로 변환한 후, CSS로 설정한 스타일을 DOM의 각 노드에 적용 하여 사용자에게 보여줍니다. 이것이 우리가 보는 웹페이지 화면입니다. 