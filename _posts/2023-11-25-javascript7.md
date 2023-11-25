---
layout: single
title: "Javascript : 개념메모2"
author_profile: false
toc: true
toc_sticky: true
published: true
---

<br>

<a href="https://developer.mozilla.org/en-US/docs/Web/API">
MDN API 문서 참조
</a>

# 자바스크립트 window 

<div class="notice--info">
웹 자바스크립트 콘솔에서 window를 검색하면 무수히 많은 속성이 등장한다. <br>
이 속성들을 직접 이용해 요소를 다루어볼 수 있다. 웹 브라우저에서 자동으로 생성하는 객체임.
</div>

- [ ] var 키워드로 변수 선언하거나 함수 선언 하면 window 객체의 property가 된다.

<img src="/assets/images/Javascript/javascript-window.png" width="80%">

<hr>
<br>

# 돔 (Document Object Model)

<div class="notice--info">
메모리에 웹 페이지 문서 구조를 트리구조로 표현하여 Web Browser가 HTML 페이지를 인식하게 한다.
자바스크립트를 활용하여 이 node 객체들에 접근하고 다룰 수 있다. <b>(DOM에서 제공하는 API로 조작함)</b>
</div>

<hr>
<br>

## DOM 활용 예시

<div class="notice--info">
HTML에서 작성한 태그 및 속성 값들에 접근할 수 있다. 태그가 여러개 존재한다면 배열 접근 방법으로 다루어 볼 수도 있다.
</div>

```javascript
let val;
val = document;

val = document.baseURI;

val = document.head;
val = document.body;
val = document.forms;

val = document.forms[0].id;
val = document.forms[0].classList;
val = document.forms[0].className;

console.log(val);
```

<hr>
<br>

### BaseURI

* 웹 페이지 절대 URI를 반환한다.

<img src="/assets/images/Javascript/javascript-dom1.png" width="90%"/>

<hr>
<br>

### head, body 등 태그 반환

<img src="/assets/images/Javascript/javascript-dom2.png" width="70%"/>

<hr>
<br>

### Array.from()

* HTML Collection을 배열로 만들고 싶을 때 사용한다.

```javascript
let fruits = document.getElementsByName('fruit');
fruits = Array.from(fruits);
```

#### forEach()

* 배열에서 사용할 수 있는 method.

```javascript
fruits.forEach((fruit, index) => {
  fruit.textContent = `${index}. List`
})
```

<hr>
<br>

### 홀수 요소들만 가져올 때

```javascript
const oddEles = document.querySelectorAll('li:nth-child(odd)');
```