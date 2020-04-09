---
title: '채팅창 textarea만들기'
date: 2020-04-09 14:10:13
category: 'react'
draft: false
---

리액트 todo리스트를 만들다가 입력창을 여러줄로 입력할수있게 만들어보라는 선생님의 조언이 있었다. <br>
그래서 기존에 들어가 있던 input 태그를 지우고 textarea를 넣었는데 문제가 한가지 발생하였다.
카카오톡에 익숙해져있던 나는 엔터를 치면 **전송**이 되어야하고, 쉬프트키와 엔터를 넣으면 **줄 바꿈**이 되어야하는데 일반적으로 되어있는 textarea는 엔터는 그냥 줄바꿈만 되는것이다.
충족해야 하는 조건은 아래와 같다. <br>

1. 엔터칠때는 전송될 것
2. 쉬프트와 엔터칠땐 줄바꿈

그래서 내가 처음 에 작성한 코드는 아래와 같다.

```javascript
const onKeyPress = e => {
  if (e.key === 'Enter') {
    return
  }
  onClick()
  // onclick 함수에는 submit 함수가 들어가 있다.
}
```

#### 오류는 다음과 같이 일어났다.

1. 리턴된 후에 줄바꿈 일어남
2. 온 클릭된 후에 줄 바꿈 일어남

##### 해결

1. e.preventDefault() 를 추가로 넣어 보았다.

```javascript
const onKeyPress = e => {
  if (e.key === 'Enter') {
    e.preventDefault()
    return
  }
  onClick()
  // onclick 함수에는 submit 함수가 들어가 있다.
}
```

#### 오류는 다음과 같이 일어났다.

1. 온 클릭 이후에도 줄 바꿈이 일어남. 온 클릭에 프리이벤트를 넣으면 엔터가 안됨 ㅜ

##### 해결

1. 모각코에 조언을 구해봄

처음에 작성했던 코드는

```javascript
const onKeyPress = e => {
  if (e.key === 'Enter') {
    if (e.key === 'Enter' && e.shiftKey) {
      return
    }
    e.preventDefault()
    onClick()
  }
}
```

#### 결론

너무 어렵게 생각했던거 같다.
가장 기본적인 엔터값은 if문으로 두고 그 안에 shift 값을 넣어 그 값이 있다면 return을 주어서
줄바꿈을 주고 그렇지않으면 textarea기본 이벤트인 엔터값을 막고 onclick 호출!

> textarea 는 엔터가 브라우저에서 기본적으로 허용되고 그거에 이벤트리스너를 할당한거니까 기본이벤트+리벤트리스너가 동시에 발생하여
> 엔터값이 전송되어도 줄바꿈이 이루어지는거였당. 흙흙
