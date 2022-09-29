### 그라데이션으로 배경 채우기
#### CSS 그라데이션
- 선형 그라데이션 : linear-gradient()
 1) to 예약어 다음에 방향을 나타내는 예약어를 최대 2개까지 사용
  `background: linear-gradient(to right bottom, #00f, #fff);`
  `background: linear-gradient(to top, #fff, #000);`
 2) 방향이나 각도 모두 생략하면 to bottom으로 인식
 - 선형 그라데이션 - 각도 :윗부분이 0deg이고, 시계 방향으로 회전하면서 증가
 `background: linear-gradient(45deg, #f50, #fff); /* 45도 (오른쪽 위)방향으로, 빨간색에서 흰색으로 */`
 - 선형 그라데이션 – 색상 중지점
  1) 색상만 지정할 수도 있고 색상과 함께 중지점의 위치도 함께 지정할 수도 있음
  2) rgba() 함수를 사용해서 불투명도를 함께 지정할 수 있음
  `background: linear-gradient(to top, #004381, #fff 40%, #99ceff);`
- 원형 그라데이션 : radial-gradient()
`radial-gradient(<모양> <크기> at <위치>, <색상 중지점>, …)`
 1) 원형 그라데이션 - 모양 circle(원형)과 ellipse(타원형); 지정하지 않으면 ellipse로 인식
 `background: radial-gradient(#fff, #f50);`
 2) 원형 그라데이션 – 색상 중지점 : 색상과 어느 부분에서 색상을 바꿀지 **위치(반지름 %)**도 함께 지정
 `background: radial-gradient(circle, #fff, yellow 30%, #f50);`
 `border-radius: 50%;`/* 사각형 원으로만들어보기 */
 - 원형 그라데이션 - 위치 : 
  1) 그라데이션이 시작하는 중심 지정(지정하지 않으면 요소의 가운데)
  2) at 키워드와 함께 위치 값 지정
  3) 사용할 수 있는 값 : 키워드나 백분율 `left, center, right; top, center, bottom`
  `background: radial-gradient(circle at 30% 15%, #fff, yellow 30%, #f50);`
- 원형 그라데이션 – 크기
 1) closest-side : 그라데이션 가장자리가 측면에 닿을때까지
 2) closest-corner : 가장가까운 가장자리 코너에 닿을 때 까지
 3) farthest-side : 가장 멀리 떨어진 측면에 닿을때까지
 4) farthest-corner : 가장 멀리 떨어진 코너에 닿을때까지
- 그라데이션 반복하기
 1) repeating-linear-gradient : 선형 그라데이션 반복
  `background: repeating-linear-gradient(yellow, red 20px);`
  `background: repeating-linear-gradient(yellow, yellow 20px, red 20px, red 40px);`
 2) repeating-radial-gradient : 원형 그라데이션 반복
 `background: repeating-radial-gradient(circle, white, #ccc 10%);`
 `background: repeating-radial-gradient(circle, white, white 10%, #ccc 10%, #ccc 20%);`
- 그라데이션으로 테두리 채우기
 `border-image: linear-gradient(#f6b73c, #4d9f0c) 30;`
- 그라데이션 제너레이터
 [css gradient generator](https://gradient-designer.csspost.com/)
 [css gradient](https://cssgradient.io/)

### 선택자 연결해서 사용하기
#### 하위, 자식, 형제, 인접, 연결 선택자
- 하위 선택자(descendant selector)- space
 `#container ul {border:1px solid blue;}`
- 자식 선택자(child selector)- >
 `#container > ul {border:1px solid blue;}`
 - 형제 선택자와 인접 형제 선택자- ~
 `h2 ~ p {font-style: italic;}`
 - 인접 형제 선택자- +
 `h2 + p {color: red;}`
#### 속성 선택자
- [ ] 안에 지정한 ‘속성’이 있는 요소를 찾아 스타일 적용
 `input[readonly] background-color:#eee;}`
 `input[required] {border-color:#f00;}`
 - [속성 = 값] 선택자 :주어진 속성과 속성 값이 일치하는 요소를 찾아 스타일 적용
 `input[type="text"],input[type="password"] {width:300px;
height:30px;}`
- [속성 ~= 값] 선택자 : 여러 속성 값 중에 해당 값이 포함되어 있는 요소를 찾아 스타일 적용
값이 한 단어여야 함
```
[class ~= “button”] /* class=“button-1” 는 선택안됨 */
```
- [속성 |= 값] 선택자 : 특정 값이 포함된 속성을 가진 요소를 찾아 스타일 적용
하이픈으로 연결해 한 단어 값을 이루는 요소도 선택
 `input[id ~="user"] {background-color:#b4fdb4;}`
- [속성 ^= 값] 선택자 : 특정 값으로 시작하는 속성을 가진 요소를 찾아 스타일 적용
단어가 아니라 값의 일부만 지정해도 됨
 `a[href ^= “http”]`
 - [속성 $= 값] 선택자 : 특정 값으로 끝나는 속성을 가진 요소를 찾아 스타일 적용
 `a[href $= “.gif”]`
#### 가상 선택자 :슈도 셀렉터(pseudo selector)
웹 문서 소스에는 존재하지 않지만 필요에 따라 가상의 선택자를 만듦
- 가상 클래스 선택자(콜론 : 뒤에 선택자 이름 붙임) 
 1) :link - 방문하지 않은 링크에 스타일 적용
 2) :visited - 방문한 링크에 스타일 적용
 3) :active - 웹 요소를 활성화했을 때의 스타일 적용
 4) :hover - 웹 요소에 마우스 커서를 올려놓을 때의 스타일 적용
 5) :focus - 웹 요소에 초점이 맞추어졌을 때의 스타일 적용(tab키로 선택)
 6) 순서 L --> V --> H --> A
```python
  <style>
  ……
  nav a:link,
  nav a:visited{
  display:block;
  font-size:14px;
  color:#000;
  padding: 10px;
  text-decoration: none;
  text-align: center;
  }
  nav a:hover,
  nav a:focus {
  background-color:#222;
  color:#fff;
  }
  nav a:active {
  background-color:#f00;
  }
  </style>
```
- 요소 상태에 따른 가상 클래스 선택자
 1) :target – 앵커로 연결된 부분에 스타일 적용
 `#intro:target {background-color:#0069e0;color:#fff;}`
 2) :enabled, :disabled – 요소의 사용 여부에 따라 스타일 적용
 `#signup input[type="text"]:hover,
#signup input[type="tel"]:hover {
border-color: #f00;}`
 3) :checked – 라디오 버튼이나 체크 박스에 체크했을 때 스타일 적용
 `#signup input:checked + label {
color:red;font-weight:bold;`
}
 4) :not – 특정 요소를 제외하고 스타일 적용
 `#signup input:not([type=radio]) `
- 문서 구조에 따른 가상 클래스 선택자
 1) :first-child /자식 요소 중에서 첫번째일 때 선택
 2) :last-child /자식 요소 중에서 마지막일 때 선택
- 문서 구조에 따른 가상 클래스 선택자
 1) A:first-of-type /자식 요소 중에서 첫번째를 선택
 2) A:last-of-type /자식 요소 중에서 마지막에 있는 요소를
선택
- 문서 구조에 따른 가상 클래스 선택자
 1) :only-child /자식 요소가 유일할 때
 2) :only-of-type /자식 요소 중에서 해당 유형이 유일할 때
 - 문서 구조에 따른 가상 클래스 선택자
  1) 수식을 사용해 위치 지정하기(:*n*th-child(*n*), :*n*th-last-child(*n*), A:*n*th-of-type(*n*), A:*n*th-last-of-type(*n*))
 `#contents :nth-child(3) {
background-color:#ffff00;}`
 `table tr:nth-child(2n+1) {
background:lightgray;
color:black;}`
 `table tr:nth-child(odd) {
background:lightgray;
color:black;}`
- 가상 요소 : 화면 꾸미기용 요소를 화면에만 보여주고, 웹 문서 자체에는 포함시키지 않기 위해 가상 요소 사용(주로 ::before와 ::after를 많이 사용함)
 1) ::first-line : 특정 요소의 첫번째 줄에 스타일 적용
 2) ::first-letter : 특정 요소의 첫번째 글자에 스타일 적용
 3) ::before : 특정 요소의 앞에 지정한 콘텐츠 추가
 3) ::after : 특정 요소의 뒤에 지정한 콘텐츠 추가
 4) ::selection : 마우스로 선택한 부분의 스타일 지정
 #### CSS 변수
 자주 사용하는 색상이나 글자 크기 등을 미리 변수로 정의

 - 변수 선언 : 문서 전체에서 사용할 CSS 변수를 선언할 때는 :root 선택자를 사용합
```
  :root {
  --bg-color: #eee;
  }
  body {
  background-color: var(--bg-color);
  }
  button {
  background-color: var(--bg-color);
  }
```











 

 
