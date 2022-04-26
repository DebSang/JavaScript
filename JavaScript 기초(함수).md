## 함수 in JavaScript

- 참조 타입 중 하나로, function 타입
- JavaScript에서 함수를 정의하는 방법은 주로 2가지로 구분
  - 함수 선언식
  - 함수 표현식
- JavaScript에서 함수는 일급 객체* 에 해당함
  - 일급객체란?
    - 변수에 할당 가능하며, 함수의 매개변수로 전달가능하고, 함수의 반환 값으로 사용가능한 객체



> ##### 함수 선언식

- 함수의 이름과 함께 정의하는 방식
- 3가지 부분으로 구성
  - 함수의 이름, 매개변수, 몸통

```javascript
function name(args) {
    //do something
}

function add(num, num2) {
    return num1 + num2
}
add(1, 2)
```



> ##### 함수 표현식

- 함수를 표현식* 내에서 정의하는 방식
  - 표현식 : 어떤 하나의 값으로 결정되는 코드의 단위
- 함수의 이름을 생략하고 익명함수로 정의 가능
  - 익명함수 : 이름이 없는 함수, 함수 표현식에서만 가능
- 3가지 부분으로 구성
  - 함수의 이름(생략가능), 매개변수, 몸통

```javascript
const name = function (args) {
	//do something
}

const add = function (num1, num2) {
	return num1 + num2
}
add(1, 2)
```



> ##### 기본 인자(default arguments)

- 인자 작성 시 '=' 문자 뒤 기본 인자 선언 가능

```javascript
const greeting = function (name = 'Anonymous') {
    return `HI ${name}`
}
greeting() //HI Anonymous
```



> ##### 매개변수와 인자의 개수 불일치 허용

```javascript
const noArgs = function () {
    return 0
}
noArgs(1, 2, 3) // 0

const twoArgs = function (arg1, arg2) {
    return [arg1, arg2]
} 
twoArgs(1, 2, 3) //[1, 2]

const threeArgs = function(arg1, arg2, arg2) {
    return [arg1, arg2, arg3]
}
threeArgs() // [undfined, undfined, undfined]
threeArgs(1, 2) // [1, 2, undfined]
```



> ##### Rest operator

- rest operator(...)를 사용하면 함수가 정해지지 않은 수의 매개변수를 다 배열로 받음

```javascript
const restOpr = function (arg1, arg2, ...restArgs) {
    return [arg1, arg2, restArgs]
}
restArgs(1, 2, 3, 4, 5) //[1, 2, [3, 4, 5]]
restArgs(1, 2) // [1, 2, []]
```



> ##### Spread operator

- spread operator(...)를 사용하면 배열 인자를 전개하여 전달 가능

```javascript
const spreadOpr = function (arg1, arg2, arg3) {
    return arg1 + arg2 + arg3
}
const numvers = [1, 2, 3]
spreadOpr(...numbers) // 6
```

```javascript
/*
[rest operator/spread operator 연습]
 */

const func = function(arg1, arg2, ...restArgs) {
	console.log(arg1, arg2, restArgs)
}

func()
func(1)
func(1, 2)
func(1, 2, 3)
func(1, 2, 3, [4, 5, 6])
func(1, 2, 3, ...[4, 5, 6])
```



> ##### 선언식 vs 표현식

|        | 함수 선언식                      | 함수 표현식                   |
| ------ | -------------------------------- | ----------------------------- |
| 공통점 | 데이터 타입, 함수구성요소        | 데이터 타입, 함수구성요소     |
| 차이점 | 익명 함수 불가능<br />호이스팅 O | 익명 함수 가능<br />호이스팅X |
| 비고   |                                  |                               |



> 화살표 함수(Arrow Function)

- 함수를 비교적 간결하게 정의할 수 있는 문법
- function 키워드 생략 가능
- 함수의 매개변수가 단 하나 뿐이라면, '()'도 생략가능
- 함수 몸통이 표현식 하나라면 '{}'과 return도 생략 가능

```javascript
const arrow = function (name) {
    return `hello ${name}`
}

// 1. function 키워드 삭제 및 '=>' 추가
const arrow1 = (name) => {return `hello ${name}`}

// 2. 매개변수가 1개일 경우 ( ) 생략 가능
const arrow2 = name => {return `hello ${name}`}

// 3. 함수 바디가 return을 포함한 표현식 1개일 경우에 {} & return 삭제 가능 
const arrow3 = name => `hello ${name}`

```