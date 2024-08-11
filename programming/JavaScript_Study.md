# JavaScript
JavaScript는 웹 페이지를 동적으로 동작하도록 만들어주는 프로그래밍 언어이다.  
시작은 웹 페이지였지만, 현재는 서버, 데이터베이스, 게임, 영상, 인공지능, 스트리밍 등 다양한 분야에 활용되고 있다.


# 변수 선언 키워드
- var: 재선언 가능, 재할당 가능 (협업 시 문제 발생 가능)
- let: 재선언 불가능, 재할당 가능 (권장)
- const: 재선언 불가능, 재할당 불가능 (권장)

> var는 변수의 중복 선언이 가능하여, 협업 시 로직 오류를 일으킬 수 있다.  
따라서, let 또는 const를 사용하는 것이 좋다.


# 문자열 연산
```javascript
"Hello" + "World"   // "HelloWorld"
```
- 문자열끼리 더하면 두 문자열이 하나로 합쳐진다.

```javascript
"a" - 10    // NaN
"a" * 10    // NaN
"a" / 10    // NaN
"a" % 10    // NaN
```
- 더하기를 제외한 연산자는 문자열과 숫자의 혼합 연산 시 `NaN`(Not a Number)을 반환한다.

```javascript
"10" + 10  // "1010" (String)
"10" - 10  // 0 (Number)
"10" * 10  // 100 (Number)
"10" / 10  // 1 (Number)
"10" % 10  // 0 (Number)
```
- 문자열로 된 숫자와 숫자를 더하면 문자열로 합쳐진다.
- 더하기 외의 연산에서는 문자열이 숫자로 변환된 후 연산이 이루어진다.


# 배열 (Array)
```javascript
let ranking = ["Jason", "Alice", "Chris", "Jane", "Tom"];   // 배열 선언
ranking[0]          // 배열 접근
ranking.length      // 배열 길이
```

## 배열의 메소드
```javascript
Array.push(value)      // 배열의 끝에 데이터 추가
Array.pop()            // 배열의 끝 데이터를 제거하고 반환
Array.includes(value)  // 배열에 특정 데이터가 있는지 여부 확인
Array.indexOf(value)   // 배열에서 특정 데이터의 인덱스 값 반환
```


# 객체 (Object)
```javascript
let userData = {
    name: 'Jason',
    age: 25,
    gender: 'male'
};
```
객체는 여러 개의 프로퍼티(속성)를 갖는 데이터 타입이다.  
각 프로퍼티는 `key`와 `value`의 쌍으로 구성된다.

## 객체의 접근방식
- Dot notation
```javascript
// 객체의 키에 접근하여 값 호출
userData.name  // "Jason"

// 객체에 없는 프로퍼티 추가
userData.email = "jason@gmail.com";
```

- Bracket notation
```javascript
// 객체의 키에 접근하여 값 호출
userData["name"]  // "Jason"

// 객체에 없는 프로퍼티 추가
userData["email"] = "jason@gmail.com";
```

> `Bracket notation`에서 `userData[name]`과 같이 접근할 경우, `name`이라는 변수가 선언되어 있지 않으면 `undefined`가 반환된다. 따라서, 반드시 `userData["name"]`처럼 접근해야 한다.

## 객체의 메소드
```javascript
Object.keys(userData)  // ["name", "age", "gender"]
Object.values(userData)  // ["Jason", 25, "male"]
```
- `Object.keys()`: 객체의 프로퍼티 키를 배열로 반환
- `Object.values()`: 객체의 프로퍼티 값을 배열로 반환


# 함수 (Function)
함수는 특정 기능을 수행하거나 계산을 실행하는 코드의 집합이다.

```javascript
// 함수 선언
const sum = function() {
    console.log(10 + 10);
};

// 함수 호출
sum();  // 20
```

## HTML 태그에 함수 연결
HTML 태그에 JavaScript 함수를 연결하려면 이벤트 속성을 사용한다.

```javascript
<script>
    const output = function() {
        console.log('function run');
    };
</script>

// HTML
<button onclick="output()">버튼</button>
```

> `script` 태그 안에 함수를 선언하고, HTML의 `onclick` 속성을 통해 버튼 클릭 시 함수를 호출할 수 있다.


# querySelector로 데이터 참조
`document.querySelector()`를 사용하여 HTML 요소의 값을 가져올 수 있다.

```javascript
<script>
    const dateFormMaker = function() {
        const inputYear = document.querySelector('#target-year-input').value;
        const inputMonth = document.querySelector('#target-month-input').value;
        const inputDay = document.querySelector('#target-day-input').value;
        console.log(`${inputYear}-${inputMonth}-${inputDay}`);
    };
</script>

// HTML
<body>
    <input id="target-year-input" class="target-input" />
    <input id="target-month-input" class="target-input" />
    <input id="target-day-input" class="target-input" />
    <button onclick="dateFormMaker()">버튼</button>
</body>
```

> `.value`를 붙이지 않으면 태그 자체를 가져오므로, 값을 가져오려면 반드시 `.value`를 사용해야 한다.


# 날짜 정보 객체 (Date)
`Date` 객체는 날짜 정보를 담고 있으며, 현재 시간이나 특정 날짜를 나타낼 수 있다.

```javascript
let now = new Date();
let target = new Date('2023-11-10');
console.log(now - target);
```

> `Date` 객체를 사용하여 현재 시간과 목표 날짜 간의 차이를 계산할 수 있으며, 이 차이는 밀리초 단위로 반환된다.