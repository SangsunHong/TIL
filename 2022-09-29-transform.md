### transform & css 애니메이션
#### transform
- 2차원 변형
 1) 수평이나 수직으로 웹 요소 변형
 2) x 축은 오른쪽으로 갈 수록, y축은 아래로 갈 수록 값이 커짐
 3) 크기나 각도만 지정하면 됨
 4) 2차원 좌표 사용
- 3차원 변형
 1) x축과 y축에 원근감 추가
 2) z축은 앞뒤로 이동(입체감을 느낄 수 있음)
- translate() 함수
 1) transform:translate(tx, ty) - x축 방향으로 tx만큼, y축 방향으로 ty만큼 이동
 2) transform:translate3d(tx, ty, tz) - x축 방향으로 tx만큼, y축 방향으로 ty만큼, z축 방향(앞뒤)으로 tz만큼 이동
 3) transform:translateX(tx) - x축 방향으로 tx만큼 이동
 4) transform:translateY(ty) - y축 방향으로 ty만큼 이동
 5) transform:translateZ(tz) - z축 방향으로 tz만큼 이동
- scale 함수
 1) transform:scale(sx, sy) - x축 방향으로 sx만큼, y축 방향으로 sy만큼 확대
 예) scale(2.0) = scale(2) = scale(2, 2) : 요소를 두 배로 확대.
 2) transform:scale3d(sx, sy, sz) - x축 방향으로 sx만큼, y축 방향으로 sy만큼, z축 방향으로 sz만큼 확대
 3) transform:scaleX(sx) – x축 방향으로 sx만큼 확대
 4) transform:scaleY(sy) - y축 방향으로 sy만큼 확대
 5) transform:scaleZ(sz) -z축 방향으로 sz만큼 확대
- rotate 함수 : 각도만큼 웹 요소를 회전 / 시계 방향 +값, 반 시계 방향 -값 // 일반 각도(degree)나 래디안(radian) 값 사용
```
  <style>
  ……
  #rotate1:hover {
  transform: rotate(40deg); 
  }
  #rotate2:hover {
  transform: rotate(-40deg); 
  }
  </style>
```
- transform-origin 속성 : rotate 트랜스폼은 요소의 중앙을 중심으로 회전 /  transform-origin으로 중심점을 지정
```
  <style>
  ……
  #rotate1:hover {
  transform: rotate(40deg);
  }
  #rotate2:hover {
  transform-origin: left top;
  transform: rotate(40deg); 
  }
  #rotate3:hover {
  transform-origin: 30px 30px;
  transform: rotate(40deg); 
  }
  #rotate4:hover {
  transform-origin: 0% 100%; 
  /* transform-origin: left bottom */
  transform: rotate(40deg); 
  }
  </style>
```
- 3차원 rotate() 함수
 1) transform: rotate(rx, ry, 각도)
 2) transform: rotate3d(rx, ry, rz, 각도)
 3) transform: rotatex(각도)
 4) transform: rotatey(각도)
 5) transform: rotatez(각도)
 6) perspective 속성 : 입체감을 표현, 변형하는 요소의 부모 요소에 정의해야 함
 `.rotatex:hover {transform: rotateX(50deg); }` /*3차원회전인데 입체감 없음*/
```
  .rotatex:hover {
  transform: rotateX(50deg); 
  }
  #pers {
  perspective:300px; 
  } /*3차원회전에 입체감을 줌*/
```
- skew 함수 : 요소를 지정한 각도만큼 비틀어 왜곡
 1) transform:skewX(ax) – x축을 따라 당김
 2) transform:skewY(ay) – y축을 따라 당김
 3) transform:skew(ax, ay) – 첫 번째 각도는 x축, 두번째 각도는 y축(없으면 0으로 간주함)
```
  <style>
  ……
  #skewx:hover {
  transform: skewX(30deg);
  }
  #skewy:hover {
  transform: skewY(15deg);
  }
  #skewxy:hover {
  transform: skew(-25deg, -15deg);
  }
  </style>
```
```
  .box {
  width:500px;
  height:80px;
  background-color:#222;
  transform: skewX(15deg); /* box전체 비틀기-굴자포함 */
  }
  h1 {
  color:#fff;
  font-weight:bold; 
  line-height: 80px;
  text-align: center; 
  transform: skewX(-15deg); /* 굴자를 원래대로 */
  }
```
- CSS로 도형 그리기
 1) 사각형
```
  <div class="square"></div>

  .square {
  width: 100px;
  height: 100px;
  background: #b8005c; }
```
 2) 원
```
  <div class=＂circle"></div>
  
  .circle {
  width: 100px;
  height: 100px;
  background: #b8005c;
  border-radius: 50%;}
```
 3) 삼각형
```
  <div class=”triangle"></div>

  .triangle {
  width: 0;
  height: 0;
  border-left: 50px solid transparent;
  border-right: 50px solid transparent;
  border-bottom: 100px solid #b8005c; }
```
 4) 평행사변형
```
  <div class=”parallel"></div>
  
  .paralle {
  width: 100px;
  height: 100px;
  transform: skew(15deg);
  background: #b8005c; }
```
 5) 마름모
```
  <div class=”diamond"></div>
  
  .diamond {
  width: 100px;
  height: 100px;
  transform: rotate(45deg);
  background: #b8005c; }
```
#### 트랜지션
웹 요소의 스타일 속성이 조금씩 자연스럽게 바뀌는 것

- 트랜지션에서 사용하는 속성들
 1) transition-property 속성 : 트랜지션을 적용할 속성(ex, 크기, 색상) 선택
 `transition-property: all | none | <속성이름>`
 `transition-property: width;`
 2) transition-duration 속성 : 트랜지션 진행 시간 지정 / 초(seconds) 또는 밀리초(milliseconds) //여러 개라면 쉼표(,)로 구분해 진행 시간 지정
```
  <style>
  .box {
  ……
  transition-property: all;
  transition-duration: 2s;
  }
  …
  </style>
```
- transition-timing-function 속성 : 트랜지션의 시작과 중간, 끝에서의 속도 지정
 1) ease : 처음엔 천천히 > 빨라지다 > 마지막 천천히 / 기본값
 2) linear : 똑같은 속도로
 3) ease-in : 느리게 시작
 4) ease-oot : 느리게 끝냄
 5) ease-in-out : 느리게 시작하고 느리게 끝냄
 6) cubic-bezier(n, n, n, n) : 베지에 함수를 정의해서 사용(n = 0~1)
 - transition-delay 속성 : 지연 시간 지정
```
  #ex:hover .box{ 
  margin-left: 420px;
  transform:rotate(720deg);
  transition-duration: 3s; }
```
- transition 속성 : 트랜지션 관련 속성을 한꺼번에 지정
 1) `transition: <transition-property값> | <transition-duration값> | <transition-timing-fuction값> | <transition-delay값>`
 2) `transition: 0.5s ease-in; `
- opacity 속성, overflow 속성
 1) opacity 속성 : 요소의 불투명도를 설정(0~1)
 2) overflow 속성 : 내용이 더 클 때 어떻게 표시할 것인지 설정 /사용 값 : visible, hidden, scroll, auto
 3) 이미지 위로 마우스 커서를 올리면 설명 표시하기
```
  .prod-list li:hover .caption {
  opacity: 1;
  transform: translateY(-200px); }
```
4) 상품 설명글에 스타일 지정하기
```
  .prod-list .caption {
  position: absolute;
  top: 200px; 
  width: 300px;
  height: 200px;
  padding-top: 20px;
  opacity: 0; 
  z-index: 10; 
  background:rgba(0,0,0,0.6); }
```
```
  .prod-list li:hover .caption {
  ……
  }
  .prod-list .caption h2,
  .prod-list .caption p {
  color: #fff;
  text-align: center;}
```
 5) 설명글이 부드럽게 등장하도록 해보자
```
  .prod-list .caption {
  position: absolute;
  top: 200px; 
  width: 300px;
  height: 200px;
  padding-top: 20px;
  opacity: 0; 
  z-index: 10; 
  background:rgba(0,0,0,0.6);
  transition: all 0.6s ease-in-out; }
```






