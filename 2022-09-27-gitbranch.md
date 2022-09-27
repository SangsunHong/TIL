### 2022-09-27

- 웹프로그래밍 기획과 기본
- Branch 병합시 충돌(conflict) 해결법

`git status`

`git add FileName`

`git commit` (Merge 기본 메세지가 있으므로 따로 작성할 필요 없음)

`git log`로 커밋 이력을 출력하여 병합이 제대로 이루어졌는지 확인
Git Branch를 활용한 작업 순서도
master/main 브랜치로 전환

```
git checkout main
git switch main

```

- 원격 저장소의 master/main 브랜치에서 내려받기 (동기화)

`git pull origin main`

작업 브랜치 생성

`git branch BranchName`

작업 브랜치 변경

`git checkout BranchName`
`git switch BranchName`
소스 코드 수정 후 저장

수정한 파일을 스테이징 영역에 올리기

`git add FileName`

commit 만들기
`git commit -m "Commit Message"`

원격 저장소에 브랜치 생성하고 동기화
`git push -u origin BranchName`

Github 사이트에서 Pull Request 생성
`New pull request`

병합 방향 설정
`Create pull request`
