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

# while
- 형태 : 
