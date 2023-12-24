---
layout: single
title: "Servlet & JSP : 개념설명1"
author_profile: false
toc: true
toc_sticky: true
published: true
categories: [Servlet, JSP]
sidebar:
  nav: "counts"
---

<br>

# Servlet과 JSP

 - [ ] 둘의 본래 성격은 동일하다.

 - [ ] Servlet을 발전시킨 것이 Spring이다.

<hr>
<br>

# @WebServlet

 - [ ] 서블릿에서는 @WebServlet 어노테이션을 사용한다.

  * 이는 Controller와 RequsetMapping을 합친 것임.

  * 서블릿 사용 시 HttpServlet을 상속 받음

  * Controller가 조금 더 발전된 형태

<hr>
<br>

# 서블릿 클래스 예시

<img src="/assets/images/JAVA&JSP/서블릿예제.png" width="100%" alt="alt-text"/>

<div class="notice--info">
서블릿 인스턴스가 존재하지 않으면 서블릿 클래스를 로딩하고 인스턴스를 생성한다. 이후 init()이 최초 호출된다. 1개의 서블릿 인스턴스를 만들어 계속 재활용 한다.
</div>

<hr>
<br>

#  JSP

  - Java 코드를 HTML에서 작성하게 하는 기술
  - WebServlet으로 굳이 호출하지 않아도 JSP는 잘 호출이 된다.
  - 서블릿과 유사하게 처음부터 객체를 만들어 놓는 것이 아니고 첫번째 호출 시 객체를 생성한다.
  - 기본적으로 lazy-init 이다.

# JSP 예제

<img src="/assets/images/JAVA&JSP/JSP예제.png" alt="alt-text"/>

<hr>
<br>

#  유효 범위, 속성

* **pageContext**
  - 하나의 페이지(JSP)에서만 접근 가능
  - EL 태그 사용을 위해 저장소가 필요했기에 사용됨

* **application**
  - 웹 어플리케이션 내부 전체 범위를 지님
  - 단 1개만 존재
  
* **session**
  - 클라이언트마다 1개씩 존재
  - 아이디를 저장하기에 적절한 저장소임
  - 최소한의 데이터만 저장한다
  - 서버 부담이 제일 큰 저장소이기도 함
  
* **request**
  - 제일 부담이 적은 객체
  - 다른 페이지에 데이터 전달 시 가급적 request 객체 사용!
  - 그렇지 않다면 session 사용 (잠깐 쓰고 지워라)
  - foward 사용하여 데이터 전달 가능