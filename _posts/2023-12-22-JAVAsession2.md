---
layout: single
title: "JAVA : 세션 - session(2)"
author_profile: false
toc: true
toc_sticky: true
published: true
categories: [JAVA, SpringFramework]
---

<br>

# 세션의 시작?

* 보통 웹사이트의 홈이나 로그인 페이지와 같은 곳에서는 session이 필요하지 않다.

* 세션은 서버에 부담이 많이 가기 때문에 최대한 유지 시간이 짧아야 한다.

* 따라서 jsp에 세션의 값에 **true**나 **false**값을 줄 수 있다.

```java
<%@ page session="true" %>
<%@ page session="false" %>
```

<div class="notice--info">
<b>session="true"</b>일 때 세션이 있을 때 생성되고, <br>
<b>session="false"</b>일 때 세션이 없을 때 생성되지 않는다. <br>
<b>새로운 세션을 시작하느냐 안하느냐를 정한다고 생각하자.</b><br>
세션을 일단 시작하고 나면 true나 false나 상관없음. <br>
true가 보통 페이지의 default 값이다. <br>
따라서 세션이 필요하지 않은 페이지에는 모두 false 값을 적용하자.
</div>

