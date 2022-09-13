# TIL

# Today I Learned

> > 매일매일 공부한 것을 기록합니다.

## 2022-09-13

### 과정명 RPA 1기 웹프로그래밍 기획과 기본

### 리눅스 커맨드라인 기초

#### pwd, cd, ls

#### `pwd` : print working directory

#### `cd` : change directory

#### -- 절대경로는 /로 나타냄

#### -- 상위경로는 '..'으로 나타냄

#### -- 'tab'을 사용하면 경로 자동완성이 됨

#### `ls` : list; 옵션 예) ls -a, ls -l, ls -al

#### `mkdir` : make directory

#### `history` : 과거에 쳤던명령어를 알려 줌

#### 123번째 명령어를 복구하고 싶으면 123 입력

#### vim 사용법

- 명령모드와 입력모드
- vim 에디터를 열때는 명령모드로 진입함
- 명령모드에서는 입력이불가능
- 입력을하려면 입력보드로 바꿔야함
- 키보드에서 'i' 누름
- 입력이 끄나고, 저장하고 나오려면 명령모드로 바꿔야함
- 키보드에서 esc를 눌러야함
- 끝내려면 :wq 를 입력하면 됩
- 파일명을 입력하려면 :w '파일명'
- 저장 후 끝내려면 :q
- [참고자료] [링크](https://ssayebee.github.io/wiki/how_to_use_vim.html)

#### 마크다운사용법

[link keyword][id]

[id]: URL "Optional Title here"

// code
Link: [Google][googlelink]

[googlelink]: https://google.com "Go google"

//

- vim 비정상종료시 해결방법
- vim이 비정상종료되면 'swp'파일이 생성됨
- ATTENTION 문구가뜨는경우

1. 두 프로세스, 두 사람이 동시에 한 파일을 수정하는 경우
2. crash가 나서 vim이 비정상적으로 닫힌 경우

- 기존에 입력했던 내용을 복구하고 싶을때는 vim -r 파일명을 입력하거나 Recovery모드로 진입
- 정상 종료 후, swp 파일 삭제
- rm .789.txt.swp <-- rm 명령어는 remove 약자

#### 오프라인 버전관리시스템과 git

#### 버전관리시스템을 사용하는이유

1.  실행취소, 재실행이 가능함
2.  버전간 소스비교가 가능합
3.  협업이 가능합

#### 다양한 버전관리방법

#### 커밋

- 변경이 있을때 만듬
- 가능하면 커밋크기가 작을수록 좋음

#### 리포지토리

-리포
