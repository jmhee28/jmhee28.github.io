---
layout: post
title: Corona-Board-CSS-Selecter
categories : Corona-Board-Nodejs
---
# CSS 셀렉터 문법

## 기본 셀렉터

기본적인 CSS 셀렉터를 이용하면 명시한 태그, id, 클래스, 속성을 만족하는 요소들을 찾는 기능을 제공합니다.

## TAG Selector

태그 셀렉터type selector는 태그 이름을 그대로 적어주면 해당 태그에 해당하는 요소를 검색합니다.
 
 EX)
 - h1 태그에 해당하는 요소 검색  
 ``` document.querySelectorAll('h1');```  


## ID Selector

 ID selector는 찾고자 하는 id 속성값 앞에 # 기호를 붙여주어 검색합니다(HTML 문서 내 에서 id값은 항상 고유하기 때문에 하나만 존재합니다).  

 EX)  
 -  id="country-title"인 요소 검색  
 ``` document.querySelectorAll('#country-title');```

## Class Selector

클래스 셀렉터class selector는 찾고자 하는 클래스 속성값의 앞에 . 기호를 붙여 검색합니다.

 EX)  
 - class="slide" 인 요소 검색  
 ```document.querySelectorAll('.slide')```

## Attribute Selector
 Attribute selector는 찾고자 하는 속성 이름을 [ ]로 묶어 검색합니다. 해당 속성의 값도 지 정하여 검색할 수 있습니다. 
 EX)  
 - "type"이라는 속성을 가진 요소 검색  
 ```document.querySelectorAll('[type]')```

# 셀렉터 조합하기

## OR 조건으로 찾기

 여러 기본 셀렉터를 ,로 연결하면 각 조건을 만족하는 요소 모두를 검색합니다. 
 -  h1 태그 또는 'slide' 클래스 속성값을 가진 요소 검색 
 ```document.querySelectorAll('h1, .slide');```

## AND 조건으로 찾기
 다른 종류의 기본 셀렉터를 띄어쓰기 없이 이어붙이면 해당 조건들을 동시에 만족하는 요소를 검색합니다.  
 이어붙일 때 태그 셀렉터가 제일 앞에 나와야 하고, 클래스 셀렉터나 속성 셀렉터는 순서에 관계없이 태그 셀렉터 뒤쪽에 있도록 하면 됩니다.
 - div 태그에 'slide' 클래스 속성값이 지정된 요소 검색 
 ```document.querySelectorAll('div.slide');```

# 계층 구조 조합하기
계층 구조를 이용하여 원하는 요소를 CSS 셀렉터 문법으로 찾는 방법을 알아봅시다.

## 계층 순서로 요소 찾기
 여러 셀렉터를 공백으로 연결하면, 연결된 순서대로 부모/자식 계층 관계를 가지는 요소를 검색 합니다. 이때 꼭 부모/자식 관계뿐 아니라 세대를 건너뛰는 요소도 검색됩니다.

 - div 태그를 상위 요소로 가진 모든 p 태그 요소 검색   
 ``` document.querySelectorAll('div p');```
 
## 직접적인 자식 요소 찾기
 여러 기본 셀렉터를 > 기호를 사용하여 연결하면 직접적인 부모/자식 계층 관계를 가지는 요소를 검색합니다. 직접적인 계층 관계를 명시하면 계층 순서로 요소를 찾을 때보다 찾고자 하는 요소를 더 정확히 찾을 수 있습니다.   

 - container' 클래스 속성값을 가진 div 요소의 직접적인 자식 중 p 태그 요소 검색  
 ```document.querySelectorAll('div.container > p'); ```

## 동일한 부모를 가진 요소 찾기 
 여러 기본 셀렉터를 ~ 기호를 사용하여 연결하면 찾은 요소를 기준으로 동일한 부모를 갖는 조건 을 만족하는 모든 요소를 검색합니다.
 -  id="input-test-title"인 요소와 동일한 부모를 가진 input 태그 요소 검색
 ``` document.querySelectorAll('#input-test-title ~ input');```

## 동일한 부모를 가지면서 인접한 요소 찾기
 여러 기본 셀렉터를 + 기호를 사용하여 연결하면 찾은 요소를 기준으로 동일한 부모를 가지면서 해당 요소 바로 다음에 나오는 요소 하나를 검색합니다.
 - id="input-test-title"인 요소와 동일한 부모를 가진 input 태그 요소 검색 
 ``` document.querySelectorAll('#input-test-title + input');```