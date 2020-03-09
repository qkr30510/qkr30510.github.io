---
title: '개츠비 블로그 오류 in 윈도우'
date: 2020-3-6 16:21:13
category: 'git blog'
draft: false
---

앞서 얘기했던 것처럼 나는 이 블로그를 만들면서 몇가지의 오류에 직면 하였는데,
그 오류들은 스스로 없어지기도 했었고 
고생을 하기도 했었다. 
오류는 크게 3가지정도로 나눌수 있을꺼 같다.

###  개츠비 cil 설치 실패

처음부터 날 힘들게 했던 오류 였다.
스타터를 사용했던 나는.. 왜 오류나는지 이유조차 몰랐었는데.. 
다행히 똑똑한 지인분이 해결해 주셨다.ㅜㅜ
비쥬얼스튜디오 초기세팅을 다시 하는걸로 문제 해결
[해당url 참고](https://www.gatsbyjs.org/docs/gatsby-on-windows/)

###  npm 오류

* ## npm not install 

    1. package.lock.json 삭제
    2. node_modules 삭제
    3. node 재 설치 

    혹시 이래도 안된다면, 컴퓨터를 재 부팅 하길 바란다. 
    만약, 이 과정에서 **권한이 없어 ~~ 실행 할 수 없습니다.** 라는 말이 나오면 터미널을 관리자 권한으로 실행하여 하면 해결된다.

* ## can not find module 'sharp'

    해당 에러도 위의 에러와 마찬가지로 해결하면 된다.

    1. package.lock.json 삭제
    2. node_modules 삭제
    3. node 재 설치     


###  GraphQL query 오류





