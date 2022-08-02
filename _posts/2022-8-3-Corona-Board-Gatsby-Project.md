---
layout: post
title: Corona-Board-Gatsby-Project
categories : Corona-Board-Frontend
---
# 개츠비 프로젝트 설치

 ```$ npm install -g gatsby-cli@3.10.0```  

 ```$ gatsby new coronaboard-web \ https://github.com/atsbyjs/gatsby-starter-hello-world ```

 ![_config.yml]({{ site.baseurl }}/images/gats_pro.jpg)
 
 ```$ cd coronaboard-web ```

 ```$ gatsby develop ```

HMR Hot Module Reload: 코드 변경이 발견될 때마다 다시 빌드 한 후 기존에 보여주던 페이지를 자동 으로 새로고침해주는 기능 


## 개츠비 프로젝트 구조

 ![_config.yml]({{ site.baseurl }}/images/gats_struc.jpg)

 **[.cache]**
 - 개츠비 빌드 과정에서 생성되는 산출물을 캐싱해두는 디렉터리

 - 이전 빌드 의 산출물을 캐싱하여 다음번 빌드를 더 빠르게 해주는 역할

 - 직접 수정할 일은 없 으나, 혹시 캐시로 인해 변경된 데이터가 제대로 나오지 않는 등의 문제가 발생하면 gatsby clean 명령으로 삭제

**[public]**
 - 빌드가 완료된 정적 웹사이트의 결과물이 저장되는 디렉터리

 - 나중에 gatsby build 명령으로 프로덕션용 정적 웹사이트 빌드한 후, 이 디렉터리 안의 모든 파일 을 파일 서버나 AWS S3 등에 업로드하여 사용

 -  gatsby clean 명 령으로 깨끗이 청소할 수 있음.

**[src/pages]**
- 정적 웹사이트 빌드에 사용할 소스 파일들이 담겨 있는 디렉터리

- 이 위 치에 존재하는 파일 하나가 정적 웹사이트의 웹페이지 하나와 1:1 매핑

**[static]**
 - 웹사이트에 사용될 정적 자원(이미지, 폰트 등)을 넣어둡니다. 

 - 이 디렉터리에 존재하는 파일들은 빌드 시 [public] 디렉터리로 복사됩니다.

**gatsby-config.js**
 - 개츠비의 설정 파일입니다. 
 - 개츠비 빌드 시 플러그인을 추가하고 설정할 수 있으며, 사이트 제목, 설명, URL 등 사이트의 메타 정보 역시 여기에 정의
 
**.prettierrc**
- 자바스크립트 코드 포매팅 도구인 프리 티어의 설정 파일

## Prettier
Prettier:  자바스크립트 코드를 자동으로 포매팅해주는 도구

개츠비와는 무관하지만 프로그래밍할 때 자동 포매팅을 사용하면 스타일이 일관된 코드를 작성할 수 있어서 매우 편리합니다.

[Prettier 홈페이지](https://prettier.io/docs/en/options.html) https://prettier.io/docs/en/options.html