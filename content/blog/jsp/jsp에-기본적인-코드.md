---
title: jsp에 기본적인 코드
date: 2020-10-08 17:10:50
category: jsp
draft: false
---

### <c:if> 태그 사용 방법

```javascript
<기본 방식>
<c:if test="조건">
...
</c:if>

<방식 1 >
항상 true
<c:if test="true">
...
</c:if>

<방식 2 >
항상 false
<c:if test="some txt">
...
</c:if>

<방식 3 >
EL의 결과값이 true인 경우 몸체 내용 실행 함
<c:if test="${expr}">
...
</c:if>

<방식 4 >
표현식의 결과값이 true인 경우 몸체 내용 실행 함
<c:if test="<%= expr %>">
...
</c:if>

<방식 5 >

<c:if test="<%= someCondition %>" var="testResult">
...
</c:if>
테스트 조건 검사 결과는 ${testResult}입니다.



```

### c:if 주의할 점

- test 속성은 true나 false에 해당하는 값이 온다. 이 조건 값이 true이면, 몸체 내용을 처리한다.
- test 속성은 표현식이나 EL 또는 정적 문자열을 값으로 가질 수 있다.

### <c:if> 태그 사용 예제

```xml
<%@ page contentType = "text/html: charset="utf-8" %>
<%@ taglib prefix="c" uri="http://java.sun.com/jsp/core" %>
<html>
<head><title>if 태그</title></head>
<body>
    <c:if test="true">
    무조건 수행<br>
    </c:if>

    <c:if test="${param.name == "bk"}">
        name 파라미터의 값이 ${param.name} 입니다.
    </c:if>


    <c:if test="${18 < param.age>}">
        당신의 나이는 18세 이상입니다.
    </c:if>

</body>
</html>

```

---

### <c:choose>, <c:when>, <c:otherwise> 태그 사용 방법

- <c:choose> 태그는 자바의 switch 구문과 if-else 블록을 혼합한 형태로서 다수의 조건문을 하나의 블로게어 수행할 떄 사용한다.

```javascript
<c:choose>
  <c:when test="${member.level == 'trial'}">...</c:when>
  <c:when test="${member.level == 'reaular'}">...</c:when>
  <c:when test="${member.level == 'provider'}">...</c:when>
  <c:otherwise>...</c:otherwise>
</c:choose>
```

### 설명

`</:choose / >`태그는 다수의 `<c:when>` 태그를 중첩해서 사용하는데, 각각의 `<c:when>`태그는 test 속성의 값이 true일 때 내부 블록을 수행한다. test 결과가 true인 첫 번째 `<c:when>` 태그의 test 결과값이 false이면 `<c:otherwise>` 를 실행한다. `<c:otherwise>` 태그는 필수는 아니며 필요한 경우에만 추가하면 된다.

### <c:choose> 태그 사용 예제

```xml
<%@ page contentType = "text/html: charset="utf-8" %>
<%@ taglib prefix="c" uri="http://java.sun.com/jsp/core" %>
<html>
<head><title>choose 태그</title></head>
<body>
    <ul>
        <c:choose>
            <c:when test=${param.name == "bk"}>
                <li>당신의 이름은 ${param.name} 입니다.</li>
            </c:when>
            <c:when test=${param.age > 20}>
                <li>당신은 20세 이상입니다.</li>
            </c:when>
            <c:otherwise>
                <li>당신은 'bk'가 아니고 20세 이상이 아닙니다.</li>
            </c:otherwise>
        </c:choose>
    </ul>
</body>
</html>

```

### 예제 간단 설명

- when 태그를 충족하지 않으면 otherwise 태그를 실행한다.
- when 태그중 하나라도 충족되면 otherwise 태그를 실행하지 않는다.

---

### <c:forEach> 태그 사용 방법

forEach 태그는 배열, Colletion 또는 Map에 저장되어 있는 값들을 순차적으로 처리 할 때 사용한다.
자바의 for, do-while 등을 대신하여 사용한다.

```javascript
<c:forEach var="변수" items="아이템">
  ...
  <tr>
      <td align="right" bgcolor="#fff">
        ${변수사용}
      </td>
      ...
  </tr>
</c:forEach>


// begin 속성과 end 속성을 통해 for문과 같은 효과를 낼 수 있다.
<c:forEach var="i" begin="1" end="10">
  ${i} 사용
</c:forEach>

// step 속성을 사용하면 증가분을 변경할 수 있다.
<c:forEach var="i" begin="1" end="10" step="2">
  ${i} 사용
</c:forEach>

// items 속성과 함께 begin,end 속성을 사용하면 참조할 변수의 개수를 제한할 수 있다.
<c:forEach var="i" items="${intArray}" begin="2" end="4">
  [${i}]
</c:forEach>

```
