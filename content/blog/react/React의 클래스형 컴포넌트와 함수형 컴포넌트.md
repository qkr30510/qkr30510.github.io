---
title: 'React의 클래스형 컴포넌트와 함수형 컴포넌트'
date: 2020-3-23 13:07:13
category: 'react'
draft: false
---

요즘 인기있는 프레임워크 중 하나인 **React**에 대해서 공부 하는 중이다.<br/>
공부를 하면서 중간중간 복습할 겸 정리를 하려고 한다.<br/>
오늘은 가장 기본적인 React의 클래스형 컴포넌트와 함수형 컴포넌트의 차이점과 기본적인 작성법에 대해 작성하겠다.<br/>

### React의 클래스형 컴포넌트와 함수형 컴포넌트의 차이

---

react에는 **클래스형**과 **함수형** 두가지의 버전이 있고 두개의 차이는 아래와 같다.

1. 클래스형

   - render 함수가 있어야한다.
   - state 기능 및 라이프 사이클 기능을 사용할 수가 있다.
   - 임의 메서드를 정의할 수 있다.

2. 함수형
   - 클래스형 컴포넌트보다는 선언하기 쉽다.
   - 메모리 자원도 클래스형 컴포넌트보다 덜 사용한다.
   - HOOK을 사용하여 state와 라이프사이클 API의 사용을 대체하여야한다.

### React의 클래스형 컴포넌트와 함수형 컴포넌트의 작성법

---

1. 클래스형 컴포넌트 작성법

```javascript
import React, { Component } from 'react'

class App extends Component {
  render() {
    const name = 'react'
    return <div className="react">{name}</div>
  }
}

export default App
```

2. 함수형 컴포넌트 작성법

```javascript
import React, from 'react';

function App(){
    const name = 'react'
    return <div className="react">{name}</div>
  }
}

export default App
```
