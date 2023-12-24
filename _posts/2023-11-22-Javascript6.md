---
layout: single
title: "Javascript : 개념메모1"
author_profile: false
toc: true
toc_sticky: true
published: true
categories: javascript
sidebar:
  nav: "counts"
---

<br>

# 배열인지 아닌지 확인할 때

## Array.isArray()

* 결과 값으로 boolean 데이터가 출력됨.

```javascript
const students = ['Kim', 'Tom', 'Yoo', 'Hyun', 'Mark'];

console.log(Array.isArray(students));

//True 출력
```

<hr>
<br>


# for/in

* 객체의 속성을 따라 반복한다.

```javascript
const face = {
  eye: '꼬막눈',
  nose: '복코',
  jaw: '사각턱'
}

for (let x in face) {
  console.log(`${x} : ${face[x]}`);
}
```

<img src="/assets/images/Javascript/javascript-forin문.png" width="50%">


<hr>
<br>

# 배열 컨트롤하는 방법

## forEach()

```javascript
const countries = ['북한', '베트남', '러시아', '중국'];

countries.forEach(function (country, index, array) {
  console.log(`${index} : ${country}`);
  console.log(array);
});
```
<img src="/assets/images/Javascript/javascript-forEach.png" width="65%">

<br>

## map()

```javascript
countries.map(function (country) {
  console.log(country);
});
```

<img src="/assets/images/Javascript/javascript-map.png" width="35%">