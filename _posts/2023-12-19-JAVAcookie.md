---
layout: single
title: "JAVA : 쿠키 - cookie"
author_profile: false
toc: true
toc_sticky: true
published: true
categories: [JAVA, SpringFramework]
sidebar:
  nav: "counts"
---

# 쿠키는?

<div class="notice--info">
쉽게 말해, 클라이언트를 식별하기 위한 기술이다.
</div>

* 이름과 값의 쌍으로 구성된 작은 정보.
* ASCII 문자만 가능함.
* 도메인 정보, path 정보, 유효기간 정보 확인 가능함.
* 한글은 URL 인코딩이 필요함.
* 쿠키가 저장되는 공간은 Browser이며 유효기간 지나면 자동으로 삭제된다.

<br>

# 쿠키 생성 방법

* 응답 객체 response에 쿠키를 담는다.

```java
Cookie cookie = new Cookie("id", "ys1996");
cookie.setMaxAge(60*60*24); //24시간
response.addCookie(cookie);
```

<br>

# 쿠키 삭제 방법

* id에 아무런 값을 넣지 않는다.
* 유효기간을 0으로 설정한다.
* 응답 객체 response에 쿠키를 추가한다.

```java
Cookie cookie = new Cookie("id", "");
cookie.setMaxAge(0);
response.addCookie(cookie);
```

<br>

# 쿠키 변경 방법

```java
Cookie cookie = new Cookie("id","");
cookie.setValue(URLEncoder.encode("아바타")); //값 변경
cookie.setDomain("www.yahoo.co.kr");
cookie.setPath("/home2");
cookie.setMaxAge(60*60*24*7)
response.addCookie(cookie); // 얘를 꼭 잊어먹으면 안된다.
```

<br>

# 쿠키 읽어 오는 방법

```java
Cookie[] cookies = request.getCookies();

for(Cookie cookie : cookies) {
  String name = cookie.getName();
  String value = cookie.getValue();

  System.out.printf("[cookie]name=%s, value=%s%n", name, value);
}
```