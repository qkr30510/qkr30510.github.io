---
title: for 문(for,for-in)
date: 2020-07-13 14:07:78
category: javascript
draft: false
---

자바스크립트의 기본 중 하나인 for문에 대해 정리해본다.

### for문

- for문은 초기식, 표현식, 증감식을 모두 포함하고 있는 반복문입니다.

  ```javascript
  for (초기식; 조건식; 증감식){
      조건식의 결과가 참인 동안 반복적으로 실행하고자 하는 실행문;
  }

  // 사용 예)
  for(let i = 0; i < 5; i++){
      document.write(i + "<br>")
  }
  // 결과
  1
  2
  3
  4
  5
  ```

### for in문

- for-in문은 해당 객체의 모든 열거할 수 있는 프로퍼티를 순회 할 수 있도록 해줍니다.

```javascript
for(변수 in 객체){
    객체의 모든 열거할 수 있는 프로퍼티의 개수 만큼 반복적으로 실행하고자 하는 실행문
}
```

```javascript

배열에서 사용할 때

//사용 예
- (일반 for문 사용시)
var arr = [3,4,5];
for (var i = 0; i < arr.length;  i++){
    document.write(i +"");
}
document.write("<br>");

//결과
0 1 2


- (for-in문 사용시)
var arr = [3,4,5];
for (var i in arr){
    document.write(i +"");
}
document.write("<br>");

//결과
0 1 2

```

```javascript
 객체에서 사용할때

// 사용 예
var obj = {
    name: '이순신',
    age : 20
}

for (var i in obj){
    document.write(i+ "<br>")
}

// 결과
name
age
```

### for of문

for-of문은 반복할 수 있는 객체를 순회할 수 있도록 해주는 반복문입니다.

자바스크립트에서 반복할 수 있는 객체에는 Array, Map, Set, arguments 객체 등이 있습니다.
이 반복문은 루프마다 객체의 열거할 수 있는 프로퍼티의 값을 지정된 변수에 대입합니다.

```javascript
for (변수 of 객체){
    객체의 모든 열거할 수 있는 프로퍼티의 개수만큼 반복적으로 실행하고자 하는 실행문
}
```

```javascript
//사용 예
- (일반 for문 사용시)
var arr = [3,4,5];
for (var i=0; i< arr.length; i++){
    document.write(arr[i] + "")
}
document.write("<br>");
// 결과
3 4 5

- (for-of문 사용시)
var arr = [3,4,5];
for (var value of arr){
    document.write(value + "");
}
// 결과
3 4 5

```

### 최종정리:

- for문
  - 조건식의 결과가 참인 동안 반복적으로 실행하고자 하는 실행문;
- for-in문
  - 객체의 모든 열거할 수 있는 프로퍼티의 개수 만큼 반복적으로 실행하고자 하는 실행문
- for-of문
  - 객체의 모든 열거할 수 있는 프로퍼티의 개수만큼 반복적으로 실행하고자 하는 실행문

> 출처: https://yjshin.tistory.com/entry/JavaScript-%EC%9E%90%EB%B0%94%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8-for-%EB%AC%B8-for-in-%EB%AC%B8-for-of-%EB%AC%B8
