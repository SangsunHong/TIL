### 애니메이션
#### CSS 애니메이션
1. @keyframes 속성 : 애니메이션의 시작과 끝을 비롯해 상태가 바뀌는 지점을 설정
```
  @keyframes shape {
  from { 
  border: 1px solid transparent; 
  }
  to {
  border: 1px solid #000; 
  border-radius: 50%; } }
```
2. animation-name, animation-duration
 - animation-name 속성 : 어떤 애니메이션을 사용할지 구별, @keyframes 속성에서 만든 애니메이션 ‘이름’을
사용
 - animation-duration 속성 : 애니메이션 실행 시간 설정. 기본값 0, 사용 가능한 값은 초(s)나 밀리초(ms)
```
  #box1 {
  background-color: #4cff00; 
  border: 1px solid transparent; 
  animation-name: shape; 
  animation-duration: 3s; }
```
3. animation-iteration-count 속성 : 애니메이션 반복 횟수 지정하기
4. animation-timing-function 속성 : 애니메이션 시작과 중간, 끝에서의 속도 지정, 트랜지션에서, transition-timing-function과 같음
5. animation-direction 속성 : 애니메이션은 원래 keyframes에서 정의한 from에서 to 순서로 진행하는데, 
animation-direction 속성을 사용해 진행 방향을 바꿀 수 있음
6. animation 속성 : 여러 개의 애니메이션 속성을 하나의 속성으로 줄여서 사용, animation-duration 속성 값은 반드시 지정해야 함
```
  #box1 {
  background-color: #4cff00;
  border: 1px solid transparent;
  animation: translate 3s alternate infinite; }
```
#### 반응형 웹 디자인
1. 반응형 웹 디자인 : 화면 크기에 ‘반응’해 화면 요소들을 자동으로 바꾸어 사이트를 구현하는 것이 바로 반응형 웹 디자인
 - 장점
• 기기의 화면 크기나 해상도에 구애받지 않음
• 화면의 변화에 즉시 반응
• 어느 기기에서든 사이트 주소가 같다
• 유지 관리가 편하다
• 최신 웹 표준을 따른다
 - 단점
• 예전 브라우저 버전과의 호환성 문제
• 사이트 디자인이 단순하다.
2. 반응형 웹 디자인 패턴
 - 유동형 패턴
 - 칼럼 드롭 패턴
 - 레이아웃 이동 패턴
 - 캔버스 밖으로 패턴
3. 반응형 웹을 구현하는 여러 가지 방법
 - 미디어 쿼리
 - 부트스트랩(Bootstrap). getbootstrap.com
4. 뷰포트(viewport) : 스마트폰에서 실제 콘텐츠가 표시되는 부분
5. 가변 레이아웃
 - CSS3의 기술들
• 미디어 쿼리(Media Query)
• 플렉서블 박스(Flexible Box) 또는 플렉스 박스(Flex box)
• CSS 그리드 레이아웃 (CSS Grid Layout)
 - 가변 레이아웃
• 간단히 각 요소의 너빗값만 늘였다 줄였다할 수 있게 만드는 방법
• 디자인이 아주 간단할 경우 편리함
• CSS3를 지원하지 않는 브라우저에서도 사용 가능
 - 고정 레이아웃 vs 가변 레이아웃
• 고정 레이아웃 : 화면 너비를 일정하게 고정한 레이아웃
• 가변 레이아웃 : 화면 너비를 % 같은 가변 값으로 지정한 레이아웃.
• 가변 레이아웃을 사용할 경우, 너비 값이 줄어들면 실제 콘텐츠를 확인하기 불편하므로
가능하면 간결한 디자인을 사용하는 것이 좋음.
 - 그리드 시스템이란
• 화면을 여러 개의 칼럼(column)으로 나누어, 필요할 때마다 칼럼들을 묶어 배치하는 방법
• 화면 너비 값에 따라 ‘960 그리드 시스템’, ‘1200 그리드 시스템‘ 등으로 나뉨
• 칼럼 개수에 따라 ’12 칼럼 그리드 시스템‘, ‘16 칼럼 그리드 시스템‘, ‘24 칼럼 그리드 시스템‘ 등으로 나뉨
• 주로 960 픽셀 12 칼럼의 그리드 시스템 사용

#### 미디어 쿼리
1. 미디어 쿼리(media queries) : 접속하는 장치(미디어)에 따라 특정한 CSS 스타일을 사용하는 방법 [미디어 쿼리를 이용해 제작된 사이트](http://mediaqueri.es)
2. 미디어 쿼리 구문
• @media 속성을 사용해 특정 미디어에서 어떤 CSS를 적용할 것인지 지정함
• <style> 태그와 </style> 태그 사이에 사용
3. 미디어 유형
 - 조건 – 뷰포트 크기 : 새로운 모바일 기기가 계속해서 등장하는데 모든 기기의 해상도와 뷰포트 크깃값을
다 기억할 수도 없고, 모든 기기에 맞출 수도 없다
[viewport](https://yesviz.com/devices.php)
 - 조건 – 단말기 크기 : 많이 사용하는 조건은 아님. 주로 뷰포트 크기를 조건으로 사용
 - 조건 – 화면 회전 : 스마트폰이나 태블릿에서 기기를 가로나 세로로 돌려보는 지 확인
 - 미디어 쿼리 중단점
 • 스마트폰: 모바일 페이지는 미디어 쿼리를 사용하지 않고 기본 CSS로 작성. 
스마트폰의 방향까지 고려할 경우 : portrait 320px, landscape 480px)
• 태블릿: 세로 크기가 768px 이상이면 태블릿으로 지정. 가로 크기는 데스크톱과 똑같이
1024px 이상으로 지정.
• 데스크톱: 화면 크기가 1024px 이상이면 데스크톱으로 설정.
(여기에서 스마트 TV를 추가할 수도 있음)
4. 미디어 쿼리 적용하기 – 문서 안에서 직접 정의하기
```
  @media screen and (max-width: 768px) {
  body { background: orange; }
  }
  @media screen and (min-width: 769px) and 
  (max-width: 1024px) {
  body { background: green; }
  }
  @media screen and (min-width: 1025px) {
  body { background: #12abcd; } }
```





