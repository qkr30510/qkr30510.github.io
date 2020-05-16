---
title: '프론트앤드면접질문PART1'
date: 2020-04-08 14:10:13
category: 'etc'
draft: false
---

### 함수형 프로그래밍, 절차지향 프로그래밍, 객체지향프로그래밍이란 무엇인가

- 함수형 프로그래밍

  - 순수 함수를 조합하고 소프트웨어를 만드는 방식이다. 선언형 프로그래밍에 속하며, 대표적인 예로는 클로저, 하스켈, 리스프 등이 있다.

- 절차지향 프로그래밍

  - 절차지향 프로그래밍이란, 일이 진행되는 순서대로 프로그래밍을 하는 방법이다. 명령형 프로그래밍에 속하며, 대표적인 예로는 C, C++ 등이 있다.

- 객체지향프로그래밍

  - 객체지향 프로그래밍이란, 캡슐화, 상속, 다형성의 특징이 있으며 모듈 재사용 등으로 인해 확장 및 유지 보수에 상대적으로 용이하다. 명령형 프로그래밍에 속하며, 대표적인 예로는 C++, JAVA, C#등이 있다.<br>

> **명령형 프로그래밍 이란,** 프로그래밍의 상태와 상태를 변경시키는 구문의 관점에서 연산을 설명하는 방식이고,
> **선언형 프로그래밍 이란,** 어떤 방법으로 해야 하는지를 나타내기보다 무엇과 같은지를 설명하는 방식이다.

<br>
<br>
<a class="source_link" href="https://susu91.tistory.com/105" target="_blank">출처</a>
<a class="source_link" href="https://madplay.github.io/post/functional-programming-object-oriented-programming" target="_blank">출처</a>
<a class="source_link" href="https://gs.saro.me/dev?tn=428" target="_blank">출처</a>
<a class="source_link" href="https://velog.io/@kyusung/%ED%95%A8%EC%88%98%ED%98%95-%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D-%EC%9A%94%EC%95%BD" target="_blank">출처</a>
<br>
<br>

---

### 함수형 프로그래밍이 갖는 장점과 단점은 무엇인가.

1. 장점

   1. 순수 함수들로 작성하면 모듈성이 증가
   2. 버그가 생길 여지가 적다,
   3. 가독성과 유지 관리 편의성이 향상
   4. 함수를 사용하기 때문에 반복되는 개발이 쉬워진다
   5. 함수를 먼저 작성하는 형태다.

2. 단점

   1. 반복문에 비해 속도가 느리다.
   2. 스택을 잡아먹기 때문에 반복이 많아질 경우 최악의 경우 스택오버플로 오류를 뱉을 수 있다.
   3. 함수형 언어가 쓰래드-병행의 근본적인 문제를 해결해 주지는 않는다.
   4. 언어적 제약으로 좀 더 안전하게 도와주는 것이다.

<br>
<br>
<a class="source_link" href="https://blog.sonim1.com/113 [Kendrick's Blog]" target="_blank">출처</a>
<a class="source_link" href="https://gs.saro.me/dev?tn=428" target="_blank">출처</a>
<br>
<br>

---

### 자바스크립트의 기본형 변수와 참조형 변수란 각각 무엇인가. 또한 기본형 변수와 참조형변수의 예제 코드를 작성하시오

- Primitive Type(기본형) : 값을 그대로 할당, 기본형 과정(변수에 할당 -> 데이터가 비어있는 주소를 찾아서 데이터 할당 -> 같은 변수에 할당-> 해당 변수가 가지고있는 주소로 가서 데이터 할당)

```javascript
Number, String, Boolean, null, undefined
let a = 5
let b = 5
b = 7
```

- Reference Type(참조형) : 참조된 주소를 할당, (변수에 할당 -> 데이터가 비어있는 주소로 가서 데이터안에 주소와 데이터를 할당 -> 데이터안의 주소에는 해당 주소에 의한 데이터를 한번 더 참조)

```javascript
Array, Function, RegExp
let obj1 = {
  a: 1,
}
```

<br>
<a class="source_link" href="https://epthffh.tistory.com/entry/Javascript-%ED%95%B5%EC%8B%AC-%EA%B0%9C%EB%85%90-%EC%95%8C%EC%95%84%EB%B3%B4%EA%B8%B0-%E2%80%93-JS-Flow%EA%B8%B0%EB%B3%B8%ED%98%95%EA%B3%BC-%EC%B0%B8%EC%A1%B0%ED%98%95" target="_blank">출처</a>
<br>

---

### 브라우저 캐시란 무엇인가. 브라우저 캐시로 인해 css가 반영안되는 경우 어떻게 해야 하는가

브라우저나 웹에서의 캐시는 프로그램과 웹사이트 자산을 저장합니다. 웹사이트를 방문했을 때, 당신의 브라우저는 몇 개의 페이지를 가지고 있고 그것을 컴퓨터 하드디스크에 저장합니다. 브라우저가 저장할 자산은 아래와 같습니다.
이미지: 로고, 사진, 백그라운드 등, HTML, CSS, Javascript 유저가 하드디스크에 최신버전파일이 캐시되어 있지 않으면 여러 문제가 발생할 수 있습니다. 포맷이 안맞고, 자바스크립트가 깨지고 올바르지 않는 이미지가 나타납니다.
대부분의 경우 서버가 어떤 자산이 업데이트되고 유저 기기에서 교체되어야 하는지 알고있기 때문에 문제가 되지 않습니다. 만약 일부 유저가 홈페이지가 깨졌다고 문제제기를 하면 브라우저 캐시를 삭제해보라고 권하면 됩니다.
대부분의 브라우저는 ‘캐시 제거’버튼이 있습니다. 버튼을 클릭하면 캐시된 모든 파일이 삭제됩니다. 캐시를 지우고 자주 방문하던 사이트에 들어가봤을 때 로드되는 얼마나 걸리는지 확인해보세요.

<br>
<a class="source_link" href="https://yngmanie.space/posts/cache" target="_blank">출처</a>
<br>

---

### use strict를 쓰면 어떤 변화가 생기는가

Strict Mode는 코드에 더 나은 오류 검사를 적용하는 방법입니다.
Strict Mode를 사용하면, 예를 들어 암시적으로 선언한 변수를 사용하거나 읽기 전용 속성에 값을 할당하거나 확장할 수 없는 개체에 속성을 추가할 수 없습니다.
Strict Mode는 ECMAScript 5 버전에 있는 새로운 기능으로써, 당신의 프로그램 또는 함수를 엄격한 운용 콘텍스트 안에서 실행시킬 수 있게끔 합니다. 이 엄격한 콘텍스트는 몇가지 액션들을 실행할 수 없도록 하며, 좀 더 많은 예외를 발생시킵니다.

<br>
<a class="source_link" href="https://ithub.tistory.com/162" target="_blank">출처</a>
<br>
