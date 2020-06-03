---
title: Merge error
date: 2020-06-03 18:06:34
category: git
draft: false
---

merge하는 도중 블루스크린이 뜨는 사태가 발생했었다. 
별로의 branch로 깃에 푸시한 상태였었고, master로 merge하는 중이였어서 크게 걱정하지는 않았었다. 
**컴퓨터 재 실행 후 다시 푸시하려고 하니 repository 와 연결이 안되어있다는 오류 메세지가 나왔다.**
----

### 오류 해결 시도 한 것
1. `git init` 후 `git remote`로 다시 연결해보았으나 `not a git repository (or any of the parent directories)`라는 오류 메세지만 출력되었다. 
2. 기존에 올라간 깃을 다시 `clone` 하였지만 깃에 연결 안되는 문제는 동일하였다. 

------

### 오류 해결
1. 해당 폴더에 들어가 숨긴폴더 설정을 해제한 후 `git`폴더를 삭제하였다. 
2. `git init` 과 `git remote`를 다시 하였다. (성공적으로 연결되었다.)
3.  `push`가 안되는 문제가 발생했고 `pull`을 실행 한 후에 다시 `push` 하였다. 
    -  `Detached HEAD `가 새롭게 발생하였고, `git checkout -b 새로운브랜치명` 으로 새 브랜치로 체크아웃후 `pull` 하였다. 
4. 기존에 작성했던 브랜치들은 지워졌지만, 커밋메세지는 다 살아있는걸 확인하였다.
    

