## JavaScrpit 기초

> JavaScrpit의 필요성

- 브라우저 화면을 조작하여 동적으로 만들 수 있는 유일한 언어!



> BOM 이란?

- Browser Object Model
- 자바스크립트가 브라우저와 소통하기 위한 모델
- 브라우저의 창이나 프레임을 추상화해서 프로그래밍적으로 제어할 수 있도록 제공하는 수단
  - 버튼, URL 입력창, 타이틀 바 등 브라우저 윈도우 및 웹 페이지 일부분을 제어 가능
- window 객체는 모든 브라우저로부터 지원받으며 브라우저의 창(window)를 지칭



> JavaScript Core

- 브라우저 (BOM & DOM)을 조작하기 위한 명령어 약속(언어) 
- ECMAScript(JS)



> 식별자 정의와 특징

- 식별자(identifier)는 변수를 구분할 수 있는 변수명을 말함
- 식별자는 반드시 문자, 달러($) 또는 밑줄(_)로 시작
- 대소문자를 구분하며, 클래스명 외에는 모두 소문자로 시작
- 예약어* 사용 불가능
  - for, if, function 등



> 식별자 작성 스타일

- 카멜케이스(camelCase), 두번째 단의어 첫 글자부터 대문자 사용
  - 변수, 객체, 함수

```javascript
//변수
let varibleName
//객체
const userInfo = {name : 'TOM', age : 20}
//함수
function getName() {}
```

- 파스칼 케이스(PascalsCal), 모든 단어의 첫번째 글자
  - 클래스, 생성자

```javascript
//클래스
class User {}
```



- 대문자 스네이크 케이스(SNAKE_CASE), 모든 단어 대문자 작성 & 단어사이에 언더스코어 삽입
  - 상수(constants)에 사용
    - 상수는 개발자의 의도와 상관없이 변경될 가능성이 없는 값을 말함

```javascript
//값이 바뀌지 않을 상수
const API_KEY = 'my-key'
const PI = Math.PI
```



> 변수 선언 키워드 let, const

|                       let                        |                        const                         |
| :----------------------------------------------: | :--------------------------------------------------: |
| `재할당` 할 예정인 변수 선언시 사용(재할당 가능) | `재할당` 예정이 없는 변수 선언시 사용(재할당 불가능) |
|               변수 `재선언` 불가능               |                변수 `재선언`  불가능                 |
|                   블록스코프*                    |                     블록스코프*                      |

*블록스코프 

- if, for 함수 등의 중괄호 내부를 가리키며, 블록스코프를 가지는 변수는 블록 바깥에서 접근이 불가능



> 데이터 타입

|              원시 타입               |              참조 타입               |
| :----------------------------------: | :----------------------------------: |
|        객체가 아닌 기본 타입         |          객체 타입의 자료형          |
|     변수에 해당 타입의 값이 담김     |  변수의 해당 객체의 참조 값이 담김   |
| 다른 변수에 복사할 때 실제 값이 복사 | 다른 변수에 복사할 때 참조 값이 복사 |



> 원시 타입

1. 숫자(Number) 타입
   - 정수, 실수 구분 없이 모두 숫자 타입
   - 부동 소수점 형식을 따름
   - NaN(Not-A-Number)
     - 계산 불가능한 경우 반환되는 값이나, 숫자 타입이다.

```javascript
const a = 13 // 양의 정수
const b = -5 // 음의 정수
const c = 3.14 // 실수
const d = 2.998e8 // 거듭제곱
const f = Infinity // 양의무한대
const g = NaN // 산술 연산 불가
```



2. 문자열(String) 타입
   - 텍스트 데이터를 나타내는 타입
   - 16비트 유니코드 문자의 집합
   - 작은따옴표, 큰따옴표 모두 가능
   - 템플릿 리터럴(Template Literal)
     - ES6부터 지원, 따옴표 대신 ``으로 표현
     - ${expression} 형태로 표현식 삽입 가능

```javascript
const firstName = 'Brandan'
const lastName = 'Eich'
const fullName = `${firstName} ${lastName}`

console.log(fullName) // Brandan Eich
```



3. undefined
   - 변수의 값이 없음을 나타내는 데이터 타입
   - 변수 선언 이후 직접 값을 할당하지 않으면, 자동으로 undefined가 할당됨 
   - typeof 연산자의 결과 `undefined`

```javascript
let firstName
console.log(firstName) // undefined
```



4. null
   - 변수의 값이 없음을 `의도적`으로 표현할 때 사용하는 데이터 타입
   - undefined와 마찬가지로 변수의 값이 없음을 나타내지만, typeof 연산자의 결과는 `객체(object)`로 표현됨

```javascript
let firstName = null
console.log(firstName) // null

typeof null // object
```



5. Boolean
   - 논리적 참 또는 거짓을 나타내는 타입
   - true(파이썬과 달리 첫글자가 소문자) 또는 false로 표현
   - 조건문 또는 반복문에서 유용하게 사용하는데, boolean이 아닌 데이터 타입들은 자동 형변환 규칙에 따라 true 또는 false로 변환

| 데이터 타입 |    거짓    |        참        |
| :---------: | :--------: | :--------------: |
|  undefined  | 항상 거짓  |                  |
|    null     | 항상 거짓  |                  |
|   number    | 0, -0, NaN | 나머지 모든 경우 |
|   string    | 빈 문자열  | 나머지 모든 경우 |
|   object    |            |     항상 참      |

