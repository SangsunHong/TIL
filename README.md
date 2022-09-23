# TIL

# Today I Learned

> > 매일매일 공부한 것을 기록합니다.

## 전체과정 : Python, SQL, R, RPA, WEB 과정으로 진행 : 2022.05.10 ~ 2022.11.07(6개월)
# RPA(Robotic Process Automation)
## 유아이패스(UiPath) 커리큘럼

### RPA는 Robotic Process Automation으로 로봇과 같은 자동화처리시스템을 말한다.
### 4차산업혁명과 인공지능시대에 유용한 솔루션이라고 생각하며, 코로나19 확산으로 크게 발전하였다.

### 그러나 인공지능과 연계되는 부분은 아직 속제로 남아있으며, 최근에 핫한 분야라 할 수 있다.

### 2021년 국내시장은 약1000억원 규모이며, 선두주자 제품은 유아이패스(UiPath)와

### 오토메이션애니웨어(Automation Anywhere)가 있다

![image](https://user-images.githubusercontent.com/54345891/190119182-8bab19c8-b9c5-40cc-a3d2-b8ecb9b34821.png)

## 9월08일 HTML5
- 그동안 보기만했던 웹 개발을 시작하였다.
- HTML5는 웹기술의 종합 완성품이다.
- 또한 이전과 같은 단순한 웹페이지가 아니고, 모든 장치와 연결하여 정보를 제공하는 플랫폼이다.

### 앞으로 HTML, CSS, Javascript를 배울것이다
- meta 태그 : 문서의 각종정보를 전달하는 중요한 테그
- CSS(cascading style sheets) : 웹 문서의 전반적인 스타일을 미리 저장해 둔 스타일시트
- 자바스크립트(JavaScript) : 웹 페이지에서 사용자로부터 특정 이벤트나 입력 값을 받아 동적인 처리를 목적으로 고안된 객체 기반의 스크립트 프로그래밍 언어
### 웹개요 : HTML 기본구조

- 주요테그 title, meta, link, hn, p, img, header, nav, link, main, div, article, section, aside, footer 등
- 오픈그래프(sns공유 하도록 설정) : meta property="속성 이름" content="속성 값"
- 파비콘은 favirote icon의 약어로 title 아이콘으로 사용한다. [파비콘 사이트](https://www.favicon-generator.org/)
### 태그와 요소(element, 엘리먼트) 차이

- 태그(tag)는 마크업을 위해 약속한 기호
- 요소(element)는 태그와 내용을 함께 묶어서 부르는 용어

## 2022-09-13 github 기초/ 이보라강사님
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
[googlelink]: https://google.com "Go google"
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
-리포? 라고 줄임말을 사용한다.

## Git Bash 세팅하기
- [깃 최초설정](https://git-scm.com/book/ko/v2/%EC%8B%9C%EC%9E%91%ED%95%98%EA%B8%B0-Git-%EC%B5%9C%EC%B4%88-%EC%84%A4%EC%A0%95)

  ```python
  - $ git config --global user.name "John Doe"
  - $ git config --global user.email johndoe@example.com
  - $ git config --global core.autocrlf true
  ```
#### 리포지토리
- 정의: 여러파일을 하나로 모은컬렉션
- 일반디렉터리와 디포지터리의 차이 .git
- 주요명령어 // 복사 shift + insert

  ```python
  git status
  git checkout 번호 : 특정시점으로 돌아가기
  git checkout main : 원래대로 돌아가기
  git clone https://github.com/SangsunHong/TIL.git
  git rebase
  git push origin main
  git log
  git reset --hard "hash"   /hash 없으면 마지막상태로 돌아감 git reset --hard
  git revert " hash"
  git revert --no-commit "hash"
  git branch add-coach
  git branch
  git switch add-coach
  git checkout            /git 2.23부터 switch, restore로 분리
  git switch -c new-team  /기존 git checkout -b new-team
  git branch -d           /브렌치삭제
  ```
## 9월14일
### 텍스트 관련 태그
- h1~h6, p, br, hr(가로줄), blockquote(인용문 넣기), pre, strong, b, em(기울임), i, cite
- ul(순서 없는 목록), ol(순서 목록), li(list), dl(설명 목록), dt, dd
- 기타 태그 : address, time, span(영역 묶기-인라인 레벨 형태로 소스를 묶음), div(블록 레벨 형태로 소스를 묶음)
### 이미지 관련 태그
- img src="이미지파일" alt="이미지설명텍스트">, 이미지(gif, jpg/jpeg, png)
- width, height 속성: %(화면크기에 자동변환), px(픽셀크기)
- 이미지에 캽션 붙이기: figure태그(img태그를 figure태그로 감싼다)와 figcaption태그(이미지설명)
### 표 관련 태그
- table(표전체), caption(표제목), tr(행-table row), td(셀-table data), th(제목셀-table heading)
- thead, tbody, tfoot(안쓰는경우도 있음)
- 표 편집: col, colgroup – 열끼리 묶어 스타일 지정; rowspan(행합치기), colspan(열합치기)
## 9월15일
### 웹과 멀티미디어
- 새로운 이미지추가방법 : srcset(img src="이미지" srcset="이미지[,이미지1, 이미지2, .....])-다양한크기의 이미지 브라우저(기기)에 따라 자동선택
- picture, source태그(picture태그안에 이미지(크기포함)지정)
- 오디오코덱 : AAC, Aorbis, mp4/m4a, mp3(사실상표준)
- 비디오코덱 : mp4, webm
### 오디오 비디오 삽입하기
- 비디오 오디오 태그 : embed(최신 비디오, 오디오 태그를 지원하지 않는 브라우저에서 사용), obejct태그(다양한 개체 삽입-pdf 등)
- audio태그(audio src="오디오파일" controls)
- video태그(video src="비디오파일" width="700“ controls)
- 공통속성: controls(컨트롤바 생성), autoplay, loop, muted, preload, width, height, poster="파일이름"(재생전 표시될 포스터)
- video태그(동영상의 크기와 기타 속성), source태그(코덱에 따라 달라지는 동영상 파일의 위치)
- 텍스트 링크 : p태그로 감싸고 a href="링크주소"링크이름 또는 이미지(img src="이미지파일" alt="html로고"
- target="\_blank" 해당 미디어가 새탭으로 열림
### 나의 첫번째 웹개발 및 호스팅(나의 간략소개)
- 닷홈 사이트에 가입
- 파일질라 프로그램설치
- 나의 첫번째 웹개발 및 호스팅(나의 간략 소개)
  [나의 간략소개 링크](http://mysshong.dothome.co.kr/)
## 9월16일
### 폼(form)
- 폼에서는 텍스트 필드, 체크박스, 버튼 등 역할마다 다른 소스를 사용해야 함
- form태그의 속성 : action(form태그안의 내용을 처리할 서버 프로그램 지정)
- method(method = ”get”을 사용하면 서버로 넘기는 값이 주소표시줄에 드러남, ”post”을 사용하면 서버로 넘기는 값이 주소표시줄에 나타나지 않음)
- 폼에서 구역 나누기 : fieldset, legend
- 필드셋 테두리 없애기 : style 안에 fieldset { border: none; } legend { display: none;}
- input태그의 type 속성 값 : text, password, serch, url, email,tel, checkbox, radio, number, range, date, month, week, time, datetime-local, submit, reset, image, button,file, hidden
- text, - password필드의 속성: size, value, maxlength
- label태그 : input태그 전체를감싸거나 id값을 활용해서 label에 for 속성사용(일반적사용)
  ![image](https://user-images.githubusercontent.com/54345891/190627986-8f1f4607-2c9a-44f5-9665-2ada96e103ea.png)
- type="hidden" 사용자에게 보여지지 않음, type="serch" 갬색필드, type="tel" 전화번호, type="email" 이메일입력필드, type="url" 웹주소필드
- type="color" value="#ff0000", type="number"(속성 min,max,step,value), type="range" 슬라이드 크기조절
- type="radio" 여러항목중 하나만 선택, type="checkbox" 둘이상 선택 // 속성 name, value, checked
- 파일첨부 :type="file"
- 전송버튼 : type="submit" type="image"
- 취소(리셋) 버튼 : type="reset"
- 전송도 리셋도 아닌 일반버튼 : type="button"
- input태그의 여러 속성 : autofocus, placeholder, readonly, required
### 텍스트영역과 목록
- textarea 텍스트 영역 : 속성 cols, rows
- 드롭다운 목록(년, 월, 일 등) : select, option태그 : option태그속성 value, selected, select태그속성 size, multiple
- 데이터 목록(정해지지않은 목록) : 임의지정값 정의로 목록 추가, 메모 입력하는 텍스트영역
- iframe태그 : 외부문서, 외부사이트 삽입
## CSS
- 웹의 뼈대(HTML)에 옷을 입히는 스타일 적용 디자인(CSS)
- CSS IS AWESOME
  ![image](https://user-images.githubusercontent.com/54345891/190633202-4564d0fb-94ec-4875-bd96-ed7903aed3bf.png)
## 9월19일
- 스타일 시트:
- 내부 스타일 시트: 웹 문서 안에 스타일 시트 포함
- 외부 스타일 시트: 스타일 시트를 파일로 저장한 후 웹 문서에서 링크해서 사용
- 스타일 형식: 선택자 {속성1: 속성값1; 속성2: 속성값2;} 보기쉽게 여러줄작성, 간편하게 한줄로적성 모두가능 주석은 /_코드_/
- 외부스타일시트: link rel="stylesheet" href="css 파일경로" [링크유형참고](https://developer.mozilla.org/ko/docs/Web/HTML/Link_types) favicon.ico link rel="icon" href="favicon.ico"
- css 경량화(minify) 파일크기를줄이기위해 주석, 공백등을제거 "css minity"로 검색 [사이트예](https://www.toptal.com/developers/cssminifier)
- css 단위: 웹에서 길이 length(px, pt, in, cm, mm), css에서 길이(em, rem, vw,vh) em의 경우 depth에 따라 지나치게 커질수 있음
- color(px, )px(pixel, 픽셀)은 해상도(보통컴퓨터 1024\*768, 4k 가로세로 4000px), 16진수표기 #ffffff 2개씩묶어 줄여서 표기가능
- 기타 color 표기 방법: rgb(RedGreenBlue), rgba(+투명도); hsl/hsla 색상(hue), 채도(saturation), 밝기(light) 알파값 : 불투명도를 나타내는 값
- 타입선택자: p, div, h1 등; class, id 선택자 묶어서 사용가능
- 스타일의 우선순위: 1.사용자스타일(사용자 장치에 설정된 경우) > 제작자 스타일(웹개발) > 브라우저 기본 스타일
- 제작자 스타일 우선순위: 1.!important 2.인라인 3.id 4.클래스 5.타입
- font-family속성 기본글꼴을 이용하는 것이 좋음, font-size 속성 기본은 16px, 1em=16px, h1=2em=32px, h2=1.5em=24px, small, large를 쓰는 경우도 있음.
- font-style 속성: normal, italic=oblique; font-weight 속성: 키워드 bold bolder, lighter, 값사용 100~900, 400 nomal, 700 bold
- font-famaily로 지정한 글꼴은 사용자 시스템에 설치되어 있는 것만 사용할 수 있음; font-family : 폰트명;
- 웹 폰트: @font-face {font-family : 폰트명 지정; src : url(폰트파일) format(‘형식’), …… }
- 무료 웹 폰트를 모아놓은 사이트: [구글 폰트](https://fonts.google.com/), [네이버 한글한글 아름답게](https://hangeul.naver.com/), [어도비 폰트](https://fonts.adobe.com/)
- 부트스트랩 : 웹 사이트나 웹 응용 프로그램을 작성하기 위해 사용하는 무료 소프트웨어 도구 모음, 트위터의 개발자인 마크 오토(Mark Otto)와 제이콥 손튼(Jacob Thornton)에 의해 처음으로 개발 [부트스트랩 다운로드](https://getbootstrap.kr/docs/5.0/getting-started/download/) v5.1이 최신(2022-0919 기준)
- text-align 속성 : start, end, left, right, center, justify(양쪽을 맞춤)
- line-height 속성: 문단의 줄간격 지정, px, 글자크기(숫자,%), 보통 글자크기의 1.5~2 정도로 사용
## 9월21일 너무 많은 것을 배웠다.
### 글꼴 스타일
- color 속성
```python
   body {
    color: brown;
    }
```

- font-family 속성 : font-family에서 지정한 글꼴은 사용자 시스템에 설치되어 있어야 의도한대로 표시됨
```htm
body { font-family : “맑은 고딕“, 돋움, 굴림; }
```

- 웹폰트 설정방법
```python
    @font-face {
    font-family : 폰트명 지정;
    src : url(폰트파일) format(‘형식’),
    ……
    }
    font-family : 폰트명;
```
- text-align 속성 : start, end, left, right, center(가운데 맞추어 정열), justify(양쪽에 맞추어 정열)
- line-height 속성 : 가독성을 좋게함
- text-decoration 속성 : none(링크에서 밑줄 없앨때 사용), underline, overline. line-though
- text-shadow 속성 : 가로길이(오른쪽 +), 세로길이(아래 +), 번짐정도, 색상 /개발자 도구창에서 효과조절가능

```python
    .shadow {
    color: #000;
    text-shadow : 0px 1px 1px #fff;
    }
```
- letter-spacing(글자간 간격) 많이쓰임 , word-spacing(단어간 간격)
- text-transform 속성 : none, capitalize(첫번째 글자를 대문자로), uppercase, lowercase, full-width(전각-정사각형-문자 한글,한자 등 )
- white-space 속성 공백처리 : nomal, nowrap, pre, pre-wrap, pre-line
- text-overflow 속성 :
  overflow: hidden; // 영역을 벗어나는 내용은 화면에 보이지 않게 한다.
  white-space: nowrap; // 줄바꿈을 하지 않는다.
  text-overflow: ellipsis; // 텍스트가 잘린 부분에 …을 붙인다. ----주로사용
```python
      .toverflow {
      overflow: hidden;
      white-space: nowrap;
      text-overflow: ellipsis;
      }
```

- list-style-type 속성 : disk(●), circle(○), square(■), decimal, decimal-leading-zero, lower-roman, upper-roman, lower-alpha(latin), upper-alpha(lgitatin), hangul(가나다), none
  ```python
  list-style: hangul;
  ```
  - list-style-image 속성

```python
      ul {
        list-style:none; /* 머릿기호 밑줄없애기 */
        }
        li {             /* 가로로 메뉴구성 */
        display: inline-block;
        border:1px solid #222;
        padding:10px 20px;
        margin:5px;
        }

```
       - 표 테두리 관련 스타일

```python
        table {
        border: 1px solid #ccc;
        border-collapse: collapse;
        }
```
## 9월22일 css 박스모델(box model)의 기본 구성
 - 실제 콘텐츠 영역 : 맨안쪽
 - 패딩(padding) : 콘텐츠 영역과 테두리 사이의 여백
 - 테두리(border)
 - 마진(margin) : 요소와 요소 사이의 여백
 - width, height 속성 : px, %, auto
 - calc() 함수 : 화면 전체 너비에서 80px을 뺀 크기를 박스 모델의 너비로 지정 
      ```python
    width: calc(100% - 80px);
    ```
### 테두리 스타일 속성
 - border-style 속성 : none, hidden, solid, dotted, dashed, double, (groove, inset, outset, ridge)-양각음각
 - border-width 속성 : border-top-width, border-right-width, border-bottom-width, border-left-width(시계방향, 반대편값) 키워드 : thin, medium, thick; 크기 : px
 - border-color 속성 : border-top-color, border-right-color, border-bottom-color, border-left-color
 - border-radius 속성 : border-radius : 10px; 또는 border-radius: 50%;
 - 방향마다 다른 border-radius 지정 : border-top-left-radius, border-top-right-radius, border-bottom-left-radius, border-bottom-right-radius
 - 테두리에 이미지 넣기 : 1단계 4귀퉁이 이미지 넣기
```python
      .box {
      width:300px; 
      height: 300px;
      background-color: #eee;
      border: 36px solid orange;
      border-image-source : url('images/border.png’);
      }
```
 - 2단계 : border-image-slice 속성 : border-image-slice : 27;
 - 3단계 : border-image-repeat 속성 : border-image-repeat:  repeat; round; space;
 - 4단계 : border-image-width 속성 : border-image-width : 27px; 원래 테두리 너비보다 작게 해야함
 - 박스 외부에 테두리표시 : border-image-outset 속성  border-image-outset: 50px;
 - border-image 속성 : border-image-source border-image-slice / border-image-width / border-imageoutset border-image-repea
 - border-image 축약형 속성 :border-image: url('images/border.png') 27(slice) / 27px(width) / 50px(outset) round;
### 여백과 관련된 스타일 속성
 - padding 속성 : padding-top, padding-right, padding-bottom, padding-left(시계방향, 반대편값)  px
 - margin 속성 : margin-top, margin-right, margin-bottom, margin-left(시계방향, 반대편값) px, %, auto
 - margin 속성을 사용해 가운데 정렬하기 : margin-left와 margin-right의 속성값을 auto로 지정
 - 마진 중첩(margin overlap)이란 요소를 세로로 배치할 경우 각 요소의 마진과 마진이 서로 만나면 마진값이 큰 쪽으로 겹쳐진다
 - outline 속성 : 박스 모델 바깥에 선을 그리는 속성 outline-style : 선 모양 (필수), outline-color : 선 색상, outline-width : 선 두께, outline : 2px solid red; 
 - box-sizing 속성 : box-sizing: border-box;
 - CSS 리셋 : 브라우저 기본 스타일을 수정하는 소스 :전체 선택자(*)를 사용해 기본적인 속성만 리셋함
 - box-shadow 속성 : 수평, 수직, 흐림, 번짐, 색상, inset

 ### 포지셔닝
  - display 속성 : block, inline, inline-block, none
  - inline과 inline-block 차이 비교하기 : 위,아래쪽 마진의 차이
  - display: none(내용이 있을 경우 만 표시) / visibility: hidden 사용자가 선택 전까지 표시안함
  - float 속성 : left, right, none

## 09월23일 github
### 실전에서 github branch 일반적인 구성 5가지
 - main(master) : 실행중인 서비스
 - hotfix : 긴급버그수정
 - release : 업데이트버전 or 차기 제품 서비스준비
 - develop : 개발
 - feature : 일부 요소개발, 시험개발
### 실전 면접
 - 1분 자기소개 : 인사 / 경험(직무나 회사관련)1, 2 / 현재 직무동향, 미래 수행계획 / 마무리
 - 직무수행계획: 단기적인계획, 장기적인계획
 - 지원동기(가장중요): 회사의 가치관 / 개인경험, 회사와의 연관
 - 스크립트 사용방법(awesome 어썸 대단해요)
    1. 스크립트 간단히 제작
    2. 위파일을 다른이름으로 저장
    3. 2번에서 키워드만 추출
    4. 키워드만보고 5번말하기
    5. 5번 반복하고 1번확인

