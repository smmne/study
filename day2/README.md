# 문장

### Statement
- JS 코드 실행 단위
- 세미몰론(;)까지 하나의 문장
- var book = "책";

### 문장 시작 위치
- 위치 제약 없음
- 들여쓰기 : 일반적으로 2칸, 4칸

<br>

# 변수

### Variable
- 값을 저장하는 영역

### 변수 사용 목적
- 변수에 저장된 값의 재사용

### 변수 선언 방법
```
var book;
```
1. var을 작성하고 변수 이름 작성
2. 값을 저장할 영역만 선언한 것

### 값을 변수에 할당하는 방법
```
var book = '책';
```
1. = 오른쪽의 값을 왼쪽의 변수에 할당
2. book 변수로 값을 사용할 수 있게 됨

<br>

# 변수 선언 방법

### 콤마로 구분하여 다수 작성
```
var book = '책', point = 123;
```
1. 콤마(,) 다음에 var을 작성하지 않음
2. 콤마와 변수 이름 사이에 일반적으로 한 칸 띄움
3. 세미콜론(;) 앞까지 콤마 사용 가능

### 줄을 바꾸어 작성
```
var book = '책';
    point = 123;
```

### 변수 이름 앞에 콤마 작성
```
var book = '책';
    , point = 123;
```

### 의미를 부여하여 변수 이름 작명
- 시맨틱(Semantic)이라고 함

<br>

# 변수에 값 할당 방법

### 나중에 할당한 값으로 바뀜
```
var point = 123, point = 456;

point 789;
```
1. JS 코드는 왼쪽에서 오른쪽으로 처리
2. point 변수값은 123 -> 456 -> 789로 바뀜

### 같은 값 할당
```
var point = amount = 123;
```
1. point와 amount의 값은 123
2. 권장 형태는 아님
3. 값이 연동되는 경우도 있음

<br>

# 주석

### 주석은 JS 코드로 인식하지 않음

### 한줄 주석
```
// 책을 book 변수에 할당합니다.
var book = '책'; // 여기부터 주석;
```
1. //부터 줄 끝까지를 주석으로 처리
2. 주석의 확장성을 위해 코드 윗줄에 작성
3. single-line comment

### 블록(Block) 주석
```
/*
var book = '책';
var music = '음악';
*/
```
1. /*와 */ 사이의 모든 코드를 주석으로 처리함
2. 일반적으로 4줄, 5줄 이상을 주석으로 처리할 때 사용함
3. multi-line comment

# /** 코드 */ 형태
- JS 스펙에 정의된 주석은 아니며 블록 주석과 같음
```
/**
    * @function getName
    * 1. 이 형태로 작성
    * @param {String} code, 코드
*/
function getName(code){};
```
1. 개발자들 사이의 코딩 관례
2. 이렇게 작성하면 프로그램 설명 문서를 자동으로 만들어 주는 툴이 있음

### JS 스펙(Specification)이란?
- 자바스크립트 문법을 작성한 문서
- ES3, ES5는 JS 스펙의 에디션

<br>

# console.log()

### console.log(...data)
- 소괄호() 안에 작성된 값을 브라우저 콘솔 창에 출력
- 문자, 숫자 등을 출력
- 콤마로 구분하여 다수 작성 가능
- 소괄호 안에 작성한 값을 강좌에서는 파라미터 값이라고 부름

### JS에서 제공하는 것은 아님

<br>

# 정수, 실수

### 정수
- 소수가 없는 숫자
- 123, -123

### 실수
- 소수를 가진 숫자
- 1.23, 1.0

### JS는 정수, 실수를 구분하지 않음
- 1, 1.,1.0 모두 1.0으로 간주
  단, 표시는 1로 표시
```
log(1);
log(1.);
log(1.0);
log(1.00001);
```

[실행 결과]
1
1
1
1.00001

<br>

# 숫자 처리

### 정수와 실수를 구분하지 않음
- 64비트(Bit) 부동 소수점 처리
- IEEE 754 표준

### 부동 소수점 처리란?
- 123을 123.0으로 처리
```
log(.123);
log(0.12 + 5);
```
1. .123처럼 소수점 앞에 값을 작성하지 않으면 0을 붙여 0.123으로 사용함
2. 정수와 실수를 구분하는 언어에서는 실수(0.12)와 정수(5)를 더할 수 없음
3. 정수는 실수(5.0)으로 변화하여 더해야함
4. JS는 정수와 실수를 구분하지 않고 실수로 계산함

[실행결과]
0.123
5.12

- ES6에 정수, 실수 구분 추가

<br>

# 상수

### 변경할 수 없는 값

### 상수 변수
- 상수가 설정된 변수
- JS는 변수의 값을 변경할 수 있으므로 상수변수는 선언적 의미

### 상수 변수 표기 방법
- 코딩 관례로 영문 대문자 사용
- var ONE = 1;
- 상수로 사용한다는 시맨틱 선언
```
var ONE = 123;
ONE = 456;
log(ONE);
log(Number.MAX_VALUE);
```
1. ONE 변수를 대문자로 선언한 것은 상수라는 것을 나타내기 위한 것
2. JS는 실행결과처럼 값을 바꿀 수 있음
3. Number.MAX_VALUE는 최대값으로 JS 상수이며 값을 바꾸면 에러가 남

[실행결과]
456
1.7976931348623157e+308

### JS가 제공하는 상수값은 변경 불가
- MAX_VALUE, MIN_VALUE 등

<br>

# 진수

### 10 진수 : 123

### 16 진수
- 0xFF : 255
- 1번째에 숫자 0 작성
- 2번째에 영문자 x 작성
- 3번째 이후 : 0~f 작성
- 대소문자 구분하지 않음
```
log(0XF);
log(0xff);
log(0xfff);
```
1. 0XF는 15
2. 0X는 16진수를 나타내므로 값이 아니며
   A:10, B:11, C:12, D:13, E:14, F:15
3. 0xff는 (16*15 + 15) 방법으로 계산
4. 0xfff는 (16*16*14) + (16*15) + 15로 계산
[실행 결과]
15
255
4095

### 8 진수
- ES3에서 폐지, ES6 재정의

### 2 진수 : ES6에서 특별한 방법 제공

<br>

# 데이터 타입

### 데이터의 사전적 의미는 자료
- 강좌에서는 데이터로 표기

### 데이터 타입 형태
- 숫자 타입: var value = 123;
- 문자 타입: var value = 'sports';

### typeof 연산자
- 데이터(값) 타입 반환
- typeof value에 데이터를 작성
```
var point = 123;
log(typeof point);

var book = '책';
log(typeof book);
```
1. 123은 숫자이므로 데이터 타입은 number
2. '책'은 문자이므로 데이터 타입은 string
   문자는 "책"처럼 큰따옴표 안에 작성하거나 '책'처럼 작은따옴표 안에 작성
3. typeof 연산자는 고려사항이 있으며 관련된 곳에서 다시 다룰 예정
[실행결과]
number
string

### 키워드(Keyword)
- 특별한 기능을 가진 단어

<br>

# 데이터 타입

### 데이터 타입을 자료형이라고도 부름
- 강좌에서는 데이터 타입으로 표기

### 데이터는 타입을 가짐
- JS는 데이터를 기준으로 타입을 결정
- 타입을 먼저 선언하고 타입에 맞는 데이터를 할당하지 않음
```
var point = 123;
log(typeof point);

point = '책';
log(typeof point);
```
1. point 변수에 123을 할당하면 point 변수의 데이터 타입은 number
2. 다시 point 변수에 '책'을 할당하면 point 변수의 데이터 타입은 string
3. JS는 이처럼 데이터(값)에 따라 데이터 타입이 결정됨
[실행 결과]
number
string

<br>

# 데이터 타입 분류

### 언어 타입과 스펙 타입

### 언어 타입
- JS 프로그램에서 사용할 수 있는 타입
- Undefined, Null, Boolean, String, Number, Object

### 스펙(문서) 타입
- 언어 알고리즘을 위한 타입으로 JS 프로그램에서 사용 불가
- Reference, List, Completion, Property Descriptor, Data Block, Lexical Environment, Lexical Record 등

<br>

# Number 타입

### Number 타입
- 부호(+, -)를 가진 값
```
var point = 123;
log(typeof point);

point = -1.23;
log(typeof point);
```
[실행 결과]
number
number

### 숫자 값 범위
- 18, 437, 736, 874, 454, 810, 627 (2의 64승 - 2의 53승 + 3)

### Number 타입의 특수한 3개 값
- NaN : Not-a-Number
```
var point = 1 * 'A';
log(point);
```
1. NaN는 값이 숫자가 아닌 것을 나타내는 값
[실행 결과]
NaN

- Infinity : 양수 무한대
- -Infinity : 음수 무한대

<br>

# String 타입

### 문자 타입
- 값을 "" 또는 '' 사이에 작성
- 최대 문자수 : 2의 53승 - 1

### 큰따옴표와 작은따옴표를 같이 사용할 때
- 따옴표 작성 방법
```
var point = "책, '123'";
log(point);

point = '책, "123"';
log(point);
```
1. 작은따옴표를 표시하려면 큰따옴표 안에 작은따옴표를 작성
2. 큰따옴표를 표시하려면 작은따옴표 안에 큰따옴표를 작성
[실행 결과]
책, '123'
책, "123"

### 따옴표에 숫자를 작성하면 문자 타입이 됨
```
var value = '123';
log(typeof value);
```
1. 123이 Number 타입에서 String 타입으로 변환
[실행 결과]
string

<br>

# Undefined 타입

### Undefined(대문자) 타입
- 값 : undefined(소문자)

### 변수의 디폴트 값
- var point;
- 변수를 선언만 한 것으로 undefined가 초기값으로 설정
```
var point;
log(point);
```
1. point 변수를 선언만 하였는데 undefined 출력
2. 변수가 이름과 값을 갖는 구조를 맞추기 위한 것
3. 초기값으로 undefined를 설정하기 때문
[실행 결과]
undefined

- 변수에 값을 할당하지 않은 것을 나타내는 시맨틱

### 변수에 undefined 할당 가능
```
var point = undefined;
log(point);
```
1. undefined가 값이므로 변수에 할당 가능
2. 하지만, 초기값인지 값을 할당한 것인지 구분이 되지 않으므로 권장하지 않음
3. 대신, null을 할당
[실행 결과]
undefined

<br>

# Null 타입

### Null(대문자) 타입
- 값 : null(소문자)

### null과 undefined 차이
- undefined는 단지 변수만 선언
- null을 할당해야 값이 null이 됨
- 의도적으로 값을 할당한 것으로 코드를 수행한 것이 됨
```
var book;
log(book);

var point = null;
log(point);
```
[실행 결과]
undefined
null

<br>

# Boolean 타입

### 불리언 타입
- 값 : true, false
```
log(true);
log(false);
```
[실행 결과]
true
false

<br>

# Object 타입

### Object 형태
- {name: value} 형태
```
var book = {
    title: "책", point: 123
};
log(book);
```
1. 중괄호{} 안에 key: value 형태로 작성
2. 콜론(:)을 기준으로 왼쪽을 프로퍼티 key 또는 name이라고 부르며 오른쪽을 프로퍼티 값이라고 부름
[실행 결과]
{title: 책, point: 123}

### 프로퍼티(Property)
- name과 value 하나를 지칭

### Object는 프로퍼티 집합

<br>

# 타입 정리

### JS의 기본 데이터 타입 정리

### 기본 데이터 타입을 Primitive 타입이라고 함
```
log(typeof 123);
log(typeof "문자열");
log(typeof true);
log(typeof undefined);
```
1. 시맨틱적으로 데이터 타입을 짐작할 수 있음
[실행 결과]
number
string
boolean
undefined

### 데이터 타입이 같다?
```
log(typeof null);
log(typeof {book: "책"});
```
1. null과 {book: "책"}의 데이터 타입이 object임
2. null의 데이터 타입이 null이 아님
[실행 결과]
object
object

