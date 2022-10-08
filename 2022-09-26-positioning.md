 ### 포지셔닝
  - display 속성 : block, inline, inline-block, none
  - inline과 inline-block 차이 비교하기 : 위,아래쪽 마진의 차이
  - display: none(내용이 있을 경우 만 표시) / visibility: hidden 사용자가 선택 전까지 표시안함
  - float 속성 : left, right, none
  - clear 속성 : float 속성을 해제 left, right, both 
  - 매뉴를 가로로 배치하는 방법
   1) `float:left;` // float: left로 가로로 배치시 기본 마진과 패딩이 없고, `clear`로 해제 해야 함
   2) `display:inline-block;` display: inline-block은 가로로 배치하면서도 기본 마진과 패딩을 가지고 있음

####  CSS 파일에서 브라우저 기본 스타일 리셋
```
  { 
  margin:0; /* 브라우저 기본 마진 리셋 */
  padding:0; /* 브라우저 기본 패딩 리셋 */
  box-sizing: border-box; /* 테두리까지 포함해서 박스 모델 너비로 계산 */
  }
```
#### 3단 레이아웃 만들기
```HTML
  <div id="container">
  <header>
  <h1>사이트 제목</h1>
  </header>
  <aside>
  <h2>사이드바</h2> 
  </aside>
  <section id="contents">
  <h2>본문</h2>
  </section>
  <aside id="right-sidebar">
  <h2>사이드바</h2>
  </aside>
  <footer>
  <h2>푸터</h2>
  </footer>
  </div>
```
```css
  header{
  width:100%; /* 부모 요소의 너비와 똑같게 */
  height:120px; /* 헤더의 높이 */
  background-color:#acacac; 
  }
  #left
  -sidebar {
  width: 250px; 
  height:600px; 
  background
  -color:#e9e9e9;
  float: left; 
  }
  #contents {
  width:900px; /* 본문의 너비 */
  height:600px; /* 본문의 높이 */
  background-color:#f7f7f7;
  float:left; /* 왼쪽으로 플로팅 */
  }
  #right
  -sidebar {
  width: 150px; 
  height:600px; 
  background
  -color:#e9e9e9;
  float: right; 
  }
  footer {
  width:100%; /* 부모 요소의 너비와 똑같게 */
  height:100px; /* 푸터의 높이 */
  background-color:#888888;
  clear:left; /* 플로팅 해제 */
  }
```
### 웹 요소 위치 지정
- position 속성 : static, relative, absolute, fixed

 1)absolute(부모 요소에 `position: relative;`라고 지정해야함)

 2)`fixed`(스크롤시에도 항상같은 위치)
 
- 위칫값은 어떻게 지정 : left, right, bottom, top

#### 배경 위에 글자 표시하기
- 배경 이미지가 있는 요소를 화면 중앙으로
  ```python
  <style> 
  * { … }
  #contents {
  background:url("images/bg.jpg") no-repeat;
  background-size:cover;
  width:800px;
  height:500px;
  margin: 0 auto;
  }
  </style>
  ```
- 텍스트 스타일을 바꾼다
```python
  <style> 
  … 
  h1 { 
  color:#fff; 
  font-size:120px;
  text-shadow: 2px 3px 0 #000; 
  }
  </style>
```
- 텍스트 위치를 지정
```python
  <style> 
  … 
  #contents {
  background:url("images/bg.jpg") norepeat;
  background-size:cover;
  width:800px;
  height:500px;
  margin:0 auto;
  position:relative;
  }
  h1 { 
  color:#fff; 
  font-size:120px;
  text-shadow: 2px 3px 0 #000;
  position:absolute;
  right:100px;
  bottom:100px; 
  }
  </style>

  ```
#### 웹 요소 중앙에 표시하기
```python
  #container {
  position: relative;
  }
  .box {
  width: 100px;
  height: 100px;
  background-color: red;
  position: absolute;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
  }
```
- 세로로만 중앙 배치할 경우
  ```python
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  ```
- 가로로만 중앙 배치할 경우
```python
  position: absolute;
  left: 50%;
  transform: translateX(-50%);
```
#### 이미지 꾸미기
```python
  <style> 
  #container {
  width:350px;
  margin:30px auto;
  }
  img {
  border:1px solid #ccc;
  border-radius:50%; 
  box-shadow: 5px 5px 30px 2px #000;
  }
  </style>
```
### 배경 관련 스타일 배경색, 배경이미지 지정하기
- background-color 속성 : 
```python
  <style>
  body {
  background-color: #ccc;
  }
  ……
  </style>
```
- background-image 속성
```python
  <style>
  body {
  text-align: center;
  background-image:url('images/bg-1.jpg'); 
  background-color:#222; /* 배경 이미지가 표시되지 않을 경우를 위해 사용 */
  }
  h1 {
  font-size:120px;
  font-family:Verdana, Geneva, Tahoma, sans-serif;
  color: #fff;
  text-shadow: 2px 2px #000;
  }
  </style>
```
- background-repeat 속성 : repeat, repeat-x, repeat-y, no-repeat
```python
  <style>
  body {
  background-image:url('images/bg-2.jpg’);
  background-repeat: repeat-x;
  }
  ……
  </style>
```
```python
  <style>
  body {
  background-image: url('images/bg-3.jpg’);
  background-repeat: no-repeat;
  }
  ……
  </style>
```
- background-position 속성 : 백분율, 길이, 키워드

 1)백분율(가로세로) `background-position : 30% 60%;`

 2)길이 'background-position:30px 20px;'

 3)키워드 'background-position:center bottom;'

- background-attachment 속성 : scroll, fixed(화면을 스크롤해도 배경 이미지는 같은 자리에 표시 `background-attachment: fixed;`)
- 불릿 대신 배경 이미지 사용하기
```python
  <style>
  ul {
  list-style:none; /* 불릿 없앰 */
  }
  li {
  background-image:url('images/book-icon.png’); /* 배경 이미지 파일 */
  padding-left:50px; /* 왼쪽 패딩 배경이미지크기에 맞게 설정해야 함*/
  line-height:40px; /* 줄간격 배경이미지크기에 맞게 설정해야 함*/
  background-repeat:no-repeat; /* 배경 이미지 반복 안함 */
  background-position:left center; /* 배경 이미지 위치 */
  }
  </style>
```
#### 배경 이미지 위치 및 범위 지정하기
- background-origin 속성(일반적으로 단일이미지경우 사용) : border-box, padding-box, content-box (clip사용시 이미지가 잘릴 수 있다)
- background-clip 속성(일반적으로 반복 이미지일경우 사용) :  border-box, padding-box, content-box
- background-size 속성 : auto, contain(이미지가 다 보이도록), cover(전체 페이지 이미지 채우기), <크기>, <백분율>