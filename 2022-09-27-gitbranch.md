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

1. 로컬 저장소에서 새로운 브런치를 생성하고 이동함(`git checkout -b ~`)
2. 이동한 브랜치에서 원하는 파일 수정 후 저장
3. 저장한 파일을 스테이징하고(`git add ~`), 커밋 생성(`git commit -m "~"`)
4. 3번에서 만든 것을 원격 저장소에 업로드(`git push 브랜치이름 파일이름`)
5. `git push origin 브랜치이름` 으로 브랜치를 원격 저장소에 업로드
6. 원격 저장소에서 'Compare & pull request' 버튼 클릭
7. 'Create pull request' 클릭 후 메모 작성
8. 'Merge pull request'로 원격 저장소 메인브런치 병합 승인 요청
9. 최종권자가 승인('Confirm merge')
10. 원격 저장소 메인브런치에 병합 완료
11. 로컬 저장소에서 main으로 변경 후(`git checkout main`), 변경된 메인을 다시 받음(`git pull origin main`)
