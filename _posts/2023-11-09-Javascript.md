---
layout: single
title: "Javascript : 기본연습1"
author_profile: false
toc: true
toc_sticky: true
published: true
categories: javascript
---

<br>

# Document
  
  * document는 문서 전체를 의미하며 보통은 
    document로 시작하여 요소에 접근한다.
  
  * winodw(글로벌 객체)는 브라우저에서 제공하는 객체이다.

```javascript
window.document.querySelector('#practice')
```

<hr>
<br>

# getBoundingClientRect()
# offsetHeight()

<div class="notice--info">
요소의 속성을 (높이, 좌, 우, 바닥) 측정하는 함수.
자세한 소수점까지 확인하고 싶을 때 getBoundingClientRect() 사용한다.
</div>

<div class="notice--info">
딱 정수부분의 요소 속성만 확인하고 싶을 때는 offsetHeight을 사용한다.
</div>

```javascript
const footer = document.querySelector('#footer');
const footerHeight = footer.getBoundingClientRect().height;
```

```javascript
const footer = document.querySelector('#footer');
const footerHeight = footer.offsetHeight;
```

<hr>
<br>

# window.scrollY()

<div class="notice--info">
현재 브라우저에서 스크롤을 움직일 때마다 어느정도 움직였는지 나타내줌
</div>

```javascript
document.addEventListener('scroll', () => {
  if(window.scrollY > footerHeight) {
    footer.classList.add('footer--dark');
  } else {
    footer.classList.remove('footer--dark')
  }
});
```