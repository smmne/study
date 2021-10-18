# 문장

- 형태 : ; (세미콜론)
- 문장을 끝나게 하는 역할

<br>

# 화이트 스페이스

### 사람 눈에 보이지 않는 문자
- 가독성을 위한 것
- 문자마다 기능을 갖고 있음

<img width="680" alt="스크린샷 2021-10-15 오후 4 24 21" src="https://user-images.githubusercontent.com/68004742/137448480-b9cc62f8-8bac-4070-9f73-f8f0de25244f.png">

<br>

# 세미콜론 자동 삽입

- 세미콜론(;)은 문장 끝에 작성
- 세미콜론을 삽입하여 자동으로 문장이 끝나게 한다
```
var one = 1
var two = 2;
console.log(one);
```
1. var one = 1 끝에 ;을 작성하지 않았습니다.
2. 두 줄의 코드를 연결하면 var one = 1 var two = 2; 형태가 되며 var을 2번 작성했으므로 에러가 난다.
3. 에러가 나지 않은 것은 엔진이 1의 끝에 세미콜론을 삽입하여 문장을 완성시키기 때문이다.
4. 줄을 분리해야 화이트 스페이스(LF/CR) 앞에 세미콜론을 자동 삽입한다.

[실행 결과]
1

<br>

# 블록

- 형태 { 문장 리스트 opt }
```
var one = 1, two = 1;
if (one === two) {
  var result = one + two;
  console.log(result);
}
```
- 중괄호 {}
  - 실행 그룹으로 블록 안의 모든 문장 실행
- 문장 리스트
  - {} 안의 모든 문장
  - 문장 리스트 작성은 선택(option)

<br>

# if, debugger

### if
- 형태 : if (표현식) 문장1<br>
        if (표현식) 문장1 else 문장2
- 조건에 따른 처리
  - 먼저 표현식을 평가
  - 평가 결과를 true/false로 변환
  - true면 문장1 실행
  [코드 1] 블록 사용하지 않음
  ```
  var a = 1, b = 1;
  if (a === b) console.log("블록을 사용하지 않음");
  
  if (a === b)
  console.log("1번 줄");
  console.log("2번 줄");
  ```
  1. 한 줄에 이어서 작성
  2. 줄을 바꿔 작성
    세미콜론(;)까지 if 조건 실행
    
  [실행 결과]
  블록을 사용하지 않음
  1번 줄
  2번 줄
  
  [코드 2] 블록 사용
  ```
  var a = 1, b = 1;
  if (a === b) {
    console.log("블록 사용");
  }
  ```
  1. 블록에 작성한 모든 문장 실행
  2. 블록 사용 권장
    - 확장성과 일관성을 위해서
    - 
  [실행 결과]
  블록 사용
  - false면 문장2 실행
  
  [코드 3] if else, 블록 사용하지 않음
  ```
  var a = 1, b = 2;
  if (a === b)
    console.log("블록 사용하지 않음, true");
  else 
    console.log("블록 사용하지 않음, else");
  ```
  1. 블록을 사용하지 않은 형태
  
  [실행 결과]
  블록 사용, else
  
  [코드 4] if else, 블록 사용
  ```
  var a = 1, b = 2;
  if (a === b) {
    console.log("블록 사용, true");
  } else {
    console.log("블록 사용, else");
  }
  ```
  1. 블록을 사용한 형태
  
  [실행 결과]
  블록 사용, else
  
### debugger 
- debugger 위치에서 실행 멈춤
  - 브라우저의 개발자 도구 창이 열려 있을 때만 멈춤
  - 열려있지 않으면 멈추지 않음
  - ES5부터 지원
  
  [코드 1] debugger
  ```
  var sports = "스포츠";
  debugger;
  console.log(sports);
  ```
  - debugger 실행

<br>

# while, do ~ while

### while
- 형태 : while (표현식) 문장
- 표현식의 평가 결과가 false가 될 때까지
  - 문장을 반복하여 실행
  - 반복이 종료되는 조건 필요
  
  [코드 1] 문장 반복 실행
  ```
  var k = 1;
  while (k < 3) {
    console.log(k);
    k++;
  }
  ```
  1. while의 표현식 평가 결과가 3보다 작으면 true이므로 while 블록의 문장 리스트를 수행한다.
  2. k가 3이 되면 평가 결과가 false가 되므로 블록의 문장 리스트를 수행하지 않는다.
  3. 표현식 평가 결과가 false가 되도록 조치를 취하지 않으면 무한 반복된다.

  [실행 결과]
  1
  2

### do ~ while
- 형태 : do 문장 while (표현식)
- 처리 방법은 while 문과 같음
   - 단, do 문을 먼저 실행

  [코드 1] 먼저 do 문장 실행
   ```
   var k = 0;
   do {
    console.log("do : ", k);
    k++;
   } while (k < 3) {
    console.log("while : ", k);
   }
   ```
   1. 먼저 do 문을 실행한다.
      [실행 결과] do : 0이 출력된다.
   2. while 문의 표현식을 평가한다.
   3. 평가 결과가 true면 do 문의 블록을 다시 실행
      k가 1이며, 3보다 작으므로 do 문을 실행한다.
   4. 평가 결과가 false면 while 문의 블록 실행
   5. k가 3이면 while 문의 블록을 실행한다.
   
   [실행 결과]
   do:0
   do:1
   do:2
   while:3
   
   <br>
   
 # for ()
 - 형태 : for (초기값 opt; 비교 opt; 증감 opt;) 문장
 - 2번째의 비교 표현식의 평가 결과가 true인 동안 문장을 반복 실행
 
 [코드 1] 블록의 코드를 반복 실행
 ```
 for (var k = 0; k < 2; k++) {
  console.log(k);
 }
 ```
 1. var k = 0;
    초기값 할당, 처음 한 번만 할당한다.
 2. k < 2;
    비교 표현식을 평가한다.
 3. 평가 결과가 true면
    for () 블록의 코드를 실행한다.
 4. 처음 반복은 k가 0이므로 true가 되어 블록의 console.log(k) 실행
 5. k++
    k 변수값을 1 증가시킨다.
 6. 다시 2번부터 5번까지 실행
    k가 2가 되면 2번에서 false가 되며 for () 문을 종료한다.
 
 [실행 결과]
 0
 1
 
 ### for () 옵션
 - 형태 : for (초기값 opt; 비교 opt; 증감 opt;) 문장
 - 형태에서 opt(option)는 생략 가능
  - 증감 생략
  ```
  for (var k = 0; k < 3;) {
    console.log(k);
    k++;
  }
  ```
  1. 증감 표현식에서 k++ 작성하지 않았으며 블록에서 k 변수값을 증가시킨 형태
  - 초기값과 증감 생략
  ```
  ```
  - 비교와 증감 생략
  ```
  ```
  - 모두 생략
  ```
  ```
