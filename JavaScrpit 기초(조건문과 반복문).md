> 조건문의 종류와 특징

- 'if' statement
  - 조건 표현식의 결과값을 Boolean 타입으로 변환 후 참/거짓을 판단
- 'switch' statement
  - 조건 표현식의 결과값이 어느 값(case)에 해당하는지 판별
  - 주로 특정 변수의 값에 따라 조건을 분기할 때 활용하며, 조건이 많아질 경우 if문보다 가독성이 나을 수 있음



> if statement

- if, else if, else
  - 조건은 소괄호(condition) 안에 작성
  - 실행할 코드는 중괄호{} 안에 작성
  - 블록 스코프 생성

```javascript
if (condition) {
	//do something
} else if (condition) {
	//do something
} else {
	//do something
}
```

- 예시

```javascript
const nation = 'Korea'

if (nation === 'Korea') {
    console.log('안녕하세요!')
} else if (nation === 'France') {
    console.log('봉쥬르!')
} else {
   console.log('하이!') 
}
```



> switch statement

- switch
  - 표현식(expression)의 결과값을 이용한 조건문
  - 표현식의 결과값과 case문의 오른쪽 값을 비교
  - break 및 default 문은 [선택적]으로 사용 가능
  - <u>break문이 없는 경우 break문을 만나거나 default문을 실행할 때까지 다음 조건문 실행</u>
  - 블록 스코프 생성

```javascript
const nation = 'Korea'
switch(nation) {
    case 'Korea': {
		console.log('안녕하세요!')
		break
  }
    case 'France': {
		console.log('봉주르!')
		break
  }
    default: {
        console.log('하이!')
    }
}
```



> 반복문의 종류와 특징

- while
- for
- for ... in
  - 주로 객체(object)의 속성들을 순회할 때 사용
  - 자바스크립트에서 객체는 딕셔너리(키:밸류)를 의미한다고 생각하면 된다.
  - 배열도 순회 가능하지만 인덱스 순으로 순회한다는 보장이 없으므로 권장하지 않음

- for ... of
  - 반복 가능한(iterable) 객체를 순회하며 값을 꺼낼 때 사용
    - 반복 가능핸 객체 : Array, Map, Set, String 등



>while

- 조건문이 참(true)인 동안 반복 시행
- 조건은 소괄호 안에 작성
- 실행할 코드는 중괄호 안에 작성

```javascript
/*
  [while문 연습]
  
  아래의 조건을 만족하는 while문을 작성하세요.
  - 주어진 변수 evenNumber를 2씩 증가시키고, 해당 값을 출력합니다.
  - evenNumber가 6이 되면 반복문을 종료합니다.
*/
// 개발자 도구 console창에서 실행시 최종 6은 console.log의 결괏값이 아닌, evenNumber에 담긴 값임

let evenNumber = 0

while (evenNumber < 6) {
  console.log(evenNumber)
  evenNumber += 2
}

console.log(evenNumber)
```



> for

- 세미콜론(;)으로 구분되는 세 부분으로 구성
- initialization
  - 최초 반복문 진입시 1회만 실행되는 부분
- condition
  - 매 반복 시행 전 평가되는 부분
- expression
  - 매 반복 시행 이후 평가되는 부분
- 블록 스코프 생성

```javascript
for (initialization; condition; expression) {
	//do something
}

/*
  [for문 연습]
  
  아래의 조건을 만족하는 for문을 작성하세요.
  - oddNumber라는 이름의 변수를 선언 및 1로 초기화합니다.
  - 매 시행마다 oddNumber를 2씩 증가시키고, 해당 값을 출력합니다.
  - oddNumber가 5가 되면 반복문을 종료합니다.
*/

for (let oddNumber = 1; oddNumber < 5; oddNumber += 2) {
}
```



> for ... in

- 객체(object)의 속성(key)들을 순회할 때 사용
- 배열도 순회 가능, 권장 X
- 실행할 코드는 중괄호 안에 작성
- 블록 스코프 생성

```javascript
for (varible in object) {
    //do something
}
/*
  [for... in 연습]

  Tip.
    JS 객체의 value는 점(.) 또는 대괄호 표기법을 이용하여 
    key값을 통해 접근 가능합니다. ex) obj.key, obj[key]
  
  - 주어진 객체를 순회하면서 예시와 같이 출력합니다.
  - 예시) title: '벤자민 버튼의 시간은 거꾸로 간다'
*/
const bestMovie = {
  title: '벤자민 버튼의 시간은 거꾸로 간다',
  releaseYear: 2008,
  actors: ['브래드 피트', '케이트 블란쳇'],
  genres: ['romance', 'fantasy'],
}

for (const key in bestMovie) {
  console.log(`${key} : ${bestMovie[key]}`)
}
```



> for ... of

- 반복 가능한(iterable) 객체를 순회하며 값을 꺼낼 때 사용

```javascript
for (varible of object) {
    //do something
}

/*
  [for... of 연습]
  
  Tip.
    JS 객체의 value는 점(.) 또는 대괄호 표기법을 이용하여
    key값을 통해 접근 가능합니다. ex) obj.key, obj[key]

  - 주어진 배열을 순회하면서 예시와 같이 출력합니다.
  - 예시) title: '어바웃 타임'
*/
const movies = [
  {title: '어바웃 타임'},
  {title: '굿 윌 헌팅'},
  {title: '인턴'},
]

for (let movie of movies) {
    console.log(`title: ${movie.title}`)
}
```

