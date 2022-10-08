#### 그리드 레이아웃
- 그리드 시스템 : 신문이나 책, 잡지 같은 인쇄에서 레이아웃을 만들 때 사용하는 시스템
- 그리드 시스템의 종류
 1) 화면 너비를 몇 픽셀로 하는가에 따라 구분 : 960 그리드 시스템, 1200 그리드 시스템
 2) 화면 가로를 몇 개 칼럼으로 나누는가에 따라 구분 : 12칼럼 그리드, 16 칼럼 그리드, 24 칼럼 그리드
- 그리드 레이아웃의 특징 
 1) 시각적으로 안정적인 디자인
 2) 간결한 디자인
 3) 내용을 원하는 위치에 배치
 - 그리드 레이아웃을 만드는 최신 방법 : 이전에는 블록, 인라인, 표, position을 사용한 레이아웃
  1) 플렉서블 박스 레이아웃 (혹은 플렉스 박스 레이아웃)
  2) CSS 그리드 레이아웃 사용

- 플렉스 박스를 사용한 레이아웃
 1) 그리드 레이아웃을 기본으로 하고 각 박스를 원하는 위치에 따라 배치
 2) 수평 방향이나 수직 방향 중에서 한쪽을 주축으로 정하고 박스를 배치
 3) 화면 너비를 넘어가면 교차축으로 넘어가서 배치
 4) 적용할 대상을 플렉스 컨테이너로 지정 >>> 플렉스 컨테이너 안에 배치할 요소를 넣는다 >>> 주축을 결정 >>> 주축의 정렬 방법과 교차축의 정렬 방법 지정
- display 속성 : flex - 항목을 블록 레벨 요소로 배치, inline-flex - 항목을 인라인 레벨 요소로 배치
- flex-direction 속성 : 주축과 방향을 지정
 1) row : 주축 가로, 왼쪽에서 오른쪽으로 배치, 기본값
 2) row-reverse : 주축 가로, 오른쪽에서 왼쪽으로 배치
 3) column : 주축 세로, 위쪽에서 아래쪽으로 배치
 4) column : 주축 세로, 아래쪽에서 위쪽으로 배치
- flex-wrap 속성 : 플렉스 항목을 한 줄에 다 표시할지, 여러 줄에 걸쳐 표시할지 지정
 1) nowrap : 플렉스 항목을 한 줄에 표시, 기본값
 2) wrap : 플렉스 항목을 여러 줄에 표시
 3) wrap-reverse : 플렉스 항목을 여러 줄에 표시, 시작 끝점 바뀜
- flex-flow 속성 : flex-direction 속성과 flex-wrap 속성을 하나의 속성으로 줄여서 표현, 기본 값은 flex-flow: row nowrap
```
  flex-direction: row;
  flex-wrap: wrap;      
  
  flex-flow : row wrap; //위 두줄을 한줄로 표현
```

- justify-content 속성 : 플렉스 항목을 주축 방향을 배치할 때의 배치 기준
 1) flex-start : 주축의 시작점에 맞춰 배치
 2) flex-end : 주축의 끝점에 맞춰 배치
 3) center  : 주축의 중앙에 맞춰 배치
 4) space-between : 주축의 시작점과 끝점에 맞춘 후 같은 사이간격 배치
 5) space-around : 모든 항목을 주축에 같은 간격으로 배치

- 플렉스 항목에서 margin 활용하기
- flex-direction: row일 때
 1) margin-right: auto; 마진이 오른쪽 모든 공간 차지. 플렉스 항목을 왼쪽 끝으로 보낼 수 있음
 2) margin-left: auto; 마진이 왼쪽 모든 공간 차지. 플렉스 항목을 오른쪽 끝으로 보낼 수 있음
 3) margin-left: auto; margin-right: auto; 마진이 왼쪽과 오른쪽 공간을 반반 차지. 플렉스 항목을 중앙에 배치할 수 있음
- flex-direction: column일 때
 1) margin-bottom: auto; 마진이 아래쪽 모든 공간 차지. 플렉스 항목을 위쪽 끝으로 배치
 2) margin-top: auto; 마진이 위쪽 모든 공간 차지 → 플렉스 항목을 아래쪽 끝으로 배치
 3) margin-top: auto; margin-bottom: auto; 마진이 위쪽과 아래쪽 공간을 반반 차지 → 플렉스 항목을 중앙에 배치

 - align-items 속성 : 교차축이 한 줄일 경우 교차축의 배치 방법 조절
  1) flex-start : 교차축의 시작점에 맞춰 배치
  2) flex-end :  교차축의 끝점에 맞춰 배치
  3) center :  교차축의 중앙에 맞춰 배치
  4) baseline :  교차축의 문자기준선에 맞춰 배치
  5) stretch :  플렉스 항목을 늘려 교차축에 가득 차게 배치

- align-self 속성 : 교차축에서 특정 항목만 선택해서 배치하려고 할 때
 1) flex-start : 교차축의 시작점에 맞춰 배치
 2) flex-end :  교차축의 끝점에 맞춰 배치
 3) center :  교차축의 중앙에 맞춰 배치
 4) baseline :  교차축의 문자기준선에 맞춰 배치
 5) stretch :  플렉스 항목을 늘려 교차축에 가득 차게 배치

- align-content 속성 : flex-wrap: wrap을 사용해서 플렉스 항목이 여러 줄로 표시될 때 교차 축의 배치 방법 지정
 1) flex-start : 교차축의 시작점에 맞춰 배치
 2) flex-end : 교차축의 끝점에 맞춰 배치
 3) center  : 교차축의 중앙에 맞춰 배치
 4) space-between : 교차축의 시작점과 끝점에 맞춘 후 같은 사이간격 배치
 5) space-around : 모든 항목을 교차축에 같은 간격으로 배치

 - gap 속성 : 플렉스 컨테이너 안에 있는 플렉스 항목들 간의 여백 조절 
 1) 값이 하나라면 : 좌우, 상하 같은 여백
 2) 값이 2개라면 : 첫번째 값은 상하 여백, 두번째 값을 좌우 여백
- align-content 속성 : 주축으로 배치하다가 너비가 넘어가서 여러 줄로 배치될 경우 교차 축의 배치 방법
 1) flex-start : 교차축의 시작점에 맞춰 배치
 2) flex-end :  교차축의 끝점에 맞춰 배치
 3) center :  교차축의 중앙에 맞춰 배치
 4) baseline :  교차축의 문자기준선에 맞춰 배치
 5) stretch :  플렉스 항목을 늘려 교차축에 가득 차게 배치

 [플렉스 박스 연습하기](https://flexboxfroggy.com/#ko)
 
 - flex-basis 속성
 1) 플렉스 항목의 기본 크기 설정
 2) flex-direction이 row라면 너비, column이라면 높이 를 정하게 됨
 3) 기본 값 auto (콘텐츠 영역만큼 크기를 차지함)
 4) px, %, em, rem 등 width에서 사용할 수 있는 모든 단위를 사용할 수 있다.
 - flex-grow 속성
1) 플렉스 항목을 배치하고도 플렉스 컨테이너에 여백이 남을 때 플렉스 항목 확대하기
2) 기본값: 0 (확대하지 않음)
3) 음수 값은 설정할 수 없음
- flex-shrink 속성
1) 플렉스 항목을 배치할 때 플렉스 컨테이너 공간이 부족할 경우 플렉스 항목 축소.
2) flex-wrap: wrap일 경우에는 적용되지 않음. ((wrap – 공간이 부족하면 다음 줄로 넘겨 버리기 때문)
3) 기본값: 1 
4) flex-shrink: 0 – 컨테이너 크기가 플렉스 항목보다 작아져도 플렉스 항목을 축소하지 않음
5) flex-shrink: 1 – 컨테이너 크기가 플렉스 항목보다 작아지면 컨테이너에 맞춰 축소함
- flex 속성
1) flex-grow와 flex-shrink, flex-basis를 한꺼번에 지정
2) 기본 flex: 0 1 auto
3) 숫자는 flex-grow와 flex-shrink. 단위가 있는 값은 flex-basis
4) 3개의 값을 모두 지정할 때는 순서를 지켜야 함. flex-grow flex-shrink flex-basis

#### CSS 그리드 레이아웃
- display 속성 : CSS 그리드 레이아웃을 사용하기 위해 부모 요소를 그리드 컨테이너로 지정
- grid-template-columns, grid-template-rows 속성 : 칼럼/줄의 크기와 개수 지정
- fr 단위 : 칼럼/줄의 크기를 지정할 때 px 단위는 적합하지 않음 → 상대적인 크기를 지정하는 fr(fraction) 단위 사용
- repeat( ) 함수 : 똑같은 값을 여러 번 반복한다면 내장 함수 repeat( ) 함수 사용
- minmax( ) 함수 : 높이를 고정하면 그 길이를 넘는 내용은 보이지 않음 → minmax() 함수를 사용해서 최솟값과 최댓값 지정
- grid-template 속성 : grid-template-rows와 grid-template-columns를 한꺼번에 지정 /를 기준으로 왼쪽에는 rows 값을, 오른쪽에는 columns 값을 사용
- auto-fill, auto-fit 속성 : 브라우저 창의 너비가 달라질 때 칼럼 너비를 어떻게 조절할지 지정
- 그리드 항목 간격 조절
1) column-gap : 칼럼과 칼럼 사이의 간격 지정
2) row-gap: 줄과 줄 사이의 간격 지정
3) gap: 칼럼과 줄 사이의 간격을 한꺼번에 지정
- 그리드 라인을 사용해 레이아웃 만들기
 1) grid-column-start : 컬럼 시작의 라인번호 지정
 2) grid-column-end : 컬럼 끝의 라인번호 지정
 3) grid-column :  컬럼 시작과 끝번호 사이에 / 사용
 4) grid-row-start : 줄 시작의 라인번호 지정 
 5) grid-row-end : 줄 끝의 라인번호 지정 
 6) grid-row : 줄 시작과 끝번호 사이에 / 사용 
 - 템플릿 영역을 사용해 레이아웃 만들기
  1) grid-area 속성을 사용해 템플릿 영역을 만들고 배치

- 폰트 어썸 사용하기 : 둘 이상의 아이콘 켭쳐서 사용하기
 1)fa-stack : 쌓을 아이콘의 부모 요소에 적용
 2)fa-stack-1x : 쌓을 아이콘 중 기본 크기대로 사용할 아이콘에 적용
 3)fa-stack-2x : 쌓을 아이콘 중 두배 크기로 사용할 아이콘에 적용(배경이 되는 아이콘)
 4)fa-inverse : 아이콘의 색상을 반전시킬 아이콘에 적용
```
  <span class="fa-stack">
  <i class="fa-solid fa-circle fa-stack-2x"></i>
  <i class="fa-solid fa-home fa-stack-1x fa-inverse"></i>
  </span>
```
[폰트어썸](https://cdnjs.com/libraries/font-awesome)
[그리드 박스 연습하기](https://cssgridgarden.com/#ko)

