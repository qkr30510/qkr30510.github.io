---
title: ref
date: 2020-06-11 15:06:91
category: react
draft: false
---

### ref의 개념

리액트 프로젝트 내부에서 DOM에 이름을 다는 개념이다.

### ref를 사용해야할 때

1. DOM을 직접 건드려야 하는경우 사용한다.
   -> id를 사용할순 있지만, 유일해야하는 id를 컴포넌트 재사용에 사용하게 된다면 중복이 발생할수 있다.
2. 특정 <input>태그에 포커스를 주는 경우
3. 스크롤 박스를 조작하는 경우
4. <Canvas>태그에 그림을 그리는 경우

### ref 사용 방법

props를 설정하는 방법과 유사하며, ref 값으로 콜백 함수를 전달한다.

```javascript
<input ref="{(ref)=> {this.input.ref}}" />
```
