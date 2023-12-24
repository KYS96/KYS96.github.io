---
layout: single
title: "Javascript : 기본연습5 (options)"
author_profile: false
toc: true
toc_sticky: true
published: true
categories: javascript
sidebar:
  nav: "counts"
---

<div class="notice--primary">
<a href="https://developer.mozilla.org/en-US/docs/Web/API/Intersection_Observer_API" target="_blank">IntersectionObserver() 공식문서</a>
</div>

#  **Options 작성**

<div class="notice--info">
<b style="color:orange">Threshold</b> : 진입점을 명확하게 명시하고 싶다면 option을 설정하게 되는데 이때 활용할 수 있는 옵션은 Threshold가 있다. 작성한 수만큼 요소가 진입했으면 관찰을 하겠다는 의미!
</div>

<div class="notice--info">
<b style="color:orange">rootMargin</b> : 요소가 들어있는 부모 컨테이너에 margin을 지정할 수 있다. 이는 관찰할 수 있는 범위를 조절 할 수 있게 된다. 만약 음수를 작성하면 관찰범위가 좁아진다. 내가 관찰하고 싶은 범위를 직접 지정한다고 볼 수 있다.
</div>

<hr>
<br>

```javascript
let options = {
  rootMargin: "150px", //-150px
  threshold: [0, 0.25, 0.5, 0.75, 1]
};

let observer = new IntersectionObserver(callback, options);
```