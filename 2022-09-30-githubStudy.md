### gitbub 관련 내용정리

#### 주요명령어
```
  commit	
  branch	
  checkout     // switch, retore로 분리		
  cherry-pick	
  reset	
  revert 
  rebase	
  merge
  pull = fatch + merge
```
#### Vim 사용법
```
  입력 시작	i(insert)	명령어 입력 모드에서 텍스트 입력 모드로 전환
  입력 종료	ESC	텍스트 입력 모드에서 명령어 입력 모드로 전환
  저장 없이 종료	:q	
  저장 없이 강제 종료	:q!	입력한 것이 있을 때 사용
  저장하고 종료	:wq	입력한 것이 있을 때 사용
  위로 스크롤	k	git log등에서 내역이 길 때 사용
  아래로 스크롤	j	git log등에서 내역이 길 때 사용
```
#### 실습사이트
[실습 사이트1](https://github.com/Violet-Bora-Lee/git-tutorial)

[실습 사이트2](https://learngitbranching.js.org/)

[실습 사이트3](https://git-school.github.io/visualizing-git/)

#### 몇가지 명령어 사용 예
```
  git reflog 명령어를 사용해 HEAD가 가리키던 커밋 이력을 볼 수 있음
  git checkout main  	캐럿은 한단계 부모 위치로 이동
  git checkout HEAD~4 	HEAD는 4단계 부모로 이동
  git branch -f main HEAD~3	main을 강제이동(메인이 아닌 branch에서 사용)
```

#### git에서 과거로 돌아가는 두 방식
reset : 원하는 시점으로 돌아간 뒤 이후 내역들을 지움
revert : 되돌리기 원하는 시점의 커밋을 거꾸로 실행
#### Merge 관련
1. base가 같으면 Fast-forword
2. base가 다르면 merge commit을 생성하여 auto merge (conflict는 스스로 처리)

3. github Pull Requeset에서 merge할수있는 3가지 방법: 
```
  create a merge commit
  squash and merge 
  rebase and merge
```
4. merge 옵션 예
```
  git checkout main
  git merge --no-ff feature  /가독성 좋음/
  git checkout main
  git merge --squash feature /하나로 합쳐져서 세세한 구분이 힘듬/
  git commit -m "squash merge message"
```

#### rebase 관련 : /Base를 재 설정 하여 합치는것 /일종의 복사 /깨끝한 커밋/ 
```
  git checkout feature  
  git rebase master	/최상단에 복사 붙여넣기, 한줄로 모든 커밋이 저장됨/
  git remote add "branch name" 원격지 주소
  git fetch "branch name" main
  git rebase "branch name"/main
```
#### Cherry-pick : 다른 브랜치에 있는 커밋을 선택적으로 내 브랜치에 적용시키는것/
```
  git checkout main
  git cherry-pick e19c319
  git push origin main
```
: 실제 사용 예
```
  git checkout main
  git checkout -b cherry
  git cherry-pick e19c319(hash)
  git push origin cherry --> githubweb에서 Merge pull request로 main에 merge
  git cherry-pick e19c319(hash) 
```
#### 10월2일 연습
[강의교재](https://www.yalco.kr/@git-github/4-4/)

[동영상강의](https://www.yalco.kr/@git-github/1-1/)

- 초기셋팅
```
  git config --global user.name
  git config --global user.email
  git config --global core.autocrlf true
  git config --global init.defaultBranch main
```
```
  git commit -am "message" add+message 단 신규생성이 아닌 있는 파일경우적용
  git reset --hard dfsdfs(hash) reset은 이후 생성 로그를 지우고 과거(hash시점)로 되돌리는 것
  git revert fsdfs(hash) revert는 이후 생성 로그를 지우지 않고 과거(hash시점)을 최후 로그로 되돌리는 것
  git revert --no-commit fsdfs(hash) commit이 안된상태로 revert
  git swich -c new_branch checkout > switch, restore로 분리 이전의 
  git checkout -b new_branch 명령과 같음.
  git branch -d 브랜치명  브랜치명 지우기, 강제삭제(다른브랜치로 적용안된 새로운 커밋이 포함)는 -D 사용
  git branch -m 기존브랜치 새브랜치  브랜치 이름바꾸기
  git log --all --decorete --oneline --graph 브랜치 내역보기
```
1) merge는 main 브랜치로 이동후 실행
```
  git switch main
  git merge 머지할브랜치명
  
  머지중 중단
  git merge --abort
  git merge --continue //머지중 충돌하면, 충돌 해결 후 add commit 해야함. 
  git add 출돌해결파일
  git commit -m "커밋내용"
  git branch -d 머지브랜치  // 머지한브랜치 삭제
```
2) rebase는 리베이스할 브랜치로 이동후 실행
```
  git switch rebasebranch 리베이스할 브랜치로 이동
  git rebase main //rebasebranch를 main으로 가지이어 붙여 넣기 하여 기존의 가지가 없어짐.
  git switch main // 머지하기위해 main으로 이동
  git merge rebasebranch   아직 HEAD가 이전에 있기 때문에 rebase한곳으로 이동해야함. 
  git branch -d rebasebranch rebase된 브랜치삭제

  리베이스중 중단 시
  git rebase --abort
  git rebase --continue

  리베이스중 충돌하면, 충돌 해결 후
  git rebase --continue 해야하고, 충돌해결후 add commit 해야함. 
  git switch main                 머지하기위해 main으로 이동                    
  git merge 리베이스브랜치명  아직 HEAD가 이전에 있기 때문에 rebase한곳으로 이동해야함.
  git branch -d 리베이스브랜치명
```

#### 공동프로젝트
- main settings에서 Developer settings(Settings / Developer settings) 
- Personal access tokens/ Generate a personal access token을 생성하여 반드시 메모장 등에 복사
- 설정은 우선 repo만 선택
- windows 자격증명관리자에서 github를 찾아 패스워드에 token을 붙여넣기
- 새로운 repository를 만들고 
- repository settings에서 
- collaborators(Manage access)를 클릭하여 팀원을 추가

##### 1) 원격 저장소 사용하기
```
  git remote add origin (원격 저장소 주소) 
  git branch -M main
  git push -u origin main  이후 push하면 자동으로 origin main으로 됨
```
##### 2) push 할 것이 있을 시 pull 하는 두 가지 방법
```
  만일 원격에 누군가가 커밋한 상태있고, 나는 로컬에 커밋할 내용이 있을경우 

  git pull --no-rebase  pull = fatch+merge 이므로 merge 방식
  git pull --rebase      rebase 방식 먼저 메인으로 재배치되어  pull 상의 rebase는 다름 (협업시 사용 OK) pull 방식
  git push               내가 수정한 사항이 수정됨   
  pull 상의 rebase는 다름 (협업시 사용 OK)

  원격지 변경내용산관없이 내로컬의 내용을 강제 푸시 할때(사전에 합의된경우)
  git push --force //주의 일반적으로 사용하지 않음 
```
##### 3) 원격의 브랜치 다루기 
```
  전체(원격,로컬) 브랜치 보기

  git branch --all
  git branch --a
  
  아래 명령어로 원격의 변경사항 확인
  git fetch
  
  아래 명령어로 로컬에 같은 이름의 브랜치를 생성하여 연결하고 switch
  git switch -t origin/from-remote
  git push (원격 이름) --delete (원격의 브랜치명) 원격의 브랜치 삭제
```
##### 4) .ignore 파일내용은 무시할 내용을 적습니다. 
```
  file.c /*파일명 입력*/
  *.c  /*확장자 입력*/
  !not_ignore_this.c /*예외파일-즉 무시하지 않고 포함할 파일*/
  logs /*logs 파일 및 폴더*/
  logs/ /*logs 폴더*/
  logs /*.c /*logs 폴더안의 .c 파일 무시*/
  logs /*debug.log` /*logs 폴더 및 하위폴더의 debug.log파일 무시*/
```