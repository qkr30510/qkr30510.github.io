---
title: Cannot read property 'getBoundingClientRect' of null
date: 2020-07-25 15:07:69
category: javascript
draft: false
---

getBoundingClientRect을 사용해서 스크롤 이벤트를 주고싶었는데, `Cannot read property 'getBoundingClientRect' of null`라는 오류가 종종 나와서 이거 해결방법에 대해 작성하고 싶었다.

```javascript
const navigator = document.querySelector('#navigator')
// Uncaught TypeError: Cannot read property 'getBoundingClientRect' of null
if (!navigator) {
  return
}

const height = navigator.getBoundingClientRect().bottom
```
