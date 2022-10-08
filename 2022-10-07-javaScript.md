### javascript
- 자바스크립트의 특징
 1. 모든 웹 브라우저에서 작동한다.
 2. 웹 브라우저에서 실행 결과를 즉시 확인할 수 있다.
 3. 풀스택 웹 개발 뿐 아니라 다양한 용도의 프로그램을 만들 수 있다
 4. 다양한 자바스크립트 공개 API를 사용할 수 있다
 5. 다양한 라이브러리와 프레임워크를 사용할 수 있다
 6. [카카오 맵 API 예](https://apis.map.kakao.com/)

- 콘솔 창에서 자바스크립트 사용하기
 1. 웹 브라우저 주소 표시줄에 about:blank 입력해서 빈 화면 표시
 2. 웹 개발자 도구 창에서 [콘솔] 선택
(윈도우 [Ctrl]+[Shift]+[J] , 맥 [Option]+[Comman]+[J] 단축키 주로 사용)
 3. 10 + 20 입력
 4. console.log(“안녕하세요?”) 입력

- 자바스크립트 소스를 작성할 때 지켜야 할 규칙
 1. 대소문자를 구별하여 소스를 작성한다
 2. 읽기 쉽게 들여쓰는 습관을 들인다
 3. 세미콜론으로 문장을 구분한다
 4. 소스에 메모하려면 주석을 사용한다
```
  // 한 줄 주석
  /* 여러 줄
  주석도 사용할 수 있습니다. */
```
 5. 식별자는 정해진 규칙을 지켜 작성한다
 6. 예약어는 식별자로 사용할 수 없다

- 자바스크립트 소스를 작성할 때 지켜야 할 규칙
 1. 식별자는 정해진 규칙을 지켜 작성한다
 2. 첫 글자는 반드시 영문자나 밑줄(_), 달러 기호($)로 시작
 3. 두 단어 이상이 모여 하나의 식별자를 만들 경우 하이픈(-)이나 밑줄(_)로 연결. 공백은 사용할 수 없음
 4. 예약어는 식별자로 사용할 수 없다

 - 자바스크립트 스타일 가이드 : 코딩 규칙을 ‘스타일 가이드’, ‘코딩 컨벤션‘, ‘코딩 스타일‘, ‘표준 스타일‘ 등으로 부름
 1. 구글 자바스크립트 스타일 가이드 (google.github.io/styleguide/jsguide.html) 
 2. 에어비앤비 자바스크립트 스타일 가이드(github.com/airbnb/javascript) 
 3. 회사 프로젝트의 경우 팀 내에서 상의해서 결정

 [Airbnb JavaScript 스타일 가이드() {](https://github.com/ParkSB/javascript-style-guide)

- 자바스크립트 소스를 작성하는 기본 규칙 
1. 코드를 보기 좋게 들여쓴다
```
  • ‘Tab’ 키나 ‘스페이스바’를 눌러 2칸이나 4칸 들여씀
  • 최근에는 공백 2칸 들여쓰기를 많이 사용함
```
2. 세미콜론으로 문장을 구분한다

```
  • 세미콜론을 붙일 것을 권장함
  • 소스는 한 줄에 한 문장만 작성하는 것이 좋다
```

3. 공백을 넣어 읽기 쉽게 작성한다
```python
  • 식별자나 연산자, 값 사이에 공백을 넣어 읽기 쉽게 작성한다
```
4. 코드를 설명하는 주석을 작성한다
```
  • 한 줄 주석 : 슬래시 2개(//) 바로 뒤에 작성
  • 여러 줄 주석 : 여는 기호(/*)를 맨 앞에, 닫는 기호(*/)를 맨 뒤에 넣고 그 사이에 주석 내용을 작성
  • 주석 사이에 또다른 주석을 넣을 수 없음
```
#### 웹 문서에서 스크립트 작성하기
1. 자바스크립트 처리기는 웹 브라우저 안에 포함되어 있기 때문에 자바스크립트 소스는 웹 문서에 작성하면 웹 브라우저가 해석함.
2. 자바스크립트 소스는 웹 문서 안에 직접 작성할 수도 있고,
3. 자바스크립트 소스만 따로 파일로 저장해서 서로 연결해서 사용할 수도 있다

- 인라인 스크립트
1. HTML 태그 안에 직접 작성하는 자바스크립트 .
2. 팝업 창을 열고 닫거나, 알림 메시지를 표시할 때처럼 간단한 명령을 처리할 경우 인라인 스크립트를 자주 사용
```
  <body>
  <button onclick = "alert('알림 메시지가 표시됩니다.')">클릭!</button>
  </body>
```
- 내부 스크립트
1. 웹 문서에서 `<script>` 태그와 `</script>` 태그 사이에 실행할 자바스크립트 소스 작성
2. `<script>` 태그는 웹 문서에서 모든 곳에 위치할 수 있고 삽입된 위치에서 바로 스크립트가
실행됨
3. 한 문서 안에 여러 개의 `<script>` 태그를 사용할 수 있음
4. 내부 스크립트는 주로 `</body>` 태그 앞에 사용함
```
  <body>
  <script>
  alert("안녕하세요?");
  </script>
  </body>
```
```
  <body>
  <button onclick="hello()">클릭</button>
  <script>
  function hello(){
  let user = "고경희";
  alert(user + "님, 안녕하세요?");
  } 
  </script>
  </body>
```
- 내부 스크립트의 단점 : 소스 수정시모든 문서를 다 찾아다니면서 하나씩 수정해야 함.
 1. 자바스크립트 소스를 작성할 때 외부 스크립트 파일로 저장해서 링크하는 방법을 많이 사용함.
 2. 마크업과 구별되기 때문에 스크립트 소스를 관리하기 쉬움

- 외부 스크립트 연결해서 사용하기
 1. 외부 스크립트 파일 확장자 : .js
 2. HTML 문서에서 `<script>` 태그를 사용해서 외부 스크립트 연결
```
  기본형:
  <script src=“스크립트 파일 경로”></script>
```
 3. 외부 스크립트 파일 안에는 `<script>` 태그 없이 자바스크립트 소스만 작성함
 4. 따로 js 폴더를 만들어 저장하는 것이 좋음 (외부 css 파일을 css 폴더에 저장하는 것처럼~)

 - 외부 스크립트 사용해서 인사하는 브라우저 만들기
  let user = prompt('이름을 입력하세요. ');
  alert(`안녕하세요, ${user}님!`);
``백팃 기호`

- alert() 함수
1. 알림 창 표시 (앨럿 창이라고도 함)
2. alert() 함수의 괄호 안에 메시지를 입력하거나 변수를 사용
- confirm() 함수
1. 확인 창 표시 (컨펌 창이라고도 함)
2. [확인] 버튼과 [취소] 버튼이 있어서 사용자가 어떤 버튼을 클릭했는가에 따라 다르게 동작하도록 할 수 있습니다
- prompt() 함수
1. 프롬프트 창
2. 사용자가 간단한 값을 입력할 수 있는 창 표시
3. 프로그램 실행에 필요한 값을 받을 때 자주 사용
4. 기본 값을 지정하지 않으면 텍스트 필드가 빈 상태로 표시됨
- console.log() 함수
1. 콘솔 창에 괄호 안의 내용을 표시함
2. 자바스크립트 소스를 작성하면서 중간중간에 프로그램이 제대로 동작하는지 확인하는 용도로 자주 사용
3. 콘솔 창에 결과를 표시하는 함수는 많지만 주로 console.log()를 많이 사용함
4. 괄호 안에 텍스트나 변수를 사용할 수 있음
- document.write() 함수
1. document.write()는 괄호 안의 내용을 웹 브라우저 화면에 표시한다.
2. 실제 웹 브라우저 화면 에 내용을 표시할 때에는 DOM을 이용
but, 우리는 아직 DOM을 공부하지 않았기 때문에 일단 document.write() 함수를 사용.
3. doument.write()문에서 연결 연산자(+)를 사용할 수도 있고, 템플릿 리터럴 을 사용할 수도
있다
```
  name = "도레미"
  document.write("제 이름은 " + name + "입니다.")

  name = "도레미"
  document.write(`제 이름은  ${name} 입니다.`)

```
#### 자바스크립트 변수
