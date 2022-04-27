## 객체 in JavaScript

- 객체는 속성(property)의 집합이며, 중괄호 내부에 key와 value의 쌍으로 표현
- key는 문자열 타입만 가능
  - key 이름에 띄어쓰기 등으 구분자가 있으면 따옴표로 묶어서 표현
- value는 모든 타입(함수포함) 가능
- 객체 요소 접근은 점 또는 대괄호로 가능
  - key 이름에 띄어쓰기 같은 구분자가 있다면 대괄호 접근만 가능

```javascript
const me = {
    name: 'jack',
    phoneNumber : '01012345678'
    'samsung products' : {
    buds: 'Galaxy Buds'
    galaxy : 'Galaxy s20'
}}
console.log(me.name)
console.log(me.phoneNumber)
console.log(me['samsung products'])
console.log(me['samsung products'].buds)
```



> 객체와 메서드

- 메서드는 어떤 객체의 송성이 참조하는 함수
- 객체.메서드명()으로 호출 가능
- 메서드 내부에서는 this 키워드가 객체를 의미함
  - fullName은 메서드가 아니기 때문에 정상출력 되지 않음(NaN)
  - getFullName은 메서드 이기 때문에 해당 객체의 firstName과 lastName을 정상적으로 이어서 반환

```javascript
const me = {
    firstName: 'John',
    lastNane: 'Doe',
    
    fullName: this.firstName + this.lastNane
    getFullName: function () {
        return this.firstName + this.lastNane
    }
}
```

