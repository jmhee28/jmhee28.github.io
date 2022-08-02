---
layout: post
title: Section1_let
categories : ES6_javascript
---


## let 
let - blockscope
for문 안에서만 유효
```javascript

var name = "gloval var"

function home() {
  var homevar = "homevar";
  for(let i=0; i<100; i++)
    { }
  console.log(i);
}

home();
```