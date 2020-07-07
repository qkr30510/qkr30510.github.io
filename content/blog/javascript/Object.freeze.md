---
title: object
date: 2020-07-07 00:07:19
category: javascript
draft: false
---

### Object.freeze

object.freeze 메서드는 객체를 동결합니다.
즉 **동결된 객체는 새로운 속성을 추가하거나 존재하는 속성을 제거하는 것을 방지하며 존재하는 속성의 불변성, 설정가능성, 작성 가능성이 변경되는 것을 방지하고, 존재하는 속성의 값이 변경되는 것도 방지합니다.**

### 예)

```javascript
const user = {
  name: 'Joe',
  age: 25,
  pet: {
    type: 'dog',
    name: 'Buttercup',
  },
}

Object.freeze(user)

user.pet.name = 'Daffodil'

console.log(user.pet.name) // Buttercup
```

### 이유

**freeze 메서드를 사용했기때문에 변경이 불가능하다.**
만약, `freeze`를 사용하지않았다고 해도 `user.pet.name`은 깊은 복사기때문에 변경되지않는다.
`user.age`는 변경이 가능하다.
