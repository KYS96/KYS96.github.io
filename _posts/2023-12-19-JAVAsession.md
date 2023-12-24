---
layout: single
title: "JAVA : 세션 - session(1)"
author_profile: false
toc: true
toc_sticky: true
published: true
categories: [JAVA, SpringFramework]
---

<br>

# Session이란?

* 서로 관련된 요청들을 하나로 묶은 것
* browser 마다 session 객체를 서버에서 제공한다.
* 쿠키는 브라우저에 저장되고 세션은 서버에 저장된다.
* 즉, 로그인 부터 로그아웃 까지를 세션이라고 한다.
* 세션 값은 중복이 되면 안되기 때문에 길다.

<hr>
<br>

# Session을 종료하는 방법

1. 수동 종료
  - **session.invalidate();** 사용.
  - **session.setMaxInactiveInterval(30*60);** 예약종료

2. 자동 종료 - web.xml (분 단위)
  <div class="notice--info">
    &lt;session-config&gt; <br>
      &nbsp; &nbsp; &lt;session-timeout&gt;<b style="color:red;">30</b>&lt;session-timeout&gt; <br>
    &lt;session-config&gt;
  </div>

<hr>
<br>

# 쿠키 , 세션 비교

* 쿠키
  - 대규모 사이트에서는 쿠키를 많이 사용함
  - 브라우저에 저장함
  - 서버 부담 없음
  - 보안에 취약함
  - 서버 다중화에 유리

* 세션
  - 서버에 저장함
  - 서버 부담 있음
  - 보안에 강함
  - 서버 다중화에 불리

<hr>
<br>

# 세션에 대하여....

<div class="notice--info">
만약 브라우저 환경설정에서 cookie를 모두 차단한다고 가정한다. 이때 모든 요청 URL의 제일 뒤에 세션ID값이 붙게 된다.
여기서 붙어오는 세션ID를 가지고 서버가 브라우저를 구분하게 된다.
이러한 상황에서는 브라우저에서 추가로 응답헤더에도 세션ID값을 준다.
</div>

<div class="notice--info">
서버 부담을 줄이기 위해 요청 URL에는 반드시 아래의 태그를 작성하도록 하자.
</div>

<img src="/assets/images/JAVA/JAVA-요청URL.png/">