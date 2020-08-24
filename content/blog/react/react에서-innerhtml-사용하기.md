---
title: React에서 innerHTML 사용하기
date: 2020-08-24 10:08:63
category: react
draft: false
---

Api로 끌어와서 뷰로 뿌려줘야하는데, 그 중에 태그들이 삽입된 부분이 있어서
innerHTML을 사용해야했다.

방법은 의외로 간단했다.
`dangerouslySetInnerHTML`을 사용하는데 이는 내가 개발자고 괜찮으니까 사용해~
라는 뜻이라고 한다. 암튼 생각보다 간단하게 해결되어 다행이다.

## dangerouslySetInnerHTML 적용 전

```javascript
<p>{contents}</p>

출력:
<p style="text-align: center; "></p><p style="text-align: center; "><br></p><p style="text-align: center; ">
같이 태그가 문자열로 나타남
```

## dangerouslySetInnerHTML 적용

```javascript
<p dangerouslySetInnerHTML={{ __html: contents }}></p>
```

출력:
원하는 모습으로 html 코드 실행
