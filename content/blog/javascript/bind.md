---
title: bind
date: 2020-07-07 14:07:79
category: javascript
draft: false
---

메소드가 호출되면 새로운 함수를 생성합니다. 받게되는 첫 인자의 value로는 `this` 키워드를 설정하고,
이어지는 인자들은 바인드된 함수의 인수에 제공됩니다.

```javascript
const module = {
  x: 42,
  getX: function() {
    return this.x
  },
}

const unboundGetX = module.getX
console.log(unboundGetX()) // the function gets invoked at the global scope
// expected output: undefined

const boundGetX = unboundGetX.bind(module)
//expected output: 42
```
