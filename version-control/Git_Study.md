# Git 에디터 설정 - VSCode

Git 충돌 시 VScode에서 시각적으로 비교하고 해결할 수 있게 한다.

```bash
git config --global core.editor "code --wait"
```

## Git 충돌 발생 시 VSCode를 통한 처리 과정

1. `충돌 발생`: git merge나 git rebase 도중 충돌이 발생하면, Git은 충돌을 해결하기 위해 에디터를 연다.

2. `VSCode 실행`: 설정이 되어 있다면, Git은 VSCode를 실행하여 충돌이 발생한 파일을 연다.

3. `충돌 내용 확인`: VSCode에서 충돌된 부분을 직접 확인하고, 충돌된 코드들을 비교하여 수정한다.

4. `수정 후 저장`: 충돌된 내용을 수정하고 저장한 후, VSCode를 닫는다.

5. `Git에 알림`: VSCode가 닫히면 Git은 충돌 해결이 완료된 것으로 인식하고, 작업을 이어서 진행할 수 있다.

# Git 기본 설정

`git config --list` : 현재 Git 설정 목록 보기

`git config --global user.name "[유저명]"` : Git 유저명 설정

`git config --global user.email "[이메일]"` : Git 이메일 설정

`cat ~/.gitconfig` : Git 설정 한눈에 보기

`git config --global core.autocrlf true` : 협업 시 윈도우와 맥 사이의 줄바꿈 오류 방지

# Git 작업 원리

1. 개발자 A가 `Local Repository`에서 작업

2. 작업한 내용을 `Commit & Push`하여 `Server Repository`에 업로드

3. 개발자 B는 `Server Repository`에서 A가 작업한 소스를 `Pull`하여 `Local Repository`에 반영

# Git 기본 명령어

`git init` : 새로운 Git 저장소 초기화

`git add [파일명]` : 스테이징 영역에 파일 추가

`git commit -m "[메시지]"` : 스테이징된 파일들을 커밋으로 저장

`git remote add origin [깃허브주소]` : 로컬 저장소와 원격 저장소 연결

`git push -u origin master` : 원격 저장소에 업로드

`git pull` : 원격 저장소에서 변경사항 가져오기

`git clone [깃허브 주소]` : 원격 저장소를 로컬로 복제

# Git 커밋 옵션

`git commit -m "[메시지]"` : 커밋 메시지와 함께 커밋

> git commit -m "메시지1  
> 메시지2  
> 메시지3"  
> 이런식으로 커밋 메시지를 여러줄 작성할 수 있다.

`git commit -am "[메시지]"` : add, commit을 동시에 실행하지만, 새로운 파일 추가 시 사용 불가

# origin이란?

origin은 원격 저장소의 기본 이름

`git remote add [이름] [주소]`

일반적으로 이름에 `origin`을 사용한다.  
이후에는 `origin`만으로도 해당 원격 저장소를 지칭할 수 있다.

# Git의 3단계 작업 과정

`Working Directory`: 소스 작업 공간

`Staging Area`: 커밋을 위해 준비된 파일들의 임시 공간

`Git Repository`: 커밋이 저장되는 로컬 저장소

> `git push` 시 `Server Repository`로 업로드

# 충돌 해결 방법 (Conflicts)

`현재 변경 사항 수락`: 내 코드만 반영

`수신 변경 사항 수락`: 다른 사람의 코드만 반영

`두 변경 사항 모두 수락`: 양쪽 코드를 모두 반영

`직접 해결`: 수동으로 충돌된 부분을 수정

# Git Flow 기본 명령어

`git flow init`: Git Flow 초기화

`git flow init -d`: 기본 설정을 자동으로 진행

`git flow feature start [브랜치명]`: 새로운 기능 브랜치 생성

`git flow feature publish`: 기능 브랜치에서 작업 후 원격 저장소로 푸시

`git flow feature finish [브랜치명]`: 기능 브랜치 작업 완료 후 병합

# Git 내역 조회

`git status`: 스테이징된 파일 목록 확인

`git log --all --oneline --graph`: 모든 커밋 내역을 한눈에 시각적으로 확인

# Git 커밋 비교

`git diff`: 최근 커밋과 현재 파일의 차이점 비교

`git difftool`: Vim 에디터나 VSCode에서 시각적으로 차이점 비교

```bash
// VSCode에서 보기 위한 설정
git config --global diff.tool vscode
git config --global difftool.vscode.cmd 'code --wait --diff $LOCAL $REMOTE'
```

# Git 브랜치 관리

`git branch [브랜치명]`: 새로운 브랜치 생성

`git branch -d [브랜치명]`: 병합된 브랜치 삭제

`git branch -D [브랜치명]`: 병합되지 않은 브랜치 강제 삭제

`git switch [브랜치명]`: 특정 브랜치로 전환

`git merge [브랜치명]`: 브랜치 병합

`git push origin --delete [브랜치명]`: 원격 저장소에서 브랜치 삭제

# 다양한 병합(Merge) 방법

`3-way merge`: 일반적으로 사용하는 병합 방법

`fast-forward merge`: 메인 브랜치에 신규 커밋이 없을 때 사용

`rebase & fast-forward merge`: rebase 후 병합하여 커밋 기록을 깔끔하게 유지

`squash & merge`: 여러 커밋을 하나로 합쳐서 병합

## 3-way merge 강제

fast-forward merge를 사용하지 못하도록 3-way merge를 강제하는 명령어는 다음과 같다.

```bash
git merge --no-ff [브랜치명]
```

### 3-way merge를 강제하는 이유

1. **명확한 병합 기록**: 병합 커밋을 생성하여 병합 이력을 명확하게 기록한다. 나중에 어떤 작업이 언제 병합되었는지 추적하기 쉽다.

2. **브랜치 히스토리의 유지**: 브랜치의 히스토리를 보존한다. 나중에 히스토리를 추적하거나 디버깅할 때 유용하다.

3. **협업 시 충돌 해결**: 병합 커밋을 통해 협업 팀원 간 변경 사항을 명확하게 구분한다. 이는 충돌 발생 시 문제 해결에 도움이 된다.

요약하면 Fast-forward Merge는 결과적으로 병합 커밋이 생성되지 않으므로 병합 기록이 남는 3-way merge를 사용한다.

# rebase & merge 차이점

-   **merge**: 메인 브랜치로 이동 후 `git merge [브랜치명]` 실행
-   **rebase**: 작업 중인 브랜치로 이동 후 `git rebase main`을 실행, 이후 메인 브랜치에서 병합

# Git 되돌리기

## 1. git restore

파일을 이전 commit 시점으로 복구한다.

`git restore [파일명]` : 파일을 최근 커밋으로 복구한다.

`git restore --source [커밋아이디] [파일명]` : 파일을 특정 커밋으로 복구한다.

`git restore --staged [파일명]` : 특정 파일의 staging을 취소한다.

## 2. git revert

commit을 취소하는 방법이다.  
reset과 비슷하지만 소스를 유지하고 history가 쌓인다.  
흔적을 남기기위해 reset보다 revert 사용이 권장된다.

`git revert HEAD` : 최근 커밋을 취소

`git revert [커밋아이디]` : 특정 커밋을 취소

`git revert [커밋아이디1] [커밋아이디2]` : 여러개의 커밋을 취소

`git revert -m 1 [merge 커밋아이디]` : merge 완료된 커밋을 취소

## 3. git reset

`git reset [hard | soft | mixed]` : commit을 되돌리는 방법으로 협업 시 다른 사람의 코드를 없앨 수 있으므로 주의!

`git reset --hard [커밋아이디]` : 특정 커밋 시점으로 되돌리고 이후의 변동사항을 삭제

`git reset --soft [커밋아이디]` : 특정 커밋 시점으로 되돌리고 이후의 변동사항을 staging

`git reset --mixed [커밋아이디]` : 특정 커밋 시점으로 되돌리고 이후의 변동사항을 unstaged

### git reset 사용법

A, B, C 커밋이 쌓여있고 C 커밋에서 B 커밋으로 돌아가고 싶을 경우

1. git reset으로 B 커밋으로 돌아간다.

2. rollback 메시지를 남기고 commit 생성

3. 소스를 rollback commit과 똑같이 수정

4. push 하면 돌아가기 성공 (reject 당하면 -uf 옵션 또는 +브랜치로 push)

# Git 파일 삭제

파일 삭제 작업 후 Staging Area에 add한 것처럼 올라간다.  
git commit으로 파일 삭제에 대한 메시지를 남기고 git push로 작업을 완료한다.

`git rm [파일명]` : 특정 파일을 삭제한다.

`git rm [파일명1] [파일명2]` : 특정 파일1과 파일2를 삭제한다.

`git rm \*.[확장자]` : 특정 확장자인 모든 파일을 삭제한다.

`git rm -r [디렉토리명]` : 디렉토리와 하위 파일까지 모두 삭제한다.

# Git 파일명 변경

Git의 파일명을 변경한다.

```
git mv [원래 파일명] [새로운 파일명]
```

파일명이 변경이 안될 경우 한번도 git add 한 적이 없는 파일이므로 staging 후 수행하기

# Git 폴더명 변경

Git의 폴더명을 변경한다.

```
git mv [원래 폴더명] [새로운 폴더명]
```

폴더가 GitHub에 이미 올라간 상태라면 폴더명을 변경하고 커밋하면 원래 폴더가 남아있다.  
따라서, 원래 폴더를 지워줘야 한다.

```
git rm -r [원래 폴더명]
```

폴더를 삭제할 때에는 rm의 -r 옵션을 사용한다.  
-r 옵션은 폴더 안의 모든 파일과 하위 폴더를 삭제해준다.

# .gitignore 걸러진 파일 확인

.gitignore를 통해 불필요한 파일들이 Git에 올라가지 않도록 설정할 수 있다.  
이 불필요한 파일들이 잘 걸러졌는지 다음과 같이 확인한다.

```
git status --ignored
```

git bash 환경에서 사용 시 .gitignore 내용에 따라 걸러진 파일들이 붉은색으로 보인다.

# Git의 마지막 커밋 메시지 변경

Git을 사용하다보면 종종 커밋 메시지를 실수해서 변경하고 싶은 경우가 있다.  
Git의 마지막 커밋 메시지를 변경하고 싶으면 다음과 같이 입력한다.

```
git commit --amend -m "[변경된 메시지]"
```

이 명령어를 통해 마지막 커밋의 메시지를 변경된 메시지로 변경한다.
