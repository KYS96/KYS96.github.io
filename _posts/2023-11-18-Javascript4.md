---
layout: single
title: "Javascript : 기본연습4 (IntersectionObserver)"
author_profile: false
toc: true
toc_sticky: true
published: true
---

<br>

<div class="notice--primary">
<a href="https://developer.mozilla.org/en-US/docs/Web/API/Intersection_Observer_API" target="_blank">IntersectionObserver() 공식문서</a>
</div>

- [ ] 관찰하고 싶은 요소가 화면에 있는지 확인하는 목적으로 자바스크립트에서는 Intersection API를 사용하면 된다. 실무에도 많이 사용되며 활용도가 매우 높다.

<hr>
<br><br>

* **기본 개념**
  - fruit 클래스의 요소들을 가져와 관찰을 하겠다는 코드를 작성한다.
  - 사용자가 어디 화면을 보고 있느냐에 따라서 요소를 노출시키거나 감출 수 있는 행동을 추가할 수 있다.
  - 관찰을 시작할 때마다 호출이 되기를 원하는(원하는 동작 기술) 콜백함수를 작성한다.
  - 관찰되는 값은 거의 다수의 값이기 때문에 배열 형태로 전달한다. 

<div class="notice--info">
<b>isIntersecting</b> : 화면에 요소가 진입하였는지 boolean 값으로 표현된다.<br>
<b>intersectionRatio</b> : 화면에 요소가 얼마만큼 진입하였는지 수치가 표현된다.<br>
<b>entry</b> : 관련된 또다른 여러 속성을 확인하려면 entry를 콘솔에 찍어 확인해보자.
</div>

<hr>
<br>

* **예시**

```html
<body>
  <div class="fruit">딸기</div>
  <div class="fruit">사과</div>
  <div class="fruit">감</div>
  <div class="fruit">포도</div>
  <div class="fruit">귤</div>
  <div class="fruit">배</div>
<body>
```

<div class="notice--info">
isIntersecting 값이 0보다 클 때 ripe 클래스를 추가하고 0이 되면 ripe 클래스를 제거한다.
</div>

```javascript
const callback = (entries) => {
  entries.forEach(entry => {
    if(entry.isIntersecting) {
      entry.target.classList.add('ripe');
    } else {
      entry.target.classList.remove('ripe');
    }
    console.log(entry.target);
    console.log(entry.isIntersecting);
    console.log(entry.intersectionRatio);
  });
}

const observer = new IntersectionObserver(callback);
const fruits = document.querySelectorAll('.fruit');
fruits.forEach(fruit => observer.observe(fruit));
```

<img src="/assets/images/Javascript/IntersectionObserver-1.png" width="100%"/>