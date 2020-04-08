---
title: 'props와 state'
date: 2020-4-03 18:15:13
category: 'react'
draft: false
---

리액트를 공부하다보면 다루는 데이터는 두개다. 바로 오늘의 주제인 **props**와 **state**다. <br>
*props*는 부모쪽에 있고 *state*는 자식쪽에 있는데, *props*는 내용이 안바뀌고 *state*는 내용이 변경된다. <br>
<br>
예시코드를 통해 한가지씩 차례대로 보도록 하자.

---

### 1. props

App.js

```javascript
import React, { Component } from 'react;'
import PropsSample from './PropsSample'

class App extends Componets {
  render() {
    return <div>name</div>
  }
}

export default App
```

PropsSample.js

```javascript
import React, { Component } from 'react;'

class PropsSample extends Componets {
  render() {
    return <div>이건 props{this.props.name}이야!</div>
  }
}

export default PropsSample
```

---

### 2. state

App.js

```javascript

import React, from 'react;'
import PropsSample from './PropsSample'

const App = () => {
    <div><PropsSample name="sample"/></div>
}

export default App;
```

PropsSample.js

```javascript
import React, from 'react;'

const PropsSample = () => {
    <div>이건 props{this.props.name}이야!</div>
}

export default PropsSample;
```
