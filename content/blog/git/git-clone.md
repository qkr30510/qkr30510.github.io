---
title: git clone
date: 2020-07-12 23:07:49
category: etc
draft: false
---

배포되어있는 사이트를 새로 추가하는 기능을 만들고 싶었다.
branch 를 생성하고 만들어서 origin으로 merge만 안하면 되는건줄 알고 기존엔 그렇게 했었는데
하다보니 branch로 만든부분을 병합하지않고 지우는것도 잘 안되고.. 마음처럼 잘 되지않아 다시 알아보니
보통은 clone을 하여 새로 만들고 그 후 기존의 레파지토리로 병합하는 식으로 진행하시는것 같았다.

### 사용방법

1. 배포되고 있는 사이트에 가서 `git remote -v` 로 연결되어있는 깃 주소 확인
2. 새로 리뉴얼 할 폴더를 만들고 그 폴더에 들어가서 `git clone 확인한 깃 주소`
3. node가 깔려있지않을테니 `yarn install` 또는 `npm install`
4. 작업후엔 `git remote add 새로운 별명`
5. 깃 커밋, 푸시 진행 후 원래 연결되어있는 사이트에서 git pull

> 풀리퀘스트라는것이 있는데 그건 아래 사이트에서 확인
> https://wayhome25.github.io/git/2017/07/08/git-first-pull-request-story/
