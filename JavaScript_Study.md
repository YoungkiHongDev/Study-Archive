# 자바스크립트
HTML과 CSS로 만들어진 웹페이지를 동적으로 변경해주는 언어

# 변수
**let**
변할 수 있는 값

사용예)
let name = "A"
let name = "B" // 에러 발생

let name = "A"
name = "B" // 정상 실행

**const**
변하지 않는 값 (상수)
상수인걸 쉽게 알아볼 수 있게 변수명은 대문자로 작성

개발팁)
모든 변수 const로 만들고 나중에 변하는 값만 let으로 바꿔주기

# 자료형
const name = "Mike"; //문자형
const age = 30; //숫자형

백틱`` -> 변수출력시 사용, 따옴표쓰면 변수가 출력이 안됌
const message = `My name is ${name}`;

const a = true; //참
const b = false; //거짓

console.log(typeof name) // typeof -> 타입반환

/*
  typeof null -> object
  객체가 뜨지만 사실 객체가 아닌 초기 버전의 오류다.
  하위 버전과의 호환성 유지를 위해 고치지 않고 있다.
*/

const c = "나는"
const d = "공부한다"
console.log(c+d) //문자형을 더하면 합쳐진다.

# 대화상자
alert	알려줌
prompt	입력받음
confirm	확인받음

const name = prompt("이름을 입력하세요");
confirm(`이름이 ${name} 맞습니까?`);
alert(`안녕하세요, ${name}님, 환영합니다`);

prompt는 취소를 누르면 null을 반환한다.
prompt는 매개변수를 2개 받을 수 있다.
prompt(메세지, 디폴트값)

const isAdult = confirm("당신은 성인 입니까?")
console.log(isAdult) //확인누르면 true, 취소누르면 false
confirm은 결제 하시겠습니까? 삭제 하시겠습니까? 물을 때 많이 사용한다.

단점)
1. 스크립트 일시 정지
2. 스타일링 불가능

위치, 모양을 정할 수 없고 브라우저마다 모양도 다르다.
하지만 기본 메소드라 빠르고 간단하게 적용가능하여 많이 사용한다.

# 형 변환
String() //문자형으로 변환
Number() //숫자형으로 변환
Boolean() //참이나 거짓으로 변환

Number(null)        //0값
Number(undefined)   //NaN값

Boolean(0)      //거짓
Boolean("0")    //참
Boolean('')     //거짓
Boolean(' ')    //참