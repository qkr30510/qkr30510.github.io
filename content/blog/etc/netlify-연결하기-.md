---
title: netlify 연결하기
date: 2020-06-28 17:06:50
category: etc
draft: false
---

netlify 연결하는데 이번에 꽤 힘들었다.
왜냐하면 netlify 자체에서 이번에 업데이트를 진행했는데 그 사실을 몰랐기 때문이다 ㅜㅜ

### 연결하는 법

1. netlify 에서 깃 레포를 연결해줌.
2. package.json에서 script 위치에 "homepage": "https://13akstjq.github.io/manflex", 깃 위치를 넣어줌
3. netlify 환경설정에서 `Build command`를 찾아 `CI= npm run build`를 넣어주고 배포를 다시 넣어줌.

- 참고: package.json.lock은 지워줘야함.

혹시 안되면 https://13akstjq.github.io/2019/07/21/%EB%A6%AC%EC%95%A1%ED%8A%B8%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8-github-netlify%EC%97%90-%EB%B0%B0%ED%8F%AC%ED%95%98%EA%B8%B0.html 볼것
