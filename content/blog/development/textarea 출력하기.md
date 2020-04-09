---
title: 'textarea 출력하기'
date: 2020-04-09 14:10:13
category: 'react'
draft: false
---

textarea를 통해 만들어야하는 값은 만들었는데, 출력하니 새로운 문제가 나타났다 ㅜㅜ
줄바꿈하고 전송하면 그대로 출력될줄알았는데.. 그렇게 될리가 없지.. 후후
구글링을 통해 replace함수를 통해 간단히 해결이 가능하다고 하여 구현해 보았다.

```javascript
    const value = document.getElemtById(textarea).value;
    const fValue = value.replace(/\n/,'<br/>');
    })

```

#### 오류는 다음과 같이 일어났다.

1. 출력에 `<br/>`값이 그대로 노출되었다.

##### 해결

1. 다시 한번 구글링 해보니 벨로퍼트님께서 해결책을 제시해두셨다. <br>
   리액트를 사용하면서 자주쓰는 map함수를 사용하면 되는것이였다 ㅜㅜ
   > 하.. 진ㅉㅏ 이럴때마다 느끼는거지만 개발은 진짜 생각의 전환이 정말정말 중요한것 같다.
   > 나처럼 약간 꽉 막힌애는? 창의성 기르는 연습부터 해야겠다. ~

```javascript
const fValue = value.split('\n').map(line => {
  return (
    <span>
      {line}
      <br />
    </span>
  )
})
```
