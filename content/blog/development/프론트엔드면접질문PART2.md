---
title: '프론트앤드면접질문PART2'
date: 2020-04-08 14:10:13
category: 'etc'
draft: false
---

### React의 특징은 어떤 것들이 있나

1. UI 컴포넌트를 만들기 위한 라이브러리이며 React의 컴포넌트는 트리형태로 구성된다.
2. Virtual DOM을 사용하여 변경된 부분에 대한 최소한의 DOM 처리로 UI를 업데이트하여 애플리케이션의 성능을 향상한다.
3. 부모 컴포넌트에서 하위 컴포넌트로 전달하는 단방향의 단순한 데이터 흐름을 갖고 있어 데이터 추적과 디버깅을 쉽게 해준다.
4. JSX(Javascript XML) 사용

<a class="source_link" href="https://meetup.toast.com/posts/100" target="_blank">출처</a>

<br>

---

### JSX란 무엇인가요. JSX의 문법을 코드를 통해 설명하시오

JSX는 함수 호출과 객체 생성을 위한 문법적 편의를 제공하는 자바스크립트의 확장으로, 특히 React.createElement() 호출을 반복해야 하는 불편을 해소한다. 템플릿 엔진이나 HTML처럼 보일 수도 있지만 그렇지 않다. JSX는 React 엘리먼트를 생성하면서 자바스크립트의 모든 기능을 쓸 수 있도록 도와준다.

```javascript
var HelloReact = React.createClass({
  render: function() {
    return (
      <p>
        <span>Hello</span>
        <span>{this.props.message}</span>
      </p>
    )
  },
})

ReactDOM.render(
  <HelloReact message="React" />,
  document.getElementById('container')
)
```

<a class="source_link" href="https://thebook.io/006961/part01/ch03/01/" target="_blank">출처</a>
<a class="source_link" href="https://meetup.toast.com/posts/100" target="_blank">출처</a>
<br>

---

### 리액트에서 컴포넌트를 어떻게 생성하나요. 코드를 통해 설명하시오

1. Js(jsx)파일을 만든다
2. - 함수형 컴포넌트

   ```javascript
   import React from 'react'

   const code = () => {
     return <div>hello</div>
   }

   export default code
   ```

   1. import 로 react 모듈을 가져옴.
   2. 원하는 이름으로 변수를 만들어 주고 그 안에 익명함수를 생성한다.( return 문을 통해 원하는 화면을 렌더링할 수 있음)
   3. Export로 컴포넌트를 내보낸다.(다른 코드에서도 사용할 수 있게)

3. - 클래스 형 컴포넌트

   ```javascript
   import React from 'react'

   class code extends Component {
     render() {
       return <div>Hello</div>
     }
   }

   export default code
   ```

   1. import 로 react 모듈을 가져옴.
   2. 원하는 이름으로 클래스를 만들어 주고 render 함수를 생성한다. (클래스형 컴포넌트에서는 render 함수에서 화면을 렌더링 함)
   3. Export로 컴포넌트를 내보낸다.(다른 코드에서도 사용할 수 있게)

<br>
<a class="source_link" href="https://ko.reactjs.org/docs/introducing-jsx.html" target="_blank">출처</a>   
<br>
---

### STATE란 무엇인가요. 코드를 통해 설명하시오

컴포넌트에서 필요한 동적 데이터, 사용자에 의해 변경되는 것을 관리할 때 사용하거나 상태를 저장해야할 때 사용하고, 컴포넌트 내에서 변경된다. 변경할 때는 반드시 setState()를 사용해야한다.

```javascript
class App extends Component {
  constructor() {
    super()
    this.state = {
      score: 0,
    }
  }

  plusscore() {
    this.setState((prevState, props) => {
      return { score: prevState.score + 1 }
    })
  }

  render() {
    return (
      <button onClick={() => this.plusscore()}>
        Score : {this.state.score}
      </button>
    )
  }
}
```

---

### PROPS란 무엇인가요. 코드를 통해 설명하시오

컴포넌트에서 필요한 정적 데이터, 변하지 않는 값으로 사용한다. 컴포넌트 내에서 변경해선 안된다.

```javascript
import React, { Component } from 'react'
import PropTypes from 'prop-types'
import logo from './logo.svg'
import './App.css'

class App extends Component {
  render() {
    return (
      <div className="App">
        <header className="App-header">
          <img src={logo} className="App-logo" alt="logo" />
          <h1 className="App-title">Welcome to React</h1>
        </header>
        <p className="App-intro">
          <div>
            이름은 {this.props.name} 이고, 나이는 {this.props.age} 입니다.
          </div>
        </p>
      </div>
    )
  }
}

App.PropTypes = {
  name: PropTypes.string,
  age: PropTypes.number.isRequired,
}
App.defaultProps = {
  name: '정프로',
}
export default App
```

<br>
<a class="source_link" href="https://jeong-pro.tistory.com/77" target="_blank">출처</a>   
<br>
