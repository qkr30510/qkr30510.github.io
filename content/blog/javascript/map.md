---
title: map
date: 2020-04-29 16:04:60
category: javascript
draft: false
---

이 주제가 map이랑 동일한지 모르겠다..

> 나중에 수정하기로 하자

react 회원가입, 생년월일을 만드는 중 option 처리를 어떻게 만들어야 하나 고민하다가 `map`을 사용하기로 하였다.
맨 처음엔 for 문을 사용했었는데, 생각해보니 map을 사용하는게 좀 더 간지나기도 하고 태그 사용하는데 있어서 좀 더 편리할꺼라는 판단에 변경하였다.

바로 리액트에 작업하면 오류가 발생하여 이게 과연 스크립트의 문제일지, 리액트 문법의 문제일지 판단하기 어려울듯 하여 https://jsfiddle.net/[https://jsfiddle.net/]로 자바스크립트 먼저 연습을 하였다.

```html
<select id="test">
  <option value=""></option>
</select>
```

1. id를 부여한 셀렉트 박스와 option을 주었다.

```javascript
var test = document.getElementById('test')

const one = [1, 2, 3]
let result = one.map(v => {
  return `<option>${v + 1}</option>`
})

test.innerHTML = result.join('')
console.log(result.join(''))
```

1. one 이라는 배열을 먼저 하나 주고
2. result 라는 변수 안에 one을 map 함수로 새로 option 값을 다시 주었다.
   여기서 주의할 점은 자바스크립트 이기 때문에 백틱으로 감싸주었다는 점이다.
3. 그리고 셀렉트에 result를 join 메서드를 통해 넣어줬다.

> join 메서드는 여러 배열을 하나로 연결해주는 메서드이다.
> 현재와 같이 사용했을 경우 <option>1</option><option>2</option><option>3</option>이렇게 쭈욱 이어진다.
