---
layout: post
title: Corona-Board-initial
categories : Corona-Board-Backend
---
# || in js
 ||는 일반적으로 OR 연산을 의미 하지만 자바스크립트에서는 특수한 용도가 하나 더 있습니다. ||를 사용하면 연산자 왼쪽 값이 undefined, null, false 또 는 빈 문자열인 경우 연산자 오른쪽 값이 해당 표현식의 최종값이 됩니다. 이러한 특징을 이용해 **특정 변수에 값이 없을 때 를 대비해 기본값을 지정하는 용도** 로 많이 활용됩니다. 앞의 코드에서는 process.env.PORT값이 따로 지정되지 않았을 때 8080을 port 변수에 할당합니다.