---
title: input 숫자만 넣기 및 빈값 체크
date: 2020-09-02 21:09:75
category: javascript
draft: false
---

### input 숫자만 넣기

```javascript
<input
  type="text"
  placeholder="숫자를 입력해주세요."
  value=""
  oninput="this.value = this.value.replace(/[^0-9]/g, '');"
/>
```

> 정규표현식인 `replace(/[^0-9]/g, ''`가 중요하다.

### input 빈값 체크

```javascript
if ($(input).val() == '') {
  alert()
}
```
