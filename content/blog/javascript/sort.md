---
title: sort
date: 2020-07-06 17:07:13
category: javascript
draft: false
---

### sort 메서드

- 원래의 배열을 정리하고 해당 배열에 대한 참조를 반환

### 예)

```javascript
const arr1 = ['a', 'b', 'c']
const arr2 = ['b', 'c', 'a']

console.log(
  arr1.sort() === arr1, /// true
  arr2.sort() === arr2, /// true
  arr1.sort() === arr2.sort() /// false
)
```

### 이유

**객체를 비교할때 배열의 정렬 순서는 중요하지않다.**

1. arr1.sort() === arr1, /// true
   - 같은 객체, 최초의 평등 테스트 반환이 같아 `true`
2. arr2.sort() === arr2, /// true

   - 같은 객체, 최초의 평등 테스트 반환이 같아 `true`

3. arr1.sort() === arr2.sort() /// false
   - 메모리의 다른 객체를 가리키기때문에 `false`
