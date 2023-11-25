---
layout: single
title: "Javascript : 개념메모3"
author_profile: false
toc: true
toc_sticky: true
published: true
---

<br>

# DOM EVENT

```javascript
document.querySelector('btn').addEventListener('click', (event) => {
  let val;
  
  val = event.type;
  val = event.clientY
  val = event.offsetY
})
```

* **event type**
  - 현재 발생한 이벤트의 타입을 알려준다.
  
* **event.clientY**
  - 윈도우로부터의 거리 좌표
  
* **event.offsetY**
  - 요소로부터의 거리 좌표

  <hr>
  <br>
  
# UI 이벤트의 종류

* load
  - 문서나 객체가 로드 완료 시 발생
  
* change
  - 객체의 내용이 변경되거나 포커스 잃을 때 방생
  - losefocus
  
* resize
  - 객체의 크기가 바뀌었을 때 발생
  
* scroll
  - 스크롤바를 조작할 때 발생
  
* error
  - 에러 시 발생

<hr>
<br>

# keyboard 이벤트의 종류

* keydown
  
* keyup
  
* keypress
  - 문자 입력 시 발생

<hr>
<br>

# 마우스 이벤트

* click
  
* dblclick
  
* mouseup
  
* mousedown
  
* mouseover
  
* mousemove
  
* mouseout
  
* mouseenter
  
* mouseleave

<hr>
<br>

# 나머지 이벤트

* blur
  
* cut
  - 잘라내기를 했을 때 발생
  
* paste
  - 붙여넣기를 했을 때 발생
  
* input
  - input 요소 값이 달라질 때 발생

<hr>
<br>

# javascript prototype

```javascript
let user = {
  name: 'Jhon',
  age: 45,
  email: 'jhon@yahoo.com'
}

console.log(user.name);
console.log(user.hasOwnProperty('email'));
```

<img src="/assets/images/Javascript/javascript-property.png" width="40%"/>

<br>

<div class="notice--info">
실제 객체를 확인해보면 내부에 Prototype이라는 속성이 존재한다.
</div>

<img src="/assets/images/Javascript/javascript-property2.png" />

## Protoype이란?

* javascript 객체가 다른 객체로부터 메서드와 속성을 상속받는 메커니즘.
* 프로토타입 객체에 있는 hasOwnProperty를 상속받아 사용하는 것을 떠올려보자.
* 더 적은 메모리 사용 가능
* 코드 재사용 가능

### 활용예제

```javascript
function Fruit(name, weight, growDate) {
  this.name = name;
  this.weight = weight;
  this.growDate = new Date(growDate);
  this.calcWhenBrought = function() {
    const date =
    this.growDate.getFullYear() 
    + '-' +
    (this.growDate.getMonth()+1)
    + '-' +
    this.growDate.getDate();
    return date;
  } 
}

const kiwi = new Fruit('kiwi', 15, '2023-12-25');
const apple = new Fruit('apple', 7, '2023-10-16');

console.log(kiwi);
console.log(apple);
```

<br>

* 아래처럼 클래스 내부에서 작성한 <b>this.calcWhenBrought()</b>을 삭제하고 아래 prototype 속성을 활용하여 별도로 만들어주었다. 동일한 함수를 또 사용할 필요는 없기 때문에 속성 처리를 해주었음. (재사용 가능하게 하고 효율을 높이기 위해서)

* 즉 prototype 속성에 메서드가 들어갈 수 있게끔!

```javascript
function Fruit(name, weight, growDate) {
  this.name = name;
  this.weight = weight;
  this.growDate = new Date(growDate);
}

Fruit.prototype.calcWhenBrought = function () {
    const year = (this.growDate).getFullYear();
    return year;
}

const kiwi = new Fruit('kiwi', 15, '2023-12-25');
const apple = new Fruit('apple', 7, '2023-10-16');

console.log(kiwi);
console.log(apple);
```

<hr>
<br>

# ES6 Classes

* ES6 문법에서 클래스 내부에 함수를 만들면 자동으로 prototype 속성에 들어가게 된다.

* static 타입의 함수를 만들 수도 있는데 prototype이 아닌 클래스 함수 자체에 메서드를 설정 시 만든다.
  - 정적 메소드
  - 메서드 사용 시 클래스 이름에서 접근하여 사용한다.

```javascript
class Student {
  constructor(stuNo, name, birthday) {
    this.stuNo = stuNo;
    this.name = name;
    this.birthday = new Date(birthday);
  }

  static study() {
    return 'I ruined my exam!';
  }

  introduce() {
    return `Hello my name is ${this.name}`;
  }
}

const student1 = new Student('1', 'Kim', '10-3-06');
console.log(student1);
```

<img src="/assets/images/Javascript/javascript-prototype.png" width="80%"/>

