---
title: git clone
date: 2020-07-12 23:07:49
category: etc
draft: false
---

깃 버전관리중 origin에 branch를 생성해서 master에 merge하는 방법도 있지만, 기존 소스를 clone하여
수정 후 origin에 merge하는 방법도 있는듯 하여 clone하여 소스를 수정해보았다.

### 사용방법

1. 배포되고 있는 사이트에 가서 `git remote -v` 로 연결되어있는 깃 주소 확인
2. 새로 리뉴얼 할 폴더를 만들고 그 폴더에 들어가서 `git clone 확인한 깃 주소`
3. node가 깔려있지않을테니 `yarn install` 또는 `npm install`
4. 작업후엔 `git remote add 새로운 별명`
5. 깃 커밋, 푸시 진행 후 원래 연결되어있는 사이트에서 git pull

> 풀리퀘스트라는것이 있는데 그건 아래 사이트에서 확인
> https://wayhome25.github.io/git/2017/07/08/git-first-pull-request-story/
