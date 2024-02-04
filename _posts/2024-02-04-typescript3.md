---
layout: single
title: "TypeScript : 타입 가드"
author_profile: false
toc: true
toc_sticky: true
published: true
categories: TypeScript
sidebar:
  nav: "counts"
---

<br>

# 타입 가드?

<div class="notice--info">
❓ 실제로 그 데이터가 존재 할 때만 동작하게 만들어 준 것.<br>
❓ If 조건이나 기타 다양한 표현을 통해서 작성된 코드가 잘 동작할 수 있게 방어를 한 것.<br>
❓ 어떤 내용이 들어가도 타입이 방어가 된다면 좋다.<br>
❓ 자바스크립트에서도 매우 중요한 개념이다.<br>
❓ 에러가 발생할 수 있는 상황을 코드 상에서 방어한다는 개념으로 생각하자.
</div>

<hr>
<br>

# 예시(1)

<img src="/assets/images/typescript/typescript3.png"/>

```typescript
const h1El = document.querySelector('h1') 
if(h1El instanceof HTMLHeadingElement) {
  logText(h1El)
}
```

<img src="/assets/images/typescript/typescript4.png" />

<hr>
<br>


# 예시(2)

```typescript
function show(val: string | number | boolean) {
  let res = "결과 : "
  if(typeof val === 'string') {
    res += val.toLowerCase()
  }
  if(typeof val === 'number') {
    res += val.toFixed(1)
  }
  console.log(res)
}

show('ColdPlayMusic')
show(167.64452656)
```

<img src="/assets/images/typescript/typescript5.png" />
