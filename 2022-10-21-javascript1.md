### 자바스크립트 변수

- 변수 이름 정하는 규칙
  1. 숫자로 시작할 수 없고, 이름 안에 공백은 안됨
  2. 영문자의 대소문자를 구별
  3. 한 단어로 이루어진 변수를 사용할 때에는 주로 소문자를 사용
  4. 두 단어 이상으로 이루어진 변수를 사용할 때에는 언더바(_)로 연결하거나 중간에 대문자를 섞어 사용
  5. 자바스크립트에서 미리 정해 놓은 예약어(예: let 등)는 변수 이름으로 사용할 수 없음
  6. 무의미한 변수 이름은 피한다선언한다

```
  let 일반변수명;     선언하고사용, 재선언불가, 재할당가능
  const 상수변수명;   선언하고사용, 재선언불가, 재할당불가 
  var 변수명;        선언안하고사용, 재선언가능, 재할당가능    

```

### 자바스크립트 자료형
크게 원시형(primitive type)과 객체(object)형으로 나눔

- 원시형(primitive type) : 하나의 값만 가지고 있는 자료형
  1. number(숫자) : 따옴표없이 숫자만 입력
  2. string("문자열") : 따옴표 안에 입력
  3. boolean(논리형) : true, false로 0, 1 값 반환
  4. undefined : 자료형을 지정하지 않았을때의 유형
  5. null : 값이 유효하지 않을 때의 유형
- 객체(object): 원시형 외의 모든 자료
  1. array(배열) : 하나의 변수에 여러값 지정
  2. object(객체) : 함수와 속성이 함께 포함된 유형(가장 많이 사용)

- typof() 함수 : 어떤 자료형인지 알려줍니다.
```
  typeof(10) // 'number'
  typeof("10") // 'string'
  typeof(3.145) // 'number'
  typeof("안녕하세요?") // 'string'
  typeof("10") // 'string'
  typeof("") // 'string', 빈 문자열
```
- 특수 기호 표시하기
```
\ddd (여기서 d는 숫자) 8진수 문자
\xddd 16진수 문자
\\ 백슬래시 문자
\' 작은따옴표 문자  //console.log('I\'m studying now.')
\" 큰따옴표 문자
\b 백스페이스 문자
\f 폼 피드 문자
\n 줄 바꿈 문자
\r 캐리지 리턴 문자
\t 탭 문자
```
- 템플릿 리터럴
```
  let name = "도레미"
  let classroom = 201
  console.log(name + "님, " + classroom + "호 강의실로 입장하세요.")

  name = "백두산"
  classroom = 205
  console.log(`${name}님, ${classroom}호 강의실로 입장하세요.`)
```
- 논리형 :참true이나 거짓false 값을 표현하기 위한 불린(boolean) 유형, 조건식에서 많이 사용, truthy와 falsy
```
  0     // 숫자 0 ; falsy
  ""    // 빈 문자열 : falsy
  NaN   // Not a Number : falsy
  undefined // 값이 정해지지 않음 -실수로 발생 : falsy
  null  // 유효하지 않은 값 - 의도적 발생 : falsy
```
#### 객체
- 여러 개의 원시 유형을 하나로 묶어 놓은 것
- 원시 유형 외에는 모두 객체. 함수도 객체
- 프로퍼티(property)(‘키:값’ 쌍)와 메서드(서브 루틴 (또는 함수))를 갖는다
```
  객체명 = {
  키 : 값,
  키 : 값,
  ....
  }

  let gitBook = { 
title : "깃&깃허브 입문", // 문자열
pubDate : "2019-12-06", // 문자열
pages : 272, // 숫자
finished : true // 논릿값
}

객체에 있는 여러 프로퍼티 중 원하는 프로퍼티 값을 가져오려면

객체명.키 이름
객체명["키 이름"]
```
#### 배열
- 하나의 변수에 여러 값을 할당할 수 있는 형태
- 대괄호([ ])로 묶고, 그 안에 값을 나열함. 각 값은 쉼표(,)로 구분
- 대괄호 안에 아무 값도 없으면 ‘빈 배열’이라고 하고, 이것 역시 배열
```
  배열명 = [값1, 값2, ...]

  emptyArr = [] // 빈 배열
  colors = ["red", "blue", "green"] // 문자열 배열
  arr = [10, "banana", true] // 여러 자료형으로 구성된 배열

  season   =  ["봄", "여름", "가을", "겨울"]  //봄,여름,가을,겨울은 인덱스 값
  변수이름   인덱스0, 인덱스1, 인덱스2, 인덱스3, 
  length: 4 // 배열의 크기
```
#### 심볼
- 심볼을 만들 때는 Symbol() 함수 사용
- 심볼은 한 번 만들면 변경할 수도 없고, 같은 값을 가진 심볼을 만들 수도 없다.
```
  let var1 = Symbol()
  let var2 = Symbor()
  let id = Symbol() // id를 심볼로 지정합니다.
  const member = {
  name : "Kim",
  [id] : 12345 // 심볼을 키로 지정할 때 대괄호를 사용합니다.
  }
```
#### 자바스크립트의 형 변환
- 자바스크립트에서는 다른 언어에서와 다르게 프로그램 실행 중에 자료형이 변환되는 언어입니다. 
- 자동으로 형이 변환될 때에도 있습니다.
- 자동으로 형이 바뀌는 경우를 미리 알아 두지 않으면 오류를 발생시키기도 하고, 처음에 예상했던 것과 다른 결과가 나올 수도 있습니다.
- 변수를 선언할 때 자료형 지정하지 않음
- 변수에 값을 저장할 때 자료형 결정
- 편리하긴 하지만, 여러 사람이 프로젝트를 지정할 때 변수를 일관성 있게 유지하기 힘들다
- 자동 형 변환
```
  one = "20" // 문자열
  two = 10 // 숫자형
  one + two // "2010”
  one - two // 10
  + 기호 앞이나 뒤에 문자열이 있으면 ＂연결 연산자”
  + 기호 앞뒤에 숫자가 있으면 “더하기 연산자”
  -, *, / 연산자기호 앞이나 뒤에 문자열이 있으면 숫자로 인식함
```
- 숫자형으로 변환하여 사용하는것이 안전함 : Number()

```
  Number(true) // 1
  Number("20") // 20
  Number("Hi?") // NaN

  변환규칙
  true 1
  false 0
  숫자 숫자
  null 0
  undefined NaN
  정수 문자열 정수(맨 앞에 0이 있으면 제거)
  실수 문자열 실수(맨 앞에 0이 있으면 제거)
  16진수 문자열 10진수
  빈 문자열 0
  위 상황 외 NaN
```
  1. partseInt() 함수: 괄호 안의 값을 정수로 변환
  2. parseFloat() 함수 : 괄호 안의 값을 실수로 변환

- 문자열로 변환하기 – toString() 함수 : null이면 ‘null’로, undefined이면 ‘undefined’로 변환. 그 외에는 toString() 함수와 같다
```
  isFull = false // 원랫값 논리형
  initValue = null // 원랫값 null형
  String(isFull) // 'false'
  String(initValue) // 'null'
```
- 논리형으로 변환하기 – Boolean() 함수
```
  Boolean(5 * 4) // true
  Boolean("Hi?") // true
  Boolean(undefined) // false
```
#### 연산자
- 산술 연산자
  1. 4착연산 +, -, *, / 는 동일함.
  2. ++ 1증가,  -- 1감소
  3.  % : 나눈 후에 남은 나머지 값
- 할당 연산자 (대입 연산자)
  1. = 오늘 쪽값을 왼쪽변수에 할당  y = x + 3
  2. += y = y + x  >> y += x  
  3. -= y = y - x  >> y -= x  
  4. *= y = y * x  >> y *= x  
  5. /= y = y / x  >> y /= x  
  6. %= y = y % x  >> y %= x  
- 연결 연산자
```
  user = prompt(“이름을 입력하세요.”)
  alert(user + “님, 안녕하세요?”)

  alert(currentYear + "년 현재,\n" + birthYear + "년에 태어난 사람의 나이는 " + age + 
  "세입니다.");

  result = 10;
  userNumber = prompt(“10보다 작은 수 입력”)
  result = result + userNumber // result += userNumber
```
- 비교 연산자
```
  == , != 두 개의 값이 같은지, 같지 않은지 확인
  <, <= 왼쪽 값이 오른쪽 값보다 작은지 혹은 작거나 같은지 확인
  >, >= 왼쪽 값이 오른쪽 값보다 큰지 혹은 크거나 같은지 확인
  === , !== 두 개의 값이 자료형까지 완벽하게 같은지, 같지 않은지 확인
```
- 논리 연산자
```
  OR 연산자  || 하나만 true면 true
  AND 연산자 && 모두 true면 true
  NOT 연산자  !  반대값
```
- 연산자 우선 순위 : 단항(!, ++, --) -> 산술 -> 비교 -> 논리 -> 할당 연산자

#### 조건문
- 제어문 : 소스 실행 순서를 결정하는 명령문
  1. 조건에 따라 순서 조절하기 : if문, if…else문, switch문, 조건 연산자
  2. 반복 횟수 조절하기 : for문, while문, do…while문
  3. 소스 흐름에 영향을 주는 문 : continue문, break문

- if문
```
  if(조건) {
  조건값이 true일 때 실행할 명령
  }
```
- if … else 문
```
  if(조건) {
  조건 결괏값이 true일 때 실행할 명령
  } else {
  조건 결괏값이 false일 때 실행할 명령
  }
```
- 조건 연산자
```
  (조건)? 명령1 : 명령2

  if (num1 < num2 ) {
  small = num1;
  } else {
  small = num2;
  }

  small = (num1 < num2) ? num1 : num2;
```
- switch문
```
  switch (변수)
  {
  case 값1 : 문장
  break;
  case 값2 : 문장
  break;
  ……
  default: 문장
  ｝
```
#### 반복문
- for 문
```
  for (초깃값; 조건; 증가식) { ... }

  for(let i = 1; i <= 10; i++) {
  console.log(i + ‘\n’);
  }
```
- for문 중첩하기
```
  for(var i = 2; i <= 9; i++) {
  document.write("<div>");
  document.write("<h3>" + i + "단</h3>");
  for (var j = 1; j <= 9; j++) {
  document.write(`${i} X ${j} = ${i * j}<br>`);
  }
  document.write("</div>");
  }
```
- while 문, do … while 문, break문, continue문
```
  while (조건) {
  실행할 명령
  }

  do {
  실행할 명령    // 한번은 무조건실행
  } while (조건)

  반복문을 빠져나와야 한다면? → break문 사용

  특정 조건이 됐을 때 실행하던 반복 문장을 더 이상 실행하지 않고 반복문의 맨 앞으로 되돌아감 → 반복 과정을 한 차례 건너뛰게 됨.
  for(let i = 1; i <= 10; i++) {
if (i % 2 === 1) {
continue;           //짝수면 표시하고 홀수면 건너 뛰게
}
document.write(`${i}<br>`);
}
```
- 소수인지 체크하기
```
  prime.js

  const number = parseInt(prompt("자연수를 입력하세요"));
  let isPrime; // 소수인지의 여부를 지정합니다.

  if (number === 1) { 
  document.write(`${number}은(는) 소수도, 합성수도 아닙니다.`);
  } else if (number === 2) {
  isPrime = true; // 숫자 2는 당연히 소수입니다.

  } else {
  for (let i = 2; i < number; i++) {
  if (number % i === 0) { // 나누어 떨어지는 수가 있다면
  isPrime = false; // 소수가 아닙니다.
  break; // for문을 빠져나옵니다
  }
  else { // 나누어 떨어지는 수가 없다면
  isPrime = true; // 소수입니다.
  } } } 
```
- for…in문 사용해서 객체 값 가져오기
```
  for...in문은 반복해서 객체의 키를 가져온다.
  각 키의 값을 알고 싶다면 가져온 키를 사용해서 객체에 접근한다.
  배열도 객체이기 때문에 배열에서도 for…in문을 사용할 수 있다.

  for (변수 in 객체) { ... }

  const gitBook = {
  title : "깃&깃허브 입문",
  pubDate : "2019-12-06",
  pages : 272,
  finished : true
  }
  for(key in gitBook) {
  document.write(`${key} : ${gitBook[key]}<br>`);
  }

결과값
  title : 깃&깃허브 입문
  pubDate : 2019-12-06
  pages : 272
  finished : true
```
- for…of문 사용해서 반복 가능 객체 값 가져오기

```
  이터러블(iterable) 객체란 여러 값이 나열되어 있는 객체를 가리킴
  문자열, 배열 등

  for (변수 of 객체) { ... }

  const students = ["Park", "Kim", "Lee", "Kang"];
  // students에 있는 student가 있는 동안 계속 반복
  for (let student of students) { 
  document.write(`${student}. `);
  }

결과값
  Park, Kim, Lee, Kang
```
