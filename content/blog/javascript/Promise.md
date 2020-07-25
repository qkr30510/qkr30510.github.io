---
title: Promise
date: 2020-07-07 00:07:77
category: javascript
draft: false
---

<span class='strong'>자바스크립트 비동기 처리에 사용되는 객체입니다.</span> 여기서 자바스크립트의 비동기 처리란 ‘특정 코드의 실행이 완료될 때까지 기다리지 않고 다음 코드를 먼저 수행하는 자바스크립트의 특성’을 의미합니다. <br><br>

**쉽게 설명하면 데이터를 받아오기 전에 마치 데이터를 다 받아온 것 마냥 화면에 데이터를 표시하려고 하면 오류가 발생하거나 빈 화면이 뜹니다. 그 문제점을 해결하기위해 사용합니다.**

```javascript
function getData(callback) {
  // new Promise() 추가
  return new Promise(function(resolve, reject) {
    $.get('url 주소/products/1', function(response) {
      // 데이터를 받으면 resolve() 호출
      resolve(response)
    })
  })
}

// getData()의 실행이 끝나면 호출되는 then()
getData().then(function(tableData) {
  // resolve()의 결과 값이 여기로 전달됨
  console.log(tableData) // $.get()의 reponse 값이 tableData에 전달됨
})
```

## Promise.all

순회 가능한 객체에 주어진 모든 프로미스가 이행한 후, 혹은 프로미스가 주어지지 않았을 때 이행하는 Promise를 반환합니다. 주어진 프로미스 중 하나가 거부하는 경우, 첫 번째로 거절한 프로미스의 이유를 사용해 자신도 거부합니다.
어떤 비동기 작업들을 다 끝내고 나서 다음 작업으로 넘어갈 때 유용합니다.

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

Math.random을 사용하긴 했지만, Proise.all 을 사용했기때문에 배열 인수에 제공된 순서와 동일한 순서로 반환되도록 신뢰할 수 있다.
