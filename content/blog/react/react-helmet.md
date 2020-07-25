---
title: React-helmet
date: 2020-06-29 16:06:41
category: react
draft: false
---

react에서 검색엔진 최적화를 하려면 `next.js`를 이용하거나 `react-helmet` 을 구현해야한다.<br>
이번엔 react-helmet을 이용하여 사이트를 제작해보았다.

### 기본 설치 방법

1. react-helmet 패키지를 설치한다.
   `yarn add react-helmet`
2. root파일에(App.js)에 helmet을 import하고 helmet으로 감싸는 태그를 만든다.

```javascript
// App.js
import React from 'react'
import { Helmet } from 'react-helmet'

export default function App() {
  return (
    <div className="App">
      <Helmet>
        <title>원하는 타이틀명</title>
        <meta name="description" content="" />
      </Helmet>
      본문
    </div>
  )
}
```

### 페이지별로 title이 다르고 싶다면,

1. react-router-dom 설치
   `yarn add react-router-dom`
2. index.js 수정

```javascript
// index.js
import React from 'react'
import ReactDOM from 'react-dom'
import App from './App'
import * as serviceWorker from './serviceWorker'
import { BrowserRouter } from 'react-router-dom'

ReactDOM.render(
  <BrowserRouter>
    <React.StrictMode>
      <App />
    </React.StrictMode>
  </BrowserRouter>,
  document.getElementById('root')
)

// If you want your app to work offline and load faster, you can change
// unregister() to register() below. Note this comes with some pitfalls.
// Learn more about service workers: https://bit.ly/CRA-PWA
serviceWorker.unregister()
```

2. TestA 생성

```javascript
// pages/TestA.js
import React from 'react'
import { Helmet } from 'react-helmet'

export default function TestA() {
  return (
    <>
      <Helmet>
        <title>테스트 - A</title>
      </Helmet>
      본문
    </>
  )
}
```

3. TestB 생성

```javascript
// pages/TestB.js
import React from 'react'
import { Helmet } from 'react-helmet'

export default function TestA() {
  return (
    <>
      <Helmet>
        <title>테스트 - B</title>
      </Helmet>
      테스트 페이지 B
    </>
  )
}
```

4. TestRouter 생성

```javascript
// components/TestRouter.js
import React from 'react'
import { Switch, Route, Redirect } from 'react-router-dom'
import TestA from '../pages/TestA'
import TestB from '../pages/TestB'

export default function TestRouter() {
  return (
    <Switch>
      <Route path="/test-A" exact="true" component={TestA} />
      <Route path="/test-B" exact="true" component={TestB} />
      <Redirect to="/test-A" />
    </Switch>
  )
}
```

5. App.js 수정

```javascript
// App.js
import React from 'react'
import { Helmet } from 'react-helmet'
import TestRouter from './components/TestRouter'
import { Link } from 'react-router-dom'

export default function App() {
  return (
    <div className="App">
      <Helmet>
        <title>리액트 헬멧을 이용한 타이틀 변경</title>
      </Helmet>
      Test 헬멧
      <div>
        <Link to="/test-A">페이지 A</Link>
        <br />
        <Link to="/test-B">페이지 B</Link>
      </div>
      <hr />
      <TestRouter />
    </div>
  )
}
```

<a class="source_link" href='https://velog.io/@byseop/SPA%EC%97%90%EC%84%9C-%EC%84%9C%EB%B2%84%EC%82%AC%EC%9D%B4%EB%93%9C-%EB%A0%8C%EB%8D%94%EB%A7%81%EC%9D%84-%EA%B5%AC%EC%B6%95%ED%95%98%EC%A7%80-%EC%95%8A%EA%B3%A0-SEO-%EC%B5%9C%EC%A0%81%ED%99%94%ED%95%98%EA%B8%B0' target="_blank">
참고사이트
</a>
