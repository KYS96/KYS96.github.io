---
layout: single
title: "Javascript : 개념메모4"
author_profile: false
toc: true
toc_sticky: true
published: true
---

<br>

# constructor (생성자)

* **생성자**사용하여 다른 메서드를 호출하기 전에 수행해야 하는 사용자 지정 초기화를 제공할 수 있다. new 연산자를 사용하여 객체 생성하면 constructor에 작성한 내용이 먼저 실행되는 것이다.

```javascript
class Student {
  constructor(stuNo, name) {
    this.stuNo = stuNo;
    this.name = name;
  }

  sayHi() {
    return `Hello my name is ${this.name}`;
  }
}

const student1 = new Student('1', 'Kim');
student1.sayHi();
```

<hr>
<br>

# 자바스크립트 Closure

<div class="notice--info">
다른 함수 내부에 정의된 함수가 있는 경우 외부 함수가 실행을 완료하고 해당 변수가 해당함수 외부에서 더 이상 접근할 수 없는 경우에도 해당 내부 함수는 외부 함수의 변수 및 범위에 접근할 수 있다.
</div>

<div class="notice--info">
클로저(Closure)는 JavaScript에서 중요한 개념 중 하나로, 함수가 정의될 때의 환경을 기억하고 있는 함수를 말한다. 이를 통해 함수 내부에서 외부 변수에 접근하거나 외부 변수의 값을 변경할 수 있다. 함수가 함수를 리턴하는 것.
</div>

<div class="notice--info">
다른 함수 내부에 정의된 함수가 있는 경우 외부 함수가 실행을 완료하고 해당 변수가 해당 함수 외부에서 더 이상 접근할 수 없는 경우에도 해당 내부 함수는 외부 함수의 변수 및 범위에 접근할 수 있다.
</div>

```javascript
function outerFunction() {
  let outerVariable = 10;

  return  function innerFunction() {
    console.log(outerVariable);
  }
}

const closureExample = outerFunction();
closureExample(); // 결과: 10
```

- [ ] Answer

  * 이 예제에서 outerFunction은 외부 변수 outerVariable을 가지고 있습니다. 그리고 innerFunction은 외부 함수인 outerFunction의 변수에 접근할 수 있습니다.

  * outerFunction이 호출되면 outerVariable에 할당된 값인 10이 출력되는 innerFunction이 반환됩니다. 반환된 closureExample 함수가 호출될 때, 여전히 outerVariable의 값을 기억하고 있기 때문에 결과로 10이 출력됩니다. 이것이 클로저의 핵심입니다. innerFunction은 자신의 스코프뿐만 아니라 외부 함수인 outerFunction의 스코프도 기억하고 있어서, outerVariable을 참조할 수 있게 됩니다.

  * 클로저는 주로 콜백 함수, 비동기 작업, 정보은닉 등 다양한 상황에서 활용됩니다. 함수가 정의된 시점의 환경을 기억하기 때문에, 해당 함수가 호출될 때의 문맥을 유지하면서 작업을 수행할 수 있습니다.

<br>

```javascript
let a = 'a';
function outerFunction() {
  function innerFunction() {
    let c = 'c';
    console.log('a, b, c');
  }
  let b = 'b';
  console.log(a, b);
  innerFunction();
}

outerFunction();
```

<img src="/assets/images/Javascript/javascript-closure.png" width="65%"/>

