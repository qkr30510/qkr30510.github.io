---
title: scroll event
date: 2020-06-11 15:06:12
category: react
draft: false
---

이력서에 이미지부분을 감싸고 있는 div에 `overflow-y:hidden` 으로 감싸고

```css
&::-webkit-scrollbar {
  display: none; /* Chrome, Safari, Opera*/
}
```

을 주었더니 보기엔 좋은데 스크롤이 되는지 파악이 안되었다.

그래서 그 부분에 Icon을 새롭게 넣어 아래에 뭐가 더 있음을 알려주고 스크롤이 될때 Icon을 지우고자 하였다.

### 간편하게 window.scroll 값 알아내기

#### 클래스 컴포넌트

```javascript
class ScrollAwareDiv extends React.Component {
  constructor(props) {
    super(props)
    this.myRef = React.createRef()
    this.state = { scrollTop: 0 }
  }

  onScroll = () => {
    const scrollTop = this.myRef.current.scrollTop
    console.log(`myRef.scrollTop: ${scrollTop}`)
    this.setState({
      scrollTop: scrollTop,
    })
  }

  render() {
    const { scrollTop } = this.state
    return (
      <div
        ref={this.myRef}
        onScroll={this.onScroll}
        style={{
          border: '1px solid black',
          width: '600px',
          height: '100px',
          overflow: 'scroll',
        }}
      >
        <p>
          This demonstrates how to get the scrollTop position within a
          scrollable react component.
        </p>
        <p>ScrollTop is {scrollTop}</p>
      </div>
    )
  }
}
```

#### 함수형 컴포넌트

```javascript
import React, { useEffect, useState } from 'react'

function MyApp() {
  const [offset, setOffset] = useState(0)

  useEffect(() => {
    window.onscroll = () => {
      setOffset(window.pageYOffset)
    }
  }, [])

  console.log(offset)
}
```

### 특정 내부 값의 scroll 값 알아내기

내가 필요한건 window값이 아니기에 ref를 사용하여 감지해야할꺼같다.

### 클래스형

```javascript
class ScrollAwareDiv extends React.Component {
  constructor(props) {
    super(props)
    this.myRef = React.createRef()
    this.state = { scrollTop: 0 }
  }

  onScroll = () => {
    const scrollY = window.scrollY //Don't get confused by what's scrolling - It's not the window
    const scrollTop = this.myRef.current.scrollTop
    console.log(
      `onScroll, window.scrollY: ${scrollY} myRef.scrollTop: ${scrollTop}`
    )
    this.setState({
      scrollTop: scrollTop,
    })
  }

  render() {
    const { scrollTop } = this.state
    return (
      <div
        ref={this.myRef}
        onScroll={this.onScroll}
        style={{
          border: '1px solid black',
          width: '600px',
          height: '100px',
          overflow: 'scroll',
        }}
      >
        <p>
          This demonstrates how to get the scrollTop position within a
          scrollable react component.
        </p>
        <p>ScrollTop is {scrollTop}</p>
        <p>
          This demonstrates how to get the scrollTop position within a
          scrollable react component.
        </p>
        <p>ScrollTop is {scrollTop}</p>
        <p>
          This demonstrates how to get the scrollTop position within a
          scrollable react component.
        </p>
        <p>ScrollTop is {scrollTop}</p>
        <p>
          This demonstrates how to get the scrollTop position within a
          scrollable react component.
        </p>
        <p>ScrollTop is {scrollTop}</p>
        <p>
          This demonstrates how to get the scrollTop position within a
          scrollable react component.
        </p>
        <p>ScrollTop is {scrollTop}</p>
        <p>
          This demonstrates how to get the scrollTop position within a
          scrollable react component.
        </p>
        <p>ScrollTop is {scrollTop}</p>
      </div>
    )
  }
}

ReactDOM.render(<ScrollAwareDiv />, document.getElementById('root'))
```

### 함수형

```javascript
```
