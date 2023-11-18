# JavaScript
웹 페이지를 동적으로 동작하도록 만들어주는 프로그래밍 언어이다.  
시작은 웹 페이지였지만 활동영역을 빠르게 넓혀서 서버, 데이터베이스, 게임, 영상, 인공지능, 스트리밍 등 다양한 곳에 활용되고 있다.

# 변수 선언 키워드
- var: 재선언O, 재할당O
- let: 재선언X, 재할당O
- const: 재선언X, 재할당X

var의 경우 협업 시 내가 만든 변수를 다른 개발자가 모르고 다시 만들어서 로직에 오류를 발생시킬 수 있으므로 var를 사용하지 않고, let을 사용한다.

# 문자 & 연산
- "Hello" + "World" = "HelloWorld"

문자열끼리 더하면 합쳐진다.

- "a" - 10 = NaN
- "a" * 10 = NaN
- "a" / 10 = NaN
- "a" % 10 = NaN

더하기를 제외한 연산자를 문자와 숫자에 혼합연산하면 Not a Number를 뜻하면 NaN이 나온다.

- "10" + 10 = "1010" //String
- "10" - 10 = 100 //Number
- "10" * 10 = 100 //Number
- "10" / 10 = 100 //Number
- "10" % 10 = 100 //Number

문자열로 된 숫자와 숫자를 연산하면 더하기는 그대로 합쳐져 문자열이 나온다. 

더하기를 제외한 연산은 문자열이 숫자라면 숫자로 변환하여 연산을 진행하여 숫자값이 나온다.

# 배열 Array
- 배열선언 : let ranking = ["Jason", "Alice", "Chris", "Jane", "Tom"]
- 배열접근 : ranking[0] ~ ranking[4]
- 배열길이 : Array.length

# 배열의 메소드
- Array.push() : 배열의 가장 끝에 데이터를 추가하는 메소드
- Array.pop() : 배열의 가장 끝에 위치한 데이터를 제거하는 메소드, pop() 동작 시 삭제한 데이터가 어떤 데이터인지 반환
- Array.includes() : 배열에 특정 데이터가 존재하는지 여부를 확인하는 메소드, 여부에 따라 true나 false를 반환
- Arary.indexOf() : 배열에서 특정 데이터의 인덱스 값을 반환하는 메소드

# 객체 Object
```javascript
let userData = {
    name: 'Jason',
    age: 25,
    gender: 'male'
};
```
객체는 여러개의 프로퍼티(속성)를 갖는 데이터 타입이다.  
각 프로퍼티는 key와 value의 쌍으로 관리된다.

# 객체 접근방식
- Dot notation
```javascript
//객체의 키에 접근하여 벨류 호출
userData.name //Jason

//객체에 없는 프로퍼티를 추가
userData.email = "jason@gmail.com"

/*
let userData = {
    name: 'Jason',
    age: 25,
    gender: 'male',
    email: 'jason@gmail.com'
};
*/
```

- Bracket notation
```javascript
//객체의 키에 접근하여 벨류 호출
userData["name"] //Jason

//객체에 없는 프로퍼티를 추가
userData["email"] = "jason@gmail.com"
```
브라켓 노테이션에서 userData[name]과 같이 접근하려고 할 경우 객체의 key가 아니라 따로 선언한 name이라는 변수에 접근하려고 한다.

변수가 선언되어 있지 않다면 결과가 undefind로 나오므로 예제와 같이 ""로 감싸서 접근해야 한다.

하지만 만약에, name = "age"와 같이 변수가 key와 같은 문자열을 값으로 가진다면 age의 value인 25가 출력될 수 있다.

# 객체 메소드
- Object.keys() : 객체 프로퍼티들의 key만 가져와서 배열에 담아주는 메소드, key들은 문자열 데이터로 가져온다.

```javascript
// userData의 key로 이루어진 배열 생성
let userArray = Object.keys(userData) //["name", "age", "gender"]

// name이라는 key를 가졌는지 여부를 확인
userArray.includes("name") //true
```

- Object.values() : 객체 프로퍼티들의 value만 가져와서 배열에 담아주는 메소드, 객체 프로퍼티 값들은 어떠한 데이터도 입력될 수 있으므로 key처럼 문자열 데이터로만 가져오지 않는다.

```javascript
// userData의 value로 이루어진 배열 생성
let userArray = Object.values(userData) //["Jason", 25 , "male"]
```

# 함수
어떠한 기능을 수행하거나 계산을 수행하는 코드의 집합이다. 함수를 사용하려면 호출하는 방법과 함수 선언의 종류를 알아야한다.

```javascript
// 자바스크립트 함수의 형태
const sum = function() {
    console.log(10+10);
};

// 자바스크립트 함수의 호출
sum();
```

function()은 자바스크립트의 함수라는 것을 알려주는 키워드이다. 함수를 실행시키면 {} 안의 코드가 실행된다.

# 함수 연결
html 태그에 자바스크립트 함수를 연결시키는 방법은 속성을 사용하면 된다.

```javascript
<script>
        const output = function() {
            console.log('function run');
        };
</script>

// HTML
<button onclick="output()">버튼</button>
```

예제와 같이 script 태그 안에 함수를 만들어 놓고, onclick과 같은 이벤트 속성을 사용하여 연결하면 함수를 원하는 때에 호출시킬 수 있다. 예제에서는 버튼을 클릭하면 함수가 호출되고 함수의 코드가 실행된다.

# querySelector 데이터 참조
```javascript
<script>
        const dateFormMaker = function() {
            const inputYear = document.querySelector('#target-year-input').value;
            const inputMonth = document.querySelector('#target-month-input').value;
            const inputDay = document.querySelector('#target-day-input').value;
            console.log(inputYear + "-" + inputMonth + "-" + inputDay);
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

document 객체의 querySelector를 활용하면 HTML의 input 태그의 값을 가져올 수 있다.
id값으로 가져올 경우 '#id' 형태로 매개변수를 주고 querySelector 뒤에 .value를 붙이면 값을 가져올 수 있다. 만약에, .value를 붙이지 않는다면 태그 자체를 가져오게 된다.

# 날짜 정보 객체 Date
Date는 날짜 정보를 담고 있는 객체로 우리가 원하는 시간대를 날짜 형식에 맞춘 데이터를 반환한다.
예를들어, new Date() 라고 쓰면 현재 요일, 달, 일, 연도 같은 정보와 현재 시간까지 보여준다.
현재가 2023년 10월 10일이고 기다리고 있는 날짜가 있으며, 그 날짜가 2023년 11월 10일이라고 가정한다면 목표 날짜를 담은 변수에서 현재 날짜를 담은 변수를 빼기하며 0.000초 단위로 얼마나 남았는지 나오게 된다. 그리고 그 값을 연산하여 남은 시간, 남은 분, 남은 초 등을 알 수 있다. 

```javascript
now = new Date()
target = new Date('2023-11-10')
console.log(now - target)
```