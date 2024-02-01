---
layout: single
title: "TypeScript : 기본개념(2)"
author_profile: false
toc: true
toc_sticky: true
published: true
categories: TypeScript
sidebar:
  nav: "counts"
---

<br>

# 1. 문자

```typescript
let str: string
let blue: string = "Blue"
let myColor: string = `MyColor : ${blue}`
```

<img src="/assets/images/typescript/typescript1.png" />


<hr>
<br>

# 2. 숫자

```typescript
let num: number
let integer: number
let float: number
let infinity: number = Infinity
let nan: number = NaN
```

<hr>
<br>


# 3. Boolean

```typescript
let isBoolean: boolean
let isDone: boolean = false
```

<hr>
<br>


# 4. 배열

* 요소의 타입들이 *문자이거나 숫자이거나*

```typescript
const union = (string|number)[] = ['Apple', 88, 'Grape', 723, 1, 'BB']
const array: number[] = [1, 2, 3]
```

<hr>
<br>


# 5. 객체

```typescript
const userA: {
  name: string
  age: number
  isValid: boolean
} = {
  name: 'Hello',
  age: 12,
  isValid: true
}
```

<hr>
<br>


# 6. 인터페이스

```typescript
interface User {
  name: string
  age: number
  isValid: boolean
}
const userB: User = {
  name: 'YOU',
  age: 23,
  isValid: false
}
```

<hr>
<br>

# 7. 함수

```typescript
const add: (x: number, y: number) => number = function (x, y) {
  return x + y
}

const multiply = function (x: number, y: number): number {
  return x * y
}

const a: number = add(10, 20)

const helloFirst: () => void = function () {
  console.log('반환 값 없음~ void~')
}

const helloSecond = function (): void {
  console.log('반환 값 없음~ void~')
}

const h: void = helloFirst()
```

<hr>
<br>

# 8. Any

* 모든 타입을 다 받음
* 그러나 타입스크립트를 사용하는 의미가 희미해지기 때문에 사용하지 않는 것이 권장 됨
* 명확하게 데이터 타입을 알 수 없는 상황에서는 unknown을 사용하자

```typescript
let hi: any = 'Hello world'
hi = 999
hi = false
hi = null
hi = []
hi = {}
hi = function(){}
```

<hr>
<br>

# 9. Union

```typescript
let unionType: string | number | boolean
unionType = 'Hello type!'
unionType = 123
unionType = false
```

<hr>
<br>

# 10. Intersection 타입

```typescript
interface Animal {
  name: string,
  weight: number
}
interface Validation {
  isRabiesed: boolean
}
const dog: Animal & Validation = {
  name: 'Bokdol',
  weight: 6.4,
  isRabiesed: false
}
```