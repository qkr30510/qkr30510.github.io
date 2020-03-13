---
title: '개츠비 블로그 오류 in 윈도우'
date: 2020-3-6 16:21:13
category: 'git blog'
draft: false
---

앞서 얘기했던 것처럼 나는 이 블로그를 만들면서 몇가지의 오류에 직면 하였는데,<br> 
그 오류들은 스스로 없어지기도 했었고 우여곡절 끝에 해결하기도 하였다.<br>
오류는 크게 3가지정도로 나눌수 있을꺼 같다.

<br>

###  1. 개츠비 cil 설치 실패

처음부터 날 힘들게 했던 오류 였다.<br>
스타터를 사용했던 나는.. 왜 오류나는지 이유조차 몰랐었는데.. <br>
다행히 똑똑한 지인분이 해결해 주셨다.ㅜㅜ<br>
비쥬얼스튜디오 초기세팅을 다시 하는걸로 문제 해결하였다.<br>
[해당url 참고](https://www.gatsbyjs.org/docs/gatsby-on-windows/)

<br>


###  2. npm 오류

* ## npm not install 

    #### 1. package.lock.json 삭제
    #### 2. node_modules 삭제
    #### 3. node 재 설치 

    혹시 이래도 안된다면, 컴퓨터를 재 부팅 하길 바란다. 
    만약, 이 과정에서 **권한이 없어 ~~ 실행 할 수 없습니다.** 라는 말이 나오면 터미널을 관리자 권한으로 실행하여 하면 해결된다.

* ## can not find module 'sharp'

    해당 에러도 위의 에러와 마찬가지로 해결하면 된다.

    #### 1. package.lock.json 삭제
    #### 2. node_modules 삭제
    #### 3. node 재 설치 

<br>

###  3. GraphQL query 오류

솔직히 말하자면, 난 아직 이 오류를 해결하지 못했다.
맨처음 로컬 호스트오류로 접속했을때, 해당 오류가 떠서 ```Have the same issue. Deleting fragments.js - helped.``` 조언에 따라 해당 파일을 지웠고, 로컬에서는 정상적으로 호출이 되어 문제없이 해결된줄 알았다.



