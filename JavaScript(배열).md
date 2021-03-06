## 배열 in JavaScript

> ##### 배열의 정의와 특징

- 키와 속성들을 담고 있는 참조타입의 객체(object)
- 순서를 보장하는 특징이 있음
- 주로 대괄호를 이용하여 생성하고, 0을 포함한 양의 정수 인덱스로 특정 값에 접근 가능
- 배열의 길이는 array.length 형태로 접근 가능



> 배열 관련 주요 메서드(기초)

- array.reverse()
  - 원본배열의 요소들의 순서를 반대로 정렬

```javascript
const numbers = [1, 2, 3, 4, 5]
numbers.reverse()
console.log(numbers) //[5, 4, 3, 2, 1]
```



- array.push() / array.pop()
  - 배열의 가장 뒤에 요소추가 / 마지막 요소 제거

```javascript
const numbers = [1, 2, 3, 4, 5]
numbers.psuh(100)
console.log(numbers)
    
numbers.pop()
console.log(numbers)
```



- array.unshift() / array.shift()
  - 배열의 가장 앞에 요소 추가 / 첫번째 요소 제거

```javascript
const numbers = [1, 2, 3, 4, 5]
numbers.unshift(100)
console.log(numbers)
    
numbers.shift()
console.shift(numbers)
```



- array.includes(value)
  - 배열에 특정 값이 존재하는지 판별 후 참 또는 거짓 반환

```javascript
const numbers = [1, 2, 3, 4, 5]
console.log(numbers.includes(1)) // true
console.log(numbers.includes(100)) // false
```



- array.indexOf(value)
  - 배열에 특정 값이 존재하느닞 확인 후 가장 첫번째로 찾은 요소의 인덱스 반환
  - 만약 해당 값이 없을 경우 -1 반환

```javascript
const numbers = [1, 2, 3, 4, 5]
let result

result = numbers.indexOf(3) // 2
console.log(result)

result = numbers.indexOf(100) // -1
console.log(result)
```



- array.join([separator])
  - 배열의 모든 요소를 연결하여 반환
  - 구분자는 선택적으로 지정 가능하며, 생략 시 쉼표를 기본 값으로 사용



```javascript
console.log(result)const numbers = [1, 2, 3, 4, 5]
let result

result = numbers.join() // 1,2,3,4,5
result = numbers.join('') // 12345
result = numbers.join(' ') // 1 2 3 4 5 
result = numbers.join('-') // 1-2-3-4-5
```



> Spread operator

- spread operator(...)를 사용하면 배열 내부에서 배열 전개 가능
- 얕은 복사에 활용 가능

```javascript
const array = [1, 2, 3]
const newArray = [0, ...array, 4]

console.log(newArray) // [0, 1, 2, 3, 4]
```

 



> 배열 관련 주요 메서드(심화)

- 배열을 순회하며 특정 로직을 수행하는 메서드
- 메서드 호출 시 인자로 **`callback 함수`**를 받는 것이 특징
  - **`callback 함수`**: 어떤 함수의 내부에서 실행될 목적으로 인자로 넘겨받는 함수를 말함



- array.forEach(callback(element[, index[,array]]))
  - 배열의 각 요소에 대해 콜백 함수를 한 번씩 실행
  - 콜백 함수는 3가지 매개변수로 구성
    - element, index, array
  - 반환 값(return)이 없는 메서드

```javascript
array.forEach(element, index, array) = > {
	//do something
})

const friuts = ['딸기', '수박', '사과', '체리']
friuts.forEach((fruit, index) => {
    console.log(fruit, index)
	}
)

friuts.forEach(
	function (elem, idx, arr) {
        console.log(elem, idx, arr)
    }
)
```



- array.map(callback(element[, index[,array]]))
  - 배열의 각 요소에 대해 콜백 함수를 한 번씩 실행
  - 콜백 함수의 반환 값을 요소로 하는 새로운 배열 반환
  - 기존 배열 전체를 다른 형태로 바꿀 때 유용

```javascript
array.map(element, index, array) = > {
	//do something
})

const numbers = [1, 2, 3, 4, 5]

const doubleNums = numbers.map((num) => {
    return num * 2
})
console.log(doubleNums) //[2, 4, 6, 8, 10]
```



- array.filter(callback(element[, index[,array]]))
  - 배열의 각 요소에 대해 콜백 함수를 한 번씩 실행
  - 콜백 함수의 반환 값이 참인 요소들만 모아서 새로운 배열을 반환
  - 기존 배열의 요소들을 필터링할때 유용

```javascript
array.filter(element, index, array) = > {
	//do something
})

const numbers = [1, 2, 3, 4, 5]

const oddNums = numbers.filter((num, index) => {
    return num % 2
})
console.log(oddNums) // [1, 3, 5]
```



- array.reduce(callback(acc, element[, index[,array]])[, initialValue])
  - 배열의 각 요소에 대해 콜백 함수를 한 번씩 실행
  - 콜백 함수의 반환 값들을 하나의 값(acc)에 누적 후 반환
  - reduce 메서드의 주요 매개변수
    - acc
      - 이전 callback 함수의 반환 값이 누적되는 변수
    - initialValue(optional)
      - 최초 callback 함수 호출 시 acc에 할당되는 값, default 값은 배열의 첫 번째 값
      - 빈 배열의 경우 initialValue를 제공하지 않으면 에러 발생

```javascript
const numbers = [1, 2, 3]
const result = numbers.reduce(
	(acc, elem, idx, arr) => {
        console.log(acc, elem, idx, arr)
    }, 0
)
```



- array.find(callback(element[, index[,array]]))
  - 배열의 각 요소에 대해 콜백 함수를 한 번씩 실행
  - 콜백 함수의 반환 값이 참이면, 조건을 만족하는 첫번째 요소를 반환
  - 찾는 값이 배열에 없으면 undefined 반환

```javascript
const avengers = [
    { name: 'Tony Stark', age: 45},
]
```



- array.some(callback(element[, index[,array]]))
  - 배열의 요소 중 하나라도 주어진 판별 함수를 통과하면 참을 반환
  - 모든 요소가 통과하지 못하면 거짓 반환
  - 빈 배열은 항상 거짓 반환

```javascript
const numbers = [1, 3, 5, 7, 9]

const hasEvenNumver = numbers.some((num) = > {
    return num % 2 === 0
})
console.log(hasEvenNumver) // false
```





- array.every(callback(element[, index[,array]]))
  - 배열의 모든 요소가 주어진 판별 함수를 통과하면 참을 반환
  - 하나의 요소라도 통과하지 못하면 거짓 반환
  - 빈 배열은 항상 참 반환