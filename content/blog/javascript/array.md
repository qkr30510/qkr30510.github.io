---
title: Array
date: 2020-04-29 17:04:51
category: javascript
draft: false
---

```javascript
var test = document.getElementById('test')

const one = new Array(1920, 1921, 1922, 1933)

for (var i = 1920; i < 2020; i++) {
  one.push(i)
}

console.log(one)
let result = one.map(v => {
  return `<option>${v + 1}</option>`
})
test.innerHTML = result.join('')

console.log(result.join(''))
```

```javascript
var test = document.getElementById('test')

const one = new Array()

for (var i = 1920; i < 2020; i++) {
  one.push(`<option>${i + 1}</option>`)
}

console.log(one)
/* let result = one.map((v)=>{
 return `<option>${v+1}</option>`
 }) */
test.innerHTML = one.join('')

console.log(one.join(''))
```

아래걸로 축약가능
