---
title: '깃과 깃허브'
date: 2020-3-16 13:15:13
category: 'git'
draft: false
---

깃과 깃 허브에 대해서 알아보면 좋을꺼 같아서 정리해 보았다.


### 깃 허브란?
깃을 사용하는 프로젝트를 지원하는 웹 호스팅 서비스 


### Git이란?
프로그램등의 소스 코드 관리를 위한 분산 버전 관리 시스템이다. <br>



### Git을 쓰는 이유
* 여럿이서 모여 팀 프로젝트를 할 때, 서로 만든 코드를 주고 받아 합치는 형식이 아닌, 각자의 수정사항을 각각 업로드 하고 
깃은 여러개의 파일을 저장해주기 때문에 버전관리가 용이해져 생산성이 증가한다. 
* 소스코드가 커밋 단위로 관리되기 때문에 이전의 내용으로 돌아갈 수 있다.
* 분산 버전관리이기 때문에 인터넷이 연결되지 않은 곳에서도 개발을 진행할 수 있으며, 중앙 저장소가 날라가 버려도 다시 원상복구 활 수 있다.


### Git의 주요 단어 

<br>

1. **저장소(Git repository)** <br>
    파일이나 폴더를 저장해 두는 곳이다. 그런데 Git 저장소가 제공하는 좋은 점 중 하나는 파일이 변경 이력 별로 구분되어 저장되어 저장된다는 점 이다. 비슷한 파일이라고 실제 내용 일부 문구가 서로 다르면 다른 파일로 인식하기 때문에 파일을 변경 사항 별로 구분해 저장할 수 있다.
<br>
<br>

2. **체크아웃 (check out)**<br>
    특정 시점이나 브랜치의 소스코드로 이동하는 것을 의미합니다. 체크아웃 대상은 브랜치, 커밋, 그리고 태그이며 체크아웃을 통해 과거 여러 시점의 소스 코드로 이동 할수 있다. 
<br>
<br>


3. **커밋 (commit)**<br>
    게임할때 중간 저장처럼 저장소의 **스냅샷**을 찍어, 저장소의 체크포인트를 가지는 것이다. <br>
    커밋 메세지는 팀원들에게도 '어떠한 내용으로 수정하였다는 내용' 으로 중요한 메세지가 되니 커밋메시지 작성할떄는 꼭 신경써서 작성하도록 하자 

<br>
<br>

4. **스테이트(state)**<br> 
    저장소의 상태를 체크.<br>
    커밋이 필요한 변경사항이 있는지, 현재 저장소의 어떤 브랜치에서 작업하고 있는지 등을 볼 수 있다.

<br>
<br>

5. **푸시 (push)**<br>
    내가 작업하고 난 작업물을 커밋한 후 **PUSH**한다.

<br>
<br>


6. **풀 (pull)**<br>
    다른이가 작업한 작업물을 **PULL**

<br>
<br>

7. **브랜치 (branch)**<br>
    개발을 하다 보면 코드를 여러 개로 복사해야 하는 일이 자주 생긴다. 코드를 통째로 복사하고 나면 원래 코드와는 상관없이 독립적으로 개발을 진행할 수 있는데, 이렇게 독립적으로 개발하는 것이 브랜치이다.

<br>
<br>

8. **병합(Merge)**<br>
    독립적으로 개발한 브랜치를 다시 병합해야하는 순간이 있는데, 이것을 merge 라고 한다.<br>

<br>
<br>

### Git의 주요 명령어 

git 에는 다양한 명령어들이 많겠지만, 내가 아직까지 사용하는 명령어들은 아래와 같다. 

```
git init : 깃 저장소를 초기화 한다. 이것을 입력한 후에 추가적인 깃 명령어를 사용할 수 있다. 
git config: 최초에 깃을 설정할때 사용한다. 
git help: 가장 많이 사용하는 깃 명령어를 보여준다.
git state: 저장소의 상태를 체크할 수 있다. 저장수 안에 어떤 파일이 있는지, 커밋이 필요한 변경사항이 있는지, 어떤 브랜치에서 작업하고 있는지 등
git branch: 새로운 브랜치를 만들고, 본인의 변경사항과 파일 추가등의 타임라인을 만든다. 동료들과 함께 작업하고 본인의 변경사항을 원할때 사용한다.
git add . : 모든 저장 내용을 저장
git commit -m "커밋내용" : '스냅샷'을 찍어 저장한다.
git checkout : 현재 위치하지않은 저장소를 "체크아웃" 할 수 있가. 체크하길 원하는 저장소로 옮겨가게 해주는 탐색 명령이다.
git merge : 브랜치 작업을 끝내고, 모든 협엽자가 볼 수 있는 master브랜치로 병합한다. 
git push -u origin master : 푸시하여 보낸다. 
git pull : 다른 사람이 변경사항을 업로드 한것을 다운로드 받는다. 
```
    

