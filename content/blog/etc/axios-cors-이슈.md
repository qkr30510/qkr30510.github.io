---
title: axios CORS 이슈
date: 2020-08-19 16:08:92
category: etc
draft: false
---

### CORS 이란?

CORS는 Cross Origin Resource Sharing의 약자로 도메인 또는 포트가 다른 서버의 자원을 요청하는 매커니즘을 말합니다.

자주 이슈되는 부분은 **동일 출처 정책(same-origin policy) 때문에 CORS 같은 상황이 발생 하면 외부서버에 요청한 데이터를 브라우저에서 보안목적으로 차단합니다. 그로 인해 정상적으로 데이터를 받을 수 없다는 것이다.**

해결방법으로는 cors, proxy등이 있는것 같은데, 나는 좀 더 상세하게 설명이 되어있는 proxy를 이용하여 문제를 해결하였다.

### 해결과정

```javascript
package.json
{
    "proxy":"http://xxx.com"
}
```

```javascript

API 불러오는 곳.js(원본)

import React, { useState, useEffect } from 'react';
import './App.css';
import axios from 'axios'

import WellstoryMenuApp from './component/WellstoryMenuApp'

const App = () => {
  const URL = 'https://snowdeer.com/menu/getMenuList.do?type=2'

  const [data, setData] = useState(null)
  const [loading, setLoading] = useState(false)

  useEffect(() => {
    const fetchData = async () => {
      setLoading(true)

      try {
        const response = await axios.get(URL, )
        console.log(response)
      }
      catch (e) {
        console.log(e)
      }
      setLoading(false)
    }

    fetchData()
  }, [])

  return (
    <div>
      Hello
    </div>
  )

}

export default App;

API 불러오는 곳.js(변경될 부분)

const App = () => {
  const URL = '/menu/getMenuList.do?type=2'
}

```

출처:https://snowdeer.github.io/openshift/2020/06/13/react-for-cors-using-proxy/
