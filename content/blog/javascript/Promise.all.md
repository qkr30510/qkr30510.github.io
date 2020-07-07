---
title: Promise.all
date: 2020-07-07 00:07:77
category: javascript
draft: false
---

### Promise.all

메서드는 순회 가능한 객체에 주어진 모든 프로미스가 이행한 후, 혹은 프로미스가 주어지지 않았을 때 이행하는 Promise를 반환합니다. 주어진 프로미스 중 하나가 거부하는 경우, 첫 번째로 거절한 프로미스의 이유를 사용해 자신도 거부합니다.

### 예)

```javascript
const timer = a => {
  return new Promise(res =>
    setTimeout(() => {
      res(a)
    }, Math.random() * 100)
  )
}

const all = Promise.all([timer('first'), timer('second')]).then(data =>
  console.log(data)
)

// 결과 -> ['first','second']
```

### 이유

Math.random을 사용하긴 했지만, Proise.all 을 사용했기때문에 배열 인수에 제공된 순서와 동일한 순서로 반환되도록 신뢰할 수 있다.
