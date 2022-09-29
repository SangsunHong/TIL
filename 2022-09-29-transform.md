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


