---
title: 프론트엔드면접질문PART4
date: 2020-04-18 16:04:80
category: etc
draft: false
---

### 1. FLEX레이아웃과 GRID 레이아웃을 설명하고 예제를 만드시오.

**flexbox**는 뷰포트나 요소의 크기가 불명확하거나 동적으로 변할 때에도 효율적으로 요소를 배치, 정렬, 분산할 수 있는 방법을 제공하는 CSS3의 새로운 레이아웃 방식입니다. flexbox의 장점을 한 마디로 표현하면 '복잡한 계산 없이 요소의 크기와 순서를 유연하게 배치할 수 있다'라고 할 수 있다. 정렬, 방향, 순서, 크기 등을 유연하게 조절할 수 있기 때문에 별도의 분기 처리를 줄일 수 있고, CSS만으로 다양한 레이아웃을 구현할 수 있습니다.

```html
<!DOCTYPE html>
<html lang="ko">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>flex</title>
    <style>
      /* option */
      .flex {
        background-color: #f7f7f7;
        border-radius: 3px;
        padding: 20px;
        counter-reset: items;
      }
      .item {
        border-radius: 3px;
        background-color: #a2cbfa;
        border: 1px solid #4390e1;
        box-sizing: border-box;
        box-shadow: 0 2px 2px rgba(0, 90, 250, 0.05), 0 4px 4px rgba(0, 90, 250, 0.05),
          0 8px 8px rgba(0, 90, 250, 0.05), 0 16px 16px rgba(0, 90, 250, 0.05);
        min-height: 100px;
        color: #fff;
        padding: 10px;
      }
      .item::before {
        counter-increment: items;
        content: counter(items);
      }
      /* flex */
      .flex1 {
        display: flex;
        border: 1px solid #000;
      }
      .item1 {
        flex-grow: 1;
      }
      .item1 + .item1 {
        margin-left: 2%;
      }

      .flex2 {
        display: flex;
        border: 1px solid #000;
      }
      .item2 {
        flex-grow: 1;
      }
      .item2:nth-child(4) {
        flex-grow: 2;
      }
      .item2 + .item2 {
        margin-left: 2%;
      }

      .flex3 {
        display: flex;
        flex-direction: row-reverse;
        border: 1px solid #000;
      }
      .item3 {
        width: 100px;
        margin-left: 2%;
      }

      .flex4 {
        display: flex;
        border: 1px solid #000;
      }
      .item4 {
        width: 100px;
      }
      .item4 + .item4 {
        margin-left: 2%;
      }
      .item4:last-child {
        margin-left: auto;
      }
      .flex5 {
        display: flex;
        flex-wrap: wrap;
        justify-content: space-between;
        border: 1px solid #000;
      }
      .item5 {
        width: 49%;
        height: 100px;
        margin-bottom: 2%;
      }
      .item5:nth-child(3n) {
        width: 100%;
      }
      .flex6 {
        display: flex;
        flex-wrap: wrap;
        justify-content: space-between;
        border: 1px solid #000;
      }
      .item6 {
        /* flex: 0 32%;  flex-grow / flex-basis */
        flex-basis: 32%;
        height: 100px;
        margin-bottom: 2%;
      }
      .flex7 {
        display: flex;
        flex-wrap: wrap;
        justify-content: space-between;
        border: 1px solid #000;
      }
      .item7 {
        flex-basis: 32%;
        padding-bottom: 30%;
        margin-bottom: 2%;
      }
      .flex8 {
        display: flex;
        justify-content: space-between;
        /* align-items: flex-start;
            align-items: center; */
        align-items: flex-end;
        height: 300px;
        border: 1px solid #000;
      }
      .item8 {
        flex-basis: 10%;
        margin-bottom: 2%;
      }
      .item8:nth-child(1) {
        height: 20%;
      }
      .item8:nth-child(2) {
        height: 40%;
      }
      .item8:nth-child(3) {
        height: 50%;
      }
      .item8:nth-child(4) {
        height: 80%;
      }
      .item8:nth-child(5) {
        height: 40%;
      }
      .item8:nth-child(6) {
        height: 30%;
      }
      .item8:nth-child(7) {
        height: 20%;
      }
      .flex9 {
        display: flex;
        justify-content: space-between;
        flex-direction: column;
        border: 1px solid #000;
      }
      .item9 {
        margin-bottom: 1%;
        height: 14%;
      }
      .item9:nth-child(1) {
        width: 20%;
      }
      .item9:nth-child(2) {
        width: 40%;
      }
      .item9:nth-child(3) {
        width: 50%;
      }
      .item9:nth-child(4) {
        width: 80%;
      }
      .item9:nth-child(5) {
        width: 40%;
      }
      .item9:nth-child(6) {
        width: 30%;
      }
      .item9:nth-child(7) {
        width: 20%;
      }
      .flex10 {
        display: flex;
        flex-flow: column wrap;
        align-content: space-between;
        height: 700px;
        border: 1px solid #000;
      }
      .item10 {
        width: 32%;
        margin-bottom: 2%;
      }
      .flex10::before,
      .flex10::after {
        content: '';
        flex-basis: 100%;
        width: 0;
        order: 2;
        border: 1px solid #ddd;
      }
      .item10:nth-child(1) {
        height: 100px;
      }
      .item10:nth-child(2) {
        height: 200px;
      }
      .item10:nth-child(3) {
        height: 300px;
      }
      .item10:nth-child(4) {
        height: 200px;
      }
      .item10:nth-child(5) {
        height: 200px;
      }
      .item10:nth-child(6) {
        height: 200px;
      }
      .item10:nth-child(7) {
        height: 300px;
      }
      .item10:nth-child(8) {
        height: 200px;
      }
      .item10:nth-child(9) {
        height: 100px;
      }
      .item10:nth-child(3n + 1) {
        order: 1;
      }
      .item10:nth-child(3n + 2) {
        order: 2;
      }
      .item10:nth-child(3n) {
        order: 3;
      }
      .flex11 {
        display: flex;
        flex-flow: column wrap;
        align-content: space-between;
        height: 780px;
        border: 1px solid #000;
      }
      .item11 {
        width: 24%;
        margin-bottom: 1%;
      }
      .item11:nth-of-type(1) {
        height: 100px;
      }
      .item11:nth-of-type(2) {
        height: 200px;
      }
      .item11:nth-of-type(3) {
        height: 300px;
      }
      .item11:nth-of-type(4) {
        height: 200px;
      }
      .item11:nth-of-type(5) {
        height: 200px;
      }
      .item11:nth-of-type(6) {
        height: 200px;
      }
      .item11:nth-of-type(7) {
        height: 200px;
      }
      .item11:nth-of-type(8) {
        height: 100px;
      }
      .item11:nth-of-type(9) {
        height: 100px;
      }
      .item11:nth-of-type(10) {
        height: 100px;
      }
      .item11:nth-of-type(11) {
        height: 100px;
      }
      .item11:nth-of-type(12) {
        height: 300px;
      }
      .item11:nth-of-type(13) {
        height: 300px;
      }
      .item11:nth-of-type(14) {
        height: 200px;
      }
      .item11:nth-of-type(4n + 1) {
        order: 1;
      }
      .item11:nth-of-type(4n + 2) {
        order: 2;
      }
      .item11:nth-of-type(4n + 3) {
        order: 3;
      }
      .item11:nth-of-type(4n) {
        order: 4;
      }

      .item11.break {
        flex-basis: 100%;
        width: 0;
        border: 1px solid #ddd;
        margin: 0;
        content: '';
        padding: 0;
        font-size: 0;
      }
      .flex12 {
        display: flex;
        flex-flow: row wrap;
        justify-content: space-between;
        border: 1px solid #000;
      }
      .item12 {
        margin-bottom: 2%;
      }
      .item12:nth-child(1) {
        /* flex-grow / flex-shrink / flex-basis : auto */
        flex: 1 100%;
      }
      .item12:nth-child(2) {
        flex: 1 0 0;
      }
      .item12:nth-child(3) {
        flex: 3 0 0;
        margin-left: 2%;
      }
      .item12:nth-child(4) {
        flex: 1 0 0;
        margin-left: 2%;
      }
      .item12:nth-child(5) {
        flex: 1 100%;
      }
      /* mediaquery */
      @media (max-width: 600px) {
        .item12:nth-child(3) {
          flex: 1 0 100%;
          margin-left: 0;
        }
        .item12:nth-child(4) {
          margin-left: 0;
        }
      }
    </style>
  </head>
  <body>
    <div class="flex flex1 ">
      <div class="item item1"></div>
      <div class="item item1"></div>
      <div class="item item1"></div>
      <div class="item item1"></div>
      <div class="item item1"></div>
      <div class="item item1"></div>
      <div class="item item1"></div>
      <div class="item item1"></div>
    </div>
    <div class="flex flex2">
      <div class="item item2"></div>
      <div class="item item2"></div>
      <div class="item item2"></div>
      <div class="item item2"></div>
      <div class="item item2"></div>
      <div class="item item2"></div>
      <div class="item item2"></div>
      <div class="item item2"></div>
    </div>
    <div class="flex flex3">
      <div class="item item3"></div>
      <div class="item item3"></div>
      <div class="item item3"></div>
      <div class="item item3"></div>
    </div>
    <div class="flex flex4">
      <div class="item item4"></div>
      <div class="item item4"></div>
      <div class="item item4"></div>
      <div class="item item4"></div>
    </div>
    <div class="flex flex5">
      <div class="item item5"></div>
      <div class="item item5"></div>
      <div class="item item5"></div>
      <div class="item item5"></div>
      <div class="item item5"></div>
    </div>
    <div class="flex flex6">
      <div class="item item6"></div>
      <div class="item item6"></div>
      <div class="item item6"></div>
      <div class="item item6"></div>
      <div class="item item6"></div>
      <div class="item item6"></div>
      <div class="item item6"></div>
      <div class="item item6"></div>
      <div class="item item6"></div>
    </div>
    <div class="flex flex7">
      <div class="item item7"></div>
      <div class="item item7"></div>
      <div class="item item7"></div>
      <div class="item item7"></div>
      <div class="item item7"></div>
      <div class="item item7"></div>
      <div class="item item7"></div>
      <div class="item item7"></div>
      <div class="item item7"></div>
    </div>
    <div class="flex flex8">
      <div class="item item8"></div>
      <div class="item item8"></div>
      <div class="item item8"></div>
      <div class="item item8"></div>
      <div class="item item8"></div>
      <div class="item item8"></div>
      <div class="item item8"></div>
    </div>
    <div class="flex flex9">
      <div class="item item9"></div>
      <div class="item item9"></div>
      <div class="item item9"></div>
      <div class="item item9"></div>
      <div class="item item9"></div>
      <div class="item item9"></div>
      <div class="item item9"></div>
    </div>
    <div class="flex flex10">
      <div class="item item10"></div>
      <div class="item item10"></div>
      <div class="item item10"></div>
      <div class="item item10"></div>
      <div class="item item10"></div>
      <div class="item item10"></div>
      <div class="item item10"></div>
      <div class="item item10"></div>
      <div class="item item10"></div>
    </div>
    <div class="flex flex11">
      <div class="item item11"></div>
      <div class="item item11"></div>
      <div class="item item11"></div>
      <div class="item item11"></div>
      <div class="item item11"></div>
      <div class="item item11"></div>
      <div class="item item11"></div>
      <div class="item item11"></div>
      <div class="item item11"></div>
      <div class="item item11"></div>
      <div class="item item11"></div>
      <div class="item item11"></div>
      <div class="item item11"></div>
      <div class="item item11"></div>
      <div class="item item11"></div>
      <div class="item item11"></div>

      <span class="item item11 break"></span>
      <span class="item item11 break"></span>
      <span class="item item11 break"></span>
    </div>
    <div class="flex flex12">
      <div class="item item12"></div>
      <div class="item item12"></div>
      <div class="item item12"></div>
      <div class="item item12"></div>
      <div class="item item12"></div>
    </div>
  </body>
</html>
```

**그리드**는 수평선과 수직선이 교차해서 이루어진 집합체입니다 - 하나의 집합체는 세로 열을 그리고 다른 하나는 가로 행을 정의합니다. 각 요소는 이러한 열과 행으로 된 라인을 따라 생성된 그리드에 배치할 수 있습니다. CSS 그리드 레이아웃에는 다음과 같은 기능이 있습니다

```html
<!DOCTYPE html>
<html lang="ko">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>flex</title>
    <style>
      .wrapper > div {
        background-color: orange;
        border: 1px black solid;
      }

      .wrapper > div:nth-child(odd) {
        background-color: indianred;
      }

      .wrapper {
        display: grid;
        grid-template-columns: 100px 100px 100px;
        grid-template-rows: 50px 50px;
      }
    </style>
  </head>
  <body>
    <div class="wrapper">
      <div class="div1">1</div>
      <div class="div2">2</div>
      <div class="div3">3</div>
      <div class="div4">4</div>
    </div>
  </body>
</html>
```

<a class="source_link" href="https://webzz.tistory.com/655" target="_blank">출처</a>
<a class="source_link" href="https://code.tutsplus.com/ko/tutorials/introduction-to-css-grid-layout-with-examples--cms-25392" target="_blank">출처</a>

---

---

### 2. ES6문법을 10가지이상 설명하고 각 예제를 만드시오.

1. const/let 블록 스코프
   var의 변수스코프는 function단위, const/let은 block 단위, const는 상수, let는 변수

```javascript
function foo() {
  let a = 1
  if (true) {
    let a = 2
    console.log(a) // 2
  }
  console.log(a) // 1
}
```

2. 템플릿 / 백틱

```javascript
document.addEventListener('DOMContentLoaded', () => {
  const you = 'Chris',
    name = 'Charles',
    surname = 'Barkley'
  const tmp = `<p>Hello, ${you}. My name is ${name} ${surname}</p>`
  const el = document.getElementById('el')
  el.insertAdjacentHTML('beforeend', tmp)
})
```

3. 화살표 함수

```javascript
// #1: 일반적인 화살표 함수
let square = num => {
  return num * num
}
console.log(square(4)) // 16

// #2: 화살표 내의 this는 ES5의 function 내의 this와 다름
console.log(this === window) // true
let basket = {
  _name: 'ball',
  _mates: ['rebound', 'shoot', 'pass'],
  matesCount() {
    console.log(this === window) // false
    console.log(this) // basket 객체를 가리킴
    this._mates.forEach(f => console.log(this._name + ' is ' + f))
  },
}
basket.matesCount()

// #3: 화살표 함수의 return 값
const even = [2, 4, 6, 8, 10, 12, 14]
const odd = even.map(n => n + 1)
const num = even.map((n, i) => n + i) // map(crruentValue, index, array)
console.log(even) // [2, 4, 6, 8, 10, 14]
console.log(odd) // [3, 5, 7, 9, 11, 13, 15]
console.log(num) // [2, 5, 8, 11, 14, 17, 20]

// #4: 비구조화 지원
const f = ([a, b] = [1, 2], { x: c } = { x: a + b }) => a + b + c
console.log(f()) //	6
```

3. 클래스
   prototype 기반의 대체재로 쓰임

```javascript
class Shape {
  constructor() {}
}

class Rectangle extends Shape {
  constructor(w, h) {
    super(w, h)
    this.w = 20
    this.h = 10
  }
  getArea(w, h) {
    return w * h
  }
  // get, set, static 예약어로 메서드를 설정할 수 있음
}
let rect = new Rectangle()
console.log(rect.getArea(30, 20)) // 600
```

4. 모듈

```javascript
// js/main.js
export default {
  init() {
    console.log('main.js')
  },
  sum(x, y) {
    return x + y
  },
}
export const PI = 3.14156265

// app.js
import Main from './js/main.js'

document.addEventListener('DOMContentLoaded', () => {
  Main.init()
  console.log(Main.sum(Main.PI * Main.PI))
})

// otherapp.js
import { sum, PI } from './js/main'
console.log('sum: ' + sum(PI, PI))

// index.html
;<script type="module" src="app.js"></script>
```

5. 배열/객체 할당 확장

```javascript
const [a, b, c] = [1, 2, 3]
console.log(a, b, c) // 1, 2, 3

const obj = { x: 'banana', y: 'apple' }
let { x, y, z } = obj
console.log(x, y, z) // x: 'banana', y: 'apple', z: undefined

function f({ name: x }) {
  console.log(x) // x: 8
}
f({ name: 8 })

var [u = 1] = []
console.log(u === 1) // true
```

6. Spread(...) 연산자

```javascript
function sum(x, y = 12) {
  return x + y
}
console.log(sum(4))

function f(x, ...y) {
  return x * y.length
}
console.log(f(3, 'hello', true))

function ff(x, y, z) {
  return x + y + z
}
console.log(ff(...[1, 2, 3]))
```

7. Fetch / Promise / Async-await

```javascript
// fetch
fetch('https://hacker-news.firebaseio.com/v0/item/8863.json')
    .then(response => response.json())
    .then(data => {
        console.log(data)
        console.log(data.title)
    })
    .catch(error => console.log(error))

// promise: pending(대기), fulfilled(이행), reject(실패)
function getData() {
    return new Promise(function (resolve, reject) {
        var data = 100
        resolve(data)
    })
}

getData().then(function (resolvedData) {
    console.log(resolvedData)
}).catch(function (err) {
    console.error(err)
})

// promise pattern in real project
getData(userInfo)
    .then(parseValue)
    .then(auth)
    .then(display)

var userInfo = {
    id: 'user@gmail.com',
    pw: '******'
}

function parseValue() {
    return new Promise() {
        // ...
    })
}
function auth() {
    return new Promise() {
        // ...
    })
}
function display() {
    return new Promise() {
        // ...
    })
}

// async-await: fetch 패턴보다 향상된 패턴
// promise 사용
function logFetch(url) {
  return fetch(url)
    .then(response => response.text())
    .then(text => {
      console.log(text);
    }).catch(err => {
      console.error('fetch failed', err);
    });
}
logFetch('https://hacker-news.firebaseio.com/v0/item/8863.json')

// async-await 사용
async function logFetch(url) {
  try {
    const response = await fetch(url)
    console.log(await response.text())
  } catch (err) {
    console.log('fetch failed', err)
  }
}
logFetch('https://hacker-news.firebaseio.com/v0/item/8863.json')

```

8. Iterator / Generator

```javascript
// iterable: Array, TypedArray, String, Map, Set
const iterable = {}

iterable[Symbol.iterator] = function*() {
  yield 1
  yield 2
  yield 3
}
console.log([...iterable])
for (var value of iterable) {
  console.log(value)
}

// iterator: interface to read
var iterator = '12'[Symbol.iterator]()
iterator.next() // {value: "1", done: false}
iterator.next() // {value: "2", done: false}
iterator.next() // {value: undefined, done: true}

// generator: interface to write (함수이면서 함수와는 다르게 동작함)
function* foo() {
  yield 1
  yield 2
  yield 3
}

for (let i of foo()) {
  console.log(i)
}
```

9. import/export

```javascript
//math.js
function plus(x, y) {
  return x + y
}
const doublePI = Math.PI * 2
export { plus, doublePI }
//다른 스크립트에서(impotMath.js)
import { plus, doublePI } from 'math'
console.log(plus(3, 4)) //7
console.log(doublePI) //6.283185307179586
```

10. 비구조화 할당

```javascript
const hudi = {
  name: '박주희',
  job: '학생 ',
  skills: ['ES6', 'React', 'node.js'],
}

let { name, job } = hudi
//비구조화 할당

console.log(name, job) // 박주희 학생
```

---

### 3. props 와 state는 언제 쓰는가.

1. Props
   부모 컴포넌트가 자식 컴포넌트한테 전달하는 데이터로, (자식 입장에서)읽기 전용이다.

2. State
   자신이 들고 있는 값을 말한다. (읽기 전용인 props와 비교해보자면, 쓰기 전용이라고 볼 수 있겠다)

---

### 4. 컴포넌트의 각 생명주기는 어떻게 되고 각 시점은 언제 호출되는가?

**React의 컴포너트는 생명주기(Life cycle)을 가진다.**

> 생명주기란 컴포넌트가 생성되고 사용되고 소멸될 때 까지 일련의 과정을 말한다.

1. componentWillMount()
   React 엘리먼트를 실제 DOM 노드에 추가하기 직전에 호출되는 메소드다.
   DOM이 생성되지 않았으므로 DOM을 조작할 수 없고, render가 호출되기 전이기 때문에 setState를 사용해도 render가 호출하지 않는다.

2. componentDidMount()
   컴포넌트가 만들어지고 render가 호출된 이후에 호출되는 메소드다. AJAX나 타이머를 생성하는 코드를 작성하는 부분이다.

3. componentWillReceiveProps(nextProps)
   컴포넌트 생성후에 첫 렌더링을 마친 후 호출되는 메서드다. 컴포넌트가 처음 마운트 되는 시점에서는 호출되지 않는다.
   props를 받아서 state를 변경해야 하는 경우 유용하다.
   이 메소드 내부에서 setState를 사용해도 추가적인 렌더링이 발생하지 않는다.

4. shouldComponentUpdate(nextProps, nextState)
   컴포넌트 업데이트 직전에 호출되는 메소드다. props 또는 state가 변경되었을 때, 재랜더링을 여부를 return 값으로 결정한다.

5. componentWillUpdate(nextProps, nextState)
   shouldComponentUpdate가 불린 이후에 컴포넌트 업데이트 직전에서 호출되는 메소드다.
   새로운 props 또는 state가 반영되기 직전 새로운 값들을 받는다.
   이 메서드 안에서 this.setState()를 사용하면 무한 루프가 일어나게 되므로 사용하면 안된다.

6. componentDidUpdate(prevProps, prevState)
   컴포넌트 업데이트 직후에 호출되는 메소드다.

7. componentWillUnmount()
   컴포넌트가 소멸된 시점에(DOM에서 삭제된 후) 실행되는 메소드다.
   컴포넌트 내부에서 타이머나 비동기 API를 사용하고 있을 때, 이를 제거하기에 유용하다.

<a class="source_link" href="https://velog.io/@kyusung/%EB%A6%AC%EC%95%A1%ED%8A%B8-%EA%B5%90%EA%B3%BC%EC%84%9C-%EC%BB%B4%ED%8F%AC%EB%84%8C%ED%8A%B8%EC%99%80-%EB%9D%BC%EC%9D%B4%ED%94%84%EC%82%AC%EC%9D%B4%ED%81%B4-%EC%9D%B4%EB%B2%A4%ED%8A%B8" target="_blank">출처</a>

---

### 5. 자바스크립트에서 사용하는 자료구조에는 어떤것들이 있는가?

Array, Linked List, Queue, Priority Queue, Stack, Hash Table, Heap, Tree, Graph

<a class="source_link" href="https://velog.io/@ryu/JavaScript-%EC%9E%90%EB%A3%8C%EA%B5%AC%EC%A1%B0-Array%EB%B0%B0%EC%97%B4" target="_blank">출처</a>
