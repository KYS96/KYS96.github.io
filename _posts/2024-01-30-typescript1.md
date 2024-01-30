---
layout: single
title: "TypeScript : 기본개념(1)"
author_profile: false
toc: true
toc_sticky: true
published: true
categories: TypeScript
sidebar:
  nav: "counts"
---

<br>

<div class="notice--info">
TypeScript는 웹브라우저에서 단독으로 동작할 수 없다. JavaScript로 먼저 변환이 이루어져야 한다. 
</div>

# 1. 환경 구축하기

* Terminal에서 **npm init -y** 실행

* 생성된 package.json 내부에 아래의 코드로 수정
* JSON 형태로 DEV와 BUILD를 추가했다.

```javascript
{
  "name": "ts-practice",
  "version": "1.0.0",
  "description": "",
  "scripts": {
    "dev": "parcel ./index.html",
    "build": "parcel build ./index.html"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "devDependencies": {
    "parcel": "^2.11.0",
    "typescript": "^5.3.3"
  }
}
```

<hr>
<br>

# 2. 프로젝트 패키지 매니저를 통해 TypeScript 설치

* **npm i -D parcel typescript** 실행

<hr>
<br>


# 3. tsconfig.json 생성

```javascript
{
  "compilerOptions": {
    "target": "ES2015",
    "module": "ESNext",
    "moduleResolution": "Node",
    "esModuleInterop": true,
    "lib": ["ESNext", "DOM"],
    "strict": true
  },
  "include": [
    "src/**/*.ts"
  ],
  "exclude": [
    "node_modules"
  ]
}
```

<hr>
<br>

# 4. 실행

* **npm run dev** 입력하여 프로젝트 실행