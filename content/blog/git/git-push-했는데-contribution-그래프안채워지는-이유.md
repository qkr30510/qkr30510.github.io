---
title: git push 했는데 contribution 그래프안채워지는 이유
date: 2020-08-17 16:08:30
category: git
draft: false
---

같은 레포지토리의 내용을 여러 컴퓨터에서 사용하다 보니 여러 컴퓨터에 clone 해서 사용해야할 일이 많았다.
근데 이상하게도 push는 되는데 contribution 에는 꽉 차지 않아서 검색해봤더니 해결방법은 이외로 간단하였다.

### 해결방법

1. git config --global user.email 바꿀@이메일주소.com
2. git config --global user.name 바꿀@이름

git에 설정되어있는 것과 동일한 email과 name 을 설정해주고 push 하면 간단하게 해결된다!
