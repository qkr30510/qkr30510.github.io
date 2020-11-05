---
title: 커밋한 것만큼 origin master가 앞서 있습니다.
date: 2020-11-05 15:11:63
category: git
draft: false
---

깃 푸시 오류로 커밋한 것만큼 origin / master 가 앞서 있습니다.라는 오류 메세지와 함께 푸시가 안되는 오류가 있었다. ㅜㅜ
한참을 끙끙 되다가 오류 메세지 해결 방법을 공유하고자 한다.

### 오류 메세지

```javascript
# On branch master
# Your branch is ahead of 'origin/master' by 1 commit.
#
nothing to commit (working directory clean)
```

### 해결 방법

```javascript
$ git fetch --all
$ git reset --hard origin/master
$ git pull origin master

//$ git fetch --all : git remote 에서 전체 내용을 받아온다.
//$ git reset --hard origin/master : 수정된 내역을 지우고 이전내용으로 복구한다.
//$ git pull origin master : 현재 작업하고있는 로컬에 커밋을 병합한다.
```

해당 해결 방법으로 `fatal: 관계 없는 커밋 내역의 병합을 거부합니다`도 해결이 가능하다.
