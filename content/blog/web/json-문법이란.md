---
title: json 문법이란
date: 2020-04-26 17:04:88
category: web
draft: false
---

json이란?

1. JavaScript Object Notation라는 의미릐 축약어로 데이터를 저장하거나 전송할 때 많이 사용되는
   **경량의 DATA 교환 형식**
2. Javascript에서 객체를 만들 때 사용하는 표현식을 의미한다.
3. JSON 표현식은 사람과 기계 모두 이해하기 쉬우며 용향이 작아서, 최근에는 JSON이 XML을 대체해서 데이터 전송 등에 많이 사용한다.
4. JSON은 데이터 포맷일 뿐이며 어더한 통신 방법도, 프로그래밍 문법도 아닌 단순히 데이터를 표시하는 표현 방법일 뿐이다.

### JSON 특징

1. 서버와 클라이언트 간의 교류에서 일반적으로 많이 사용된다.
2. 자바스크립트 객체 표기법과 아주 유사하다.
3. 자바스크립트를 이용하여 JSON 형식의 문서를 쉽게 자바스크립트 객체로 변환할 수 있는 이점이 있다.
4. Json 문서 형식은 자바스크립트 객체의 형식을 기반으로 만들어졌다.
5. 자바스크립트의 문법과 굉장히 유사하지만 텍스트 형식일 뿐이다.
6. 다른 프로그래밍 언어를 이용해서도 쉽게 만들 수 있다.
7. 특정 언어에 종속되지 않으며, 대부분의 프로그래밍 언어에서 JSON 포맷의 데이터를 핸들링 할 수 있는 라이브러리를 제공한다.

### JSON 문법

```javascript
{
  "employees": [
    {
      "name": "Surim",
      "lastName": "Son"
    },
    {
      "name": "Someone",
      "lastName": "Huh"
    },
    {
      "name": "Someone else",
      "lastName": "Kim"
    }
  ]
}

```

- JSON 형식은 자바스크립트 객체와 마찬가지로 key/value가 존재할 수 있으며 key값이나 문자열은 항상 쌍 따음표를 이용하여 표기 해야한다.
- 객체, 배열 등의 표기를 사용할 수 있다.
- 일반 자바스크립트의 객체처럼 원하는 만큼 중첩시켜서 사용할 수도 있다.
- JSON형식에서는 null,number,string,array,object,boolean을 사용할 수 있다.

### JSON 형식

1. name-value 형식의 쌍

- 여러가지 언어들에서 object등으로 실현되었다.
- {String Key:String value}

```javascript
{
  "firstName": "Kwon",
  "lastName": "YoungJae",
  "email": "kyoje11@gmail.com"
}

```

2. 값들의 순서화된 리스트 형식

- 여러가지 언어들에서 배열(Array) 등으로 실현되었다.
- [value1, value2, ...]

```javascript
{
  "firstName": "Kwon",
  "lastName": "YoungJae",
  "email": "kyoje11@gmail.com",
  "hobby": ["puzzles","swimming"]
}
```

### JSON의 문제점

AJAX는 단순히 데이터만이 아니라 JavaScript 그 자체도 전달할 수 있다. 이 말은 JSON데이터라고 해서 받았는데 단순 데이터가 아니라 JavaScript가
될 수도 있고, 그게 실행 될 수 있다는 것이다. (데이터인 둘 알고 받았는데 악성 스크립트사 될 수 있다.)

위와 같은 이유로 받은 내용에서 순수하게 데이터만 추출하기 위한 JSON 관련 라이브러리를 따로 사용하기도 한다.

### JSON이 가져올 수 있는 데이터

JSON으로 가져올 수 있는 데이터는 해당 자바스크립트가 로드된 서버의 데이터에 한정된다.
JSON은 단순히 데이터 포맷일 뿐이며 그 데이터를 불러오기 위해선 XMLHttpRequest()라는 JavaScript 함수를 사용해야 하는데 이 함수가 동일 서버에 개한 것만 지원하기 때문이다. (JSONP 또는 프락시 역할을 하는 서버쪽 Script 파일로 가능하게도 할 수 있다. )

### JSON 형식 텍스트를 JavaScript Object로 변환하기

```javascript
var jsonText = '{ "name": "Someone else", "lastName": "Kim" }' // JSON 형식의 문자열
var realObject = JSON.parse(jsonText)
var jsonText2 = JSON.stringify(realObject)

console.log(realObject)
console.log(jsonText2)
```

- JSON.parse(JSON으로 변환할 문자열) : JSON 형식의 텍스트를 자바스트립트 객체로 변환한다.
- JSON.stringify(JSON 문자열로 변환할 값) : 자바스크립트 객체를 JSON 텍스트로 변환한다.

<a class="source_link" href="https://velog.io/@surim014/JSON%EC%9D%B4%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80" target="_blank">출처</a>
