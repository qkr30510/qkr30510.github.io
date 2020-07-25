---
title: reduce
date: 2020-07-07 01:07:13
category: javascript
draft: false
---

reduce() 메서드는 배열의 각 요소에 대해 주어진 리듀서(reducer)함수를 실행하고, 하나의 결과값을 반환합니다.

리듀서 함수는 네 개의 인자를 가집니다.

1. 누산기 acccumulator (acc)
2. 현재 값 (cur)
3. 현재 인덱스 (idx)
4. 원본 배열 (src)

<p class='strong'>리듀서 함수의 반환 값은 누산기에 할당되고, 누산기는 순회 중 유지되므로 결국 최종 결과는 하나의 값이 됩니다.</p>

```javascript
const array1 = [1, 2, 3, 4]
const reducer = (accumulator, currentValue) => accmulator + currentValue

// 1+2+3+4
console.log(array1, reduce(reducer))
//expected output: 10

// 5+1+2+3+4
console.log(array1.reduce(reducer, 5))
//expected output: 15
```

### reduce를 이용한 문제

```javascript
const arr = [x => x * 1, x => x * 2, x => x * 3, x => x * 4]

console.log(arr.reduce((agg, el) => agg + el(agg), 1)) // 120
```

누적값 + 누적값 \* 1
이 배열의 초기값은 1이다. 즉, 첫번째 배열의 x는 1
x = 1

1 + (1*1) = 2
2 + (2*2) = 6
6 + (6*3) = 24
24 + (24*4) = 120
