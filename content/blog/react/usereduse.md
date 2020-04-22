---
title: useReduse.md
date: 2020-04-21 17:04:59
category: react
draft: false
---

### 기존 코드

```javascript
import React, { useState } from 'react'

function Counter() {
  const [number, setNumber] = useState(0)

  const onIncrease = () => {
    setNumber(prevNumber => prevNumber + 1)
  }

  const onDecrease = () => {
    setNumber(prevNumber => prevNumber - 1)
  }

  return (
    <div>
      <h1>{number}</h1>
      <button onClick={onIncrease}>+1</button>
      <button onClick={onDecrease}>-1</button>
    </div>
  )
}
export default Counter
```
