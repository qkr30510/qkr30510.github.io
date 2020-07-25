---
title: Sort
date: 2020-07-06 17:07:13
category: javascript
draft: false
---

알파벳 순서로 정렬하고 숫자의 경우 묵시적으로 문자열로 형변환 하기 때문에 숫자 1이 숫자 10보다 먼저 나온다.

```javascript
const months = ['March', 'Jan', 'Feb', 'Dec']
months.sort()
console.log(months)
// expected output: Array ["Dec", "Feb", "Jan", "March"]

const array1 = [1, 30, 4, 21, 100000]
array1.sort()
console.log(array1)
// expected output: Array [1, 100000, 21, 30, 4]

const numbers = [20, 10, 9, 8, 7, 6, 5, 4, 3, 2, 1]
numbers.sort() // [1,10,2,20,3,4,5,6,7,8,9], 암시적으로 원소를 문자로 형변환 하기 때문에 10이 1뒤에 온다.
```

### sort를 이용한 문제

```javascript
const arr1 = ['a', 'b', 'c']
const arr2 = ['b', 'c', 'a']

console.log(
  arr1.sort() === arr1, /// true
  arr2.sort() === arr2, /// true
  arr1.sort() === arr2.sort() /// false
)
```

**객체를 비교할때 배열의 정렬 순서는 중요하지않다.**

1. arr1.sort() === arr1, /// true
   같은 객체, 최초의 평등 테스트 반환이 같아 `true`
2. arr2.sort() === arr2, /// true
   같은 객체, 최초의 평등 테스트 반환이 같아 `true`
3. arr1.sort() === arr2.sort() /// false
   메모리의 다른 객체를 가리키기때문에 `false`
