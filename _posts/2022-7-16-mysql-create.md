---
layout: post
title: Mysql Creating database
categories : Mysql
---
 ``` mysql> CREATE USER 'coronaboard_admin'@'%' IDENTIFIED BY '비밀번호'; ``` 
  
 여기서 ‘@’ 문자를 기준으로 앞쪽은 계정 이름을, 뒤쪽은 해당 계정으로부터의 접근을 허용할 호 스트host를 의미합니다. 호스트를 ‘%’로 지정하면 어떠한 호스트에서의 접근도 허용한다는 뜻입니 다. % 대신 121.157.214.98과 같이 IP 주소를 명시하면 지정한 IP의 호스트에서만 접근할 수 있습니다.
