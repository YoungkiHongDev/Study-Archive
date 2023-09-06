# Git 설치 시 설정
**VScode 에디터 설정** -> 충돌 문제 발생 시 VScode로 볼 수 있다.
**bash only X window prompt** -> 편의를 위해서 선택한다.


# GitLens
VScode 확장으로 설치한다.
왼쪽 사이드바 원 안에 줄기 아이콘으로 사용할 수 있다.
VScode 환경에서 변경사항, 브랜치, 리모트, 히스토리 등 Git을 편하게 확인할 수 있다.

# Git 설정
**git config --list** //깃 설정 목록 보기
**git config --global user.name [깃 유저명]** //깃 유저명 설정
**git config --global user.email [깃 이메일]** //깃 이메일 설정
**cat ~/.gitconfig** //깃 설정 한눈에 보기

# Git 작업원리
1. 개발자A가 Local Repository에서 작업
2. 작업한 내용을 Commit & Push하여 Server Repository에 업로드
3. 개발자B는 A가 작업한 소스를 Pull하여 Local Repository에 받아옴

# Git 기본명령
**git init** //깃 초기화
**git add** //업로드할 파일 준비
**git commit** //업로드할 파일 커밋으로 묶어주기
**git remote add origin** [깃허브주소] //서버와 로컬 통로 연결
**git push -u origin master** //서버에 업로드
**git pull** //서버에서 받아오기
**git clone** //깃허브에 만든 저장소 클론하기

# Git 커밋 옵션
**git commit -m "메시지"** // 메시지를 남기는 옵션
**git commit -m "메시지1    
메시지2     
메시지3"** //커밋 메시지를 여러줄 쓰는 방법
**git commit -am "메시지"** //add & commit을 동시에 하는 옵션, 새로운 파일 추가할 때는 사용 불가능

# origin이란?
원격 저장소의 기본 이름이다.
**git remote add [이름] [주소]** 형식으로 명령어에서 일반적으로 이름에 origin을 사용한다.
주소는 이름에 등록되어 주소를 일일히 칠 필요없이 origin만 사용 가능하다.

# add & commit 3단계
1. **working directory** -> 소스를 작업하는 디렉터리, add시 staging area로 넘어감  
2. **staging area** -> 준비 태세 단계, commit시 git repository로 넘어감  
3. **git repository** -> 로컬 저장소, push시 server repository로 올라감  

# conflicts 해결방법
여럿이 같은 부분을 수정하면 충돌이 날 경우 다음과 같은 해결방법들이 있다.
1. 현재 변경 사항 수락 -> 내 코드만 수용
2. 수신 변경 사항 수락 -> 다른 사람 코드만 수용
3. 두 변경 사항 모두 수락 -> 양쪽 코드를 모두 수용
4. 직접 해결 -> 자동으로 해결이 안될 경우 직접 코드를 수정

# Git flow & Git issue 실습
**실습 과정 기록**  
- https://blog.naver.com/ceron3804/222812092254

**1. Git flow**  
git flow 설치 유무를 확인한다.
일반적으로 git을 설치하면 같이 설치된다.

**2. Git flow init**  
git flow를 초기화 한다.
**-d** 옵션을 사용하면 엔터를 칠 필요 없이 **default**로 진행된다.
**develop** 브랜치가 생성된다.

**3. Git flow feature start [브랜치명]**
**feature** 브랜치가 생성된다.

**4. Git branch -a**  
모든 브랜치를 확인할 수 있다.

**5. Git push origin --all**  
우선, 생성한 브랜치를 깃허브에 올린다.

**6. Github에 브랜치가 생겼는지 확인하기**  
깃허브 사이트에서 프로젝트에 브랜치가 생겼는지 확인한다.

**7. add & commit**  
작성한 파일 올릴 준비  

**8. Git flow feature publish**  
작성한 md 파일 feature 브랜치에서 main 브랜치로 PR 요청한다.

**9. Github 상단에 나온 Compare & pull requests 클릭**

**10. Pull requests에 녹색 Merge pull request 나오면 성공이므로 merge하기**

# Git 내역조회
**1. Git status**  
- git add로 staging한 파일들을 조회한다.

**2. Git log --all --oneline**  
git commit한 모든 내역을 한눈에 조회한다.
**--graph** 옵션을 쓰면 시각적 효과 상승

# Git 커밋비교
**1. Git diff**
최근 commit과 현재파일의 차이점을 보여준다.
J, K를 사용하여 스크롤을 조작하고 Q로 종료한다.
터미널 하나로 보기 불편하고 스페이스바, 엔터까지 차이점으로 판단한다.

**2. Git difftool**
git diff를 Vim 에디터로 보여주어 시각적 비교가 편리한 명령어이다.
H, J, K, L 키를 사용하여 커서 이동이 가능하다.
:q 혹은 :qa를 사용하여 종료한다.
**git difftool [특정 커밋 아이디]** //특정 커밋과 현재 파일의 차이점을 비교한다.
**git difftool [특정 커밋 아이디1] [특정 커밋 아이디2]** //특정 커밋 둘의 차이점을 비교한다.

**Vim 에디터가 아닌 VScode로 보고싶을 경우**
**git config --global diff.tool vscode**
**git config --global difftool.vscode.cmd 'code --wait --diff $LOCAL $REMOTE'**

# Git 브랜치
**git branch [브랜치명]** //브랜치 생성
**git branch -d [브랜치명]** //merge 완료된 브랜치 삭제
**git branch -D [브랜치명]** //merge 안한 브랜치 삭제
**git switch [특정 브랜치명]** //특정 브랜치로 변경
**git merge [특정 브랜치명]** //특정 브랜치와 병합, 충돌 해결 후 add & commit
**git push origin --delete [브랜치명]** //원격 저장소 브랜치 삭제

# merge 다양한 방법
**3-way merge**  
각 브랜치에 신규 commit이 있는 경우 일반적으로 merge하는 방법이다.

**fast-forward merge**  
main 브랜치에는 신규 commit이 없고 다른 브랜치에는 신규 commit이 있는 경우에 사용하는 방법이다.
다른 브랜치를 main 브랜치로 지칭하여 사용한다.
조건이 만족되면 자동으로 발동되는 merge 방식이다.
자동으로 못하게 하는 방법 -> **git merge --no-ff [브랜치명]**

**rebase & fast-forward merge**
merge가 아닌 rebase를 사용하는 방법이다.
신규 브랜치의 시작점을 다른 commit으로 변경한다.
main 브랜치의 최근 commit으로 시작점을 옮기고 fast-forward merge한다.
3-way merge를 많이쓰면 git log가 복잡해지므로 log를 깔끔하게 보기위해 사용한다.
**conflict 충돌**이 자주 발생하는 단점이 있다.

**squash & merge**
**git merge --squash [새로운 브랜치명]**
3-way merge를 하다보면 commit 내역에 쓸데없는 merge 내역이 다수 출력된다.
main 브랜치 로그만 볼 수 있도록 곁가지를 쳐내는 방법이다. (rebase와 유사함)

1. 다른 브랜치에서 작업
2. main 브랜치 이동
3. merge --squash
4. 다른 브랜치의 commit을 잘라와서 main 브랜치에 붙이기

# rebase & merge 차이점
**merge**
1. main 브랜치로 이동
2. git merge [다른 브랜치명]

**rebase**
1. 다른 브랜치로 이동
2. git rebase main
3. main 브랜치로 이동
4. git merge [다른 브랜치명]

# Git 되돌리기
## Git restore
파일을 이전 commit 시점으로 복구하는 방법이다.

**git restore [파일명]** //파일을 최근 커밋으로 복구한다.
**git restore --source [커밋아이디] [파일명]** //파일을 특정 커밋으로 복구한다.
**git restore --staged [파일명]** //특정 파일의 staging을 취소한다.

## Git revert
commit을 취소하는 방법이다.
reset과 비슷하지만 소스를 유지하고 history가 쌓인다.
흔적을 남기기위해 reset보다 revert 사용이 권장된다.

**git revert HEAD** //최근 커밋을 취소
**git revert [커밋아이디]** //특정 커밋을 취소
**git revert [커밋아이디1] [커밋아이디2]** //여러개의 커밋을 취소
**git revert -m 1 [merge 커밋아이디]** //merge 완료된 커밋을 취소

## Git reset
**Git reset [hard | soft | mixed]**
commit을 되돌리는 방법으로 협업 시 다른 사람의 코드를 없앨 수 있으므로 주의!
**git reset --hard [커밋아이디]** //특정 커밋 시점으로 되돌리고 이후의 변동사항을 삭제
**git reset --soft [커밋아이디]** //특정 커밋 시점으로 되돌리고 이후의 변동사항을 staging
**git reset --mixed [커밋아이디]** //특정 커밋 시점으로 되돌리고 이후의 변동사항을 unstaged

**Git reset 사용법**
A, B, C 커밋이 쌓여있고 C 커밋에서 B 커밋으로 돌아가고 싶을 경우
1. git reset으로 B 커밋으로 돌아간다.
2. rollback 메시지를 남기고 commit 생성
3. 소스를 rollback commit과 똑같이 수정
4. push 하면 돌아가기 성공 (reject 당하면 -uf 옵션 또는 +브랜치로 push)

# Git 파일 삭제
**Git rm [파일명]**
파일 삭제 작업 후 Staging Area에 add한 것처럼 올라간다.
git commit으로 파일 삭제에 대한 메시지를 남기고 git push로 작업을 완료한다.

만약, 여러 파일을 삭제하고 싶다면?
- 파일 개수가 적을 경우: **git rm [파일명1] [파일명2]**
- 파일 개수가 많고 확장자가 같을 경우: **git rm *.[확장자]**

# Git 파일 이름 변경
```
git mv [원래 파일명] [바꿀 파일명]
```
파일명이 변경이 안될 경우 한번도 git add 한 적이 없는 파일이므로 staging 후 수행하기

# .gitignore 걸러진 파일 확인
```
git status --ignored
```
git bash 환경에서 사용 시 gitignore 내용에 따라 걸러진 파일들이 붉은색으로 보인다.

# 마지막 커밋 메시지 변경
```
git commit --amend -m "변경 커밋 메시지"
```