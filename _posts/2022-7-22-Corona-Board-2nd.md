---
layout: post
title: Corona-Board-2nd
categories : Corona-Board-Backend
---

require( ) : 다른 파일에 존재하는 코드를 불러옵니다.
module.exports  : 현재 파일에 있는 내용 중 다른 파일에 보여주고 싶은 내용만 노출할 수 있도록 해줍니다

public define(modelName: string, attributes: object, options: object): Model 

• modelName : 객체 모델 이름 
• attributes : 객체 모델의 속성 목록(속성 하나가 데이터베이스 테이블의 컬럼 하나에 대응) 
• options : (선택 사항) 인덱스 등 추가 옵션

//req 객체 는 수신된 HTTP 요청에 대한 모든 정보를 담고 있으며  
//res 객체는 클라이언트에 돌려줄 HTTP 응답을 만들 때 사용합니다.
~~~javascript

   app.get('/', (req, res) => {
        
      res.json({ message: 'Hello CoronaBoard!' });
    });
~~~
# 객체 모델과 데이터베이스를 동기화하는 방법
- sequelize.sync( ); : 동기화하려는 테이블이 존재하면 아무런 작업을 하지 않고 테이블이 없 을 때만 새롭게 생성합니다. 

- sequelize.sync({ force: true }); : 동기화하려는 테이블이 존재하면 삭제해버리고 테이블을 새 로 생성합니다. 예를 들어 개발 서버에서 기존에 저장된 데이터가 삭제되거나 테이블 스키마 가 완전히 바뀌어도 문제 없이 사용할 수 있습니다. 

- sequelize.sync({ alter: true }); : 동기화하려는 테이블의 필드와 자료형을 확인해 객체 모델 정 의와 다르다면 같아지도록 적절히 변경합니다

# HTTP 요청이 라우터를 통해 컨트롤러로 전달되는 과정

![_config.yml]({{ site.baseurl }}/images/process.jpg) 

각자 별도의 컨트 롤러로 연결합니다. RESTful API를 디자인할 때 일반적으로 많이 사용되는 방식입니다. 

특정 리 소스resource에 대해 하나의 경로를 지정하고 해당 리소스에 대한 처리를 담당하는 컨트롤러를 만들 어서 관련 코드들을 해당 컨트롤러 안에 모아서 작성

리소스에 따라 컨트롤러를 분리해두면 하나의 컨트롤러가 비대해지는 것 을 막을 수 있다.

관련도가 높은 코드들을 한 파일 안에 모아둘 수 있기 때문에 코드를 관 리하기도 쉽고 가독성도 좋아진다.

# 시퀄라이즈 ORM에서 제공하는 대표적인 기능  
- ```create( )```  SQL의 INSERT 구문에 해당 
- ```findAll( )``` SQL의 SELECT 구문에해당 
- ```findOne( )``` SQL의 SELECT 구문에 해당하는 작업을 수행하되 첫 번째 찾은 레코드만 반환 
- ```count( )``` SQL의 SELECT 구문으로 검색된 레코드의 개수 반환 
- ```update( )``` SQL의 UPDATE 구문에 해당 
- ```destroy( )``` SQL의 DELETE 구문에 해당 
- ```upsert( )``` MySQL의 INSERT ... ON DUPLICATE KEY UPDATE 구문 8 에 해당 (INSERT를 시도해보고 기 존에 존재하는 데이터가 있으면 업데이트)