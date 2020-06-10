---
title: 아토믹 디자인 패턴(props 전달)
date: 2020-06-10 13:06:23
category: react
draft: false
---

### 편하게 더치페이 제작
이전 회사 'O' 를 다니면서 직장 동료들과 술 한잔씩 기울이는 일이 많았었는데, 계산하기가 참 애매모호하였다. 야근이 많은 회사였기에 2차에 합류한사람 또 술 안드시는 분들의 계산등등
계산하기 너무 복잡해서 우리는 늘 엑셀을 이용하여 금액을 n분의1을 하곤했다. 
다음날 회사에 간다면 간김에 엑셀 켜서 계산해도 되었지만, 휴무날 만났다면 이걸 위해 컴퓨터를 키고 
엑셀을 켜야하는 번거로움이 있었다. 
그래서 좀 더 나의 친구들(이젠 난 퇴사했으니까)이 집에서 누워서도 계산할 수 있게 이 프로젝트를 기획하게 되었다.

### 컴포넌트 나누다보니 아토믹 디자인 패턴
리액트의 가장 강점은 컴포넌트의 재사용성이고, 이 프로젝트의 경우 input과 span창이 반복되어 따로 컴포넌트를 빼서 map함수로 반복해주었다.
input을 map함수로 반복하다보니 각각의 onChange와 value값을 부여해야했고 난 이 과정조차 번거롭다고 느껴졌다. 
그래서 input 부분을 다시 컴포넌트로 빼서 그곳에서 onChange와 value값을 주었다. 
즉, 현재 내 컴포넌트는 `부모 -Wrap.js(Div가 담겨져있음.) ,자식-Div.js(span과 input map으로 반복) ,손자- Input.js(input만 있음)` 이런식으로 세분화가(아토믹 디자인 패턴) 되었다.

> 아토믹 디자인 패턴이란, 디자인 요소들을 나누어 파악하고 이 요소들이 조합되는 과정을 통해서 디자인을 구성하는 방식을 의미한다. (즉, 컴포넌트 중심의 디자인 패턴인 것)

>Atoms: 하나의 구성 요소. 본인 자체의 스타일만 가지고 있으며 다른 곳에 영향을 미치는 스타일은 적용되지 않아야 함.
Molecules: 원자들의 모음
Organisms: 분자들의 모음
Templates: 유기체들을 모아 템플릿으로 생성
Pages: 실제 페이지를 구성
<a class="source_link" href="https://tech.madup.com/atomic-design/" target="_blank">출처</a>

***Wrap.js***
```javascript

import React from 'react';
import Div from './Div';


const Wrap = () => {
  
  return (
    <>
        <Div />
    </>
  );
};
export default Wrap;

```

***Div.js***
```javascript

import React, { useCallback, useState } from 'react';
import styled from 'styled-components';
import Input from './Input';

const Div = () => {
  const InputBox = [
    {
      id: 1,
      title: '전체인원',
    },
    {
      id: 2,
      title: '술 먹은 인원',
    },
    {
      id: 3,
      title: '음료 먹은 인원',
    },
    {
      id: 4,
      title: '술과 음료를 먹은 인원',
    },
  ];


  let InputBoxs = InputBox.map((InputBoxLi, index) => (
    <div key={index}>
      <span>{InputBoxLi.id}</span>
      <span>{InputBoxLi.title}</span>
      <Input/>
    </div>
  ));


  return (
    <>
      <div>{InputBoxs}</div>
    </>
  );
};

export default Div;


```
***Input.js***
```javascript

import React, { useCallback, useState } from 'react';


const Input = () => {

  const [state, setState] = useState();
  
  const onChange = useCallback(
    (e) => {
      setState(e.target.value);
    },
    [setState],
  );



  return (
    <>
      <input type="text" value={state} onChange={onChange} />
    </>
  );
};

export default Input;


```

### props 전달 방법 

내가 만든 레이아웃은 **`부모 -> 자식 -> 손자`가 있고, 손자의 value값이 부모까지 와야했다.**  
useContext를 사용한다면 조금 더 편리하게 값을 가져왔겠지만, 나는 그냥 땡겨오기로 했다. 
리액트는 단방향 데이터 흐름을 지향하기 때문에 부모에서 state 값과 onChange 이벤트를 주고 그 state값을 자식과 손자에게 내려주었다.

***Wrap.js***
```javascript

import React from 'react';
import Div from './Div';


const Wrap = () => {
  const [state, setState] = useState();
  
  const onChange = useCallback(
    (e) => {
      setState(e.target.value);
    },
    [setState],
  );

  return (
    <>
        <Div value={state} onChange={onChange} />
    </>
  );
};
export default Wrap;

```

***Div.js***
```javascript

import React, { useCallback, useState } from 'react';
import styled from 'styled-components';
import Input from './Input';

const Div = ({onChange,state }) => {
  const InputBox = [
    {
      id: 1,
      title: '전체인원',
    },
    {
      id: 2,
      title: '술 먹은 인원',
    },
    {
      id: 3,
      title: '음료 먹은 인원',
    },
    {
      id: 4,
      title: '술과 음료를 먹은 인원',
    },
  ];


  let InputBoxs = InputBox.map((InputBoxLi, index) => (
    <div key={index}>
      <span>{InputBoxLi.id}</span>
      <span>{InputBoxLi.title}</span>
      <Input value={state}   onChange={onChange}/>
    </div>
  ));


  return (
    <>
      <div>{InputBoxs}</div>
    </>
  );
};

export default Div;


```
***Input.js***
```javascript

import React, { useCallback, useState } from 'react';


const Input = ({onChange,state }) => {



  return (
    <>
      <input type="text" value={state} onChange={onChange}  />
    </>
  );
};

export default Input;


```

그리고 제대로 데이터가 들어왔는지 확인하기 위해 `Wrap.js`에서 `  console.log('값이 오나', state)`
를 찍어보았다.

