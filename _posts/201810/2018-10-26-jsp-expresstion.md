---
layout: post
title: JSP 표현식의 단순화
date: 2018-10-26 23:55:00 +0900
author: 원성규
excerpt: 
categories:
- javascript
tags:
- JSP
- EL
- JSTL
keywords:
---

Javascript에서 JQuery를 사용하듯이 JSP에서 EL과 JSTL을 사용한다. 복잡한 표현식을 단축하거나 혼종된 표현식을 단일하게 바꾸어준다.

## EL(Expression Language)
`EL 예시`
```JSP
<body>
pageContext.getAttribute("p1") : ${pageScope.p1 }<br>
request.getAttribute("r1") : ${requestScope.r1 }<br>
session.getAttribute("s1") : ${sessionScope.s1 }<br>
application.getAttribute("a1") : ${applicationScope.a1 }<br>
<br><br>
pageContext.getAttribute("p1") : ${p1 }<br>
request.getAttribute("r1") : ${r1 }<br>
session.getAttribute("s1") : ${s1 }<br>
application.getAttribute("a1") : ${a1 }<br>
</body>
```

## JSTL(JSP Standard Tag Library)
JSTL taglib를 포함해야 한다.
```JSP
<%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %> 
```
`JSTL 예시`
```JSP
<body>
<c:set var="value1" scope="request" value="kang"/>
성 : ${value1} <br>
<c:remove var="value1" scope="request"/>
성 : ${value1 }
</body>
```

```JSP
<%
request.setAttribute("n", 10);
%>
<c:set var="n" scope="request" value="10"/>
```

```JSP
<c:if test="${n == 10}">
n은 과 10과 같습니다.
</c:if>
```

```JSP
<c:choose>
    <c:when test="${score >=90 }">
    A학점입니다.
    </c:when>
    <c:when test="${score >=80 }">
    B학점입니다.
    </c:when>
    <c:when test="${score >=70 }">
    C학점입니다.
    </c:when>
    <c:when test="${score >=60 }">
    D학점입니다.
    </c:when>
    <c:otherwise>
    F학점입니다.
    </c:otherwise>            
</c:choose>
```

```JSP
<%@ page import="java.util.*" %>
<%
    List<String> list = new ArrayList<>();
    list.add("hello");
    list.add("world");
    list.add("!!!");
    request.setAttribute("list", list);
%>
<c:forEach items="${list}" var="item">
    ${item } <br>
</c:forEach>
```



