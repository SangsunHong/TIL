### gitbub 관련 내용정리

#### 주요명령어
```
  commit	
  branch	
  checkout		
  cherry-pick	
  reset	
  revert 
  rebase	
  merge
  pull= fatch+merge
```

#### 실습사이트
[실습 사이트1](https://github.com/Violet-Bora-Lee/git-tutorial)
[실습 사이트2](https://learngitbranching.js.org/)
[실습 사이트3](https://git-school.github.io/visualizing-git/)

#### 몇가지 명령어 사용 예
`git reflog` 명령어를 사용해 HEAD가 가리키던 커밋 이력을 볼 수 있음
`git checkout main^`  	캐럿은 한단계 부모 위치로 이동
`git checkout HEAD~4` 	HEAD는 4단계 부모로 이동
`git branch -f main HEAD~3`	main을 강제이동(메인이 아닌 branch에서 사용

#### Merge 관련
1. base가 같으면 Fast-forword
2. base가 다르면 merge commit을 생성하여 auto merge (conflict는 스스로 처리)
3. github Pull Requeset에서 merge할수있는 3가지 방법: 
 1) create a merge commit
 2) squash and merge 
 3) rebase and merge
4. merge 옵션 예
`git checkout main`
`git merge --no-ff feature`  /가독성 좋음/

`git checkout main`
`git merge --squash feature` /하나로 합쳐져서 세세한 구분이 힘듬/
`git commit -m "squash merge message"`

#### rebase 관련 : /Base를 재 설정 하여 합치는것 /일종의 복사 /깨끝한 커밋/ 
`git checkout feature`  
`git rebase master`	/최상단에 복사 붙여넣기, 한줄로 모든 커밋이 저장됨/

```
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
```python
  git checkout main
  git checkout -b cherry
  git cherry-pick e19c319(hash)
  git push origin cherry --> githubweb에서 Merge pull request로 main에 merge
  git cherry-pick e19c319(hash) 
```