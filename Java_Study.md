# 자바 개념
## C언어와 JAVA의 차이점
**C언어**
- 절차지향의 대표적인 언어
- 이식성이 뛰어남
- 개발자가 메모리를 직접 관리
- 시스템 프로그래밍이 가능하고 속도가 빨라서 운영체제나 임베디드 개발에 활용
- 문제가 발생하면 순차적으로 수정해야하므로 유지보수가 어려움

**JAVA**
- 객체지향의 대표적인 언어
- 자바 가상 머신(JVM)을 이용해 다양한 운영체제에서 사용할 수 있는 독립성을 갖춤
- 가비지 컬렉션을 이용해 메모리를 자동으로 관리
- 문제가 발생하면 문제가 되는 객체만 수정하면 되므로 유지보수가 용이함

## JAVA 버전
- 8버전부터 LTS / Non-LTS 버전으로 나뉘어 릴리즈
- LTS : 8년 동안 업데이트를 지원하는 버전
- Non-LTS : 새로운 버전이 출시되면 더이상 업데이트를 지원하지 않는 버전

## JAVA 주요 특징
- 객체지향 언어
- 분산처리 지원
- 멀티스레드 지원
- OS 플랫폼 독립성 : C언어의 경우 동일한 프로그램을 OS에 따라 달리 제작하지만 JAVA는 JVM 위에서 동작하므로 JVM을 OS에 맞게 설치해야 한다.
- 가비지 컬렉션 : 메모리에 인스턴스 객체를 만들면 사용 후 자동으로 해제한다.

## JAVA 동작 방식
- 1. 에디터 : 소스코드 Hello.java 작성
- 2. 컴파일러 : Hello.java를 컴파일하여 Hello.class 산출
- 3. 클래스로더 : 사용된 클래스들을 로딩해서 Hello.class 파일에 클래스들을 합침
- 4. 바이트코드 검증기 : Hello.class 파일의 바이트코드를 검증
- 5. 인터프리터 : 검증된 Hello.class를 한줄씩 번역

## JDK
- 자바 개발 도구
- 자바가 동작할 수 있는 실행환경
- 자바 프로그램을 개발하는 데 필요한 도구 Ex) 컴파일러

## JVM
- 자바 가상 머신
- 바이트 코드 파일로 구성되는 자바 프로그램
- JVM이 운영체제에 맞춰 해석
- 다양한 운영체제에서 사용 가능

## JAVA 설치 과정
- https://www.oracle.com/java/technologies/downloads/
- java -version //자바 버전 확인 명령어로 설치유무 확인
- 최근에는 자바 설치 시 자바 환경 변수가 자동 등록됨

## 자바 환경 변수
- JDK 안에는 java.exe 런처 파일, javac.exe 컴파일러 파일 등의 도구가 있음
- 도구를 어느 폴더에서도 실행 할 수 있도록 자바 환경 변수를 등록이 필요했지만 최근에는 자동으로 등록
- 그러나 버전을 변경하려면 환경 변수를 수동으로 등록하여 원하는 버전의 JDK를 지정

## JAVA 버전 변경
- 새로운 버전의 JDK를 설치
- 시스템 변수 Path에 자동 등록되어 있는 자바 환경 변수 삭제
- 시스템 변수 Path에 원하는 JDK의 bin 폴더 경로 등록
- java -version으로 버전 확인

# 객체지향 프로그래밍 OOP
**개념**
- 작은 문제들을 해결하는 객체를 만듬
- 만든 객체들을 조합해 큰 문제를 해결하는 Bottom-UP 방식

**장점**
- 코드의 재사용성이 높아짐
- 유지보수가 쉬움
- 코드가 간결해짐

**단점**
- 처리 시간이 비교적 오래 걸림
- 프로그램 설계 시 많은 시간을 투자해야함

## OOP의 4가지 특징
**1. 캡슐화**
- 유사한 속성과 메소드를 하나의 클래스로 모은것
- 로직이나 변수를 감추고 API만 외부에 제공하는 정보 은닉이 가능

**2. 상속**
- 자식 클래스가 상속을 받아 부모 클래스의 멤버 변수나 메소드를 사용 가능
- 클래스의 재사용이 용이함

**3. 추상화**
- 클래스들의 공통적인 메소드들을 인터페이스로 정의하는 것

**4. 다형성**
- 자신의 서브클래스에서 생성한 인스턴스도 클래스 변수에 대입할 수 있는 것
- Ex) 슈퍼클래스 변수 선언 -> 슈퍼클래스 변수에 서브클래스의 인스턴스 대입
- 같은 이름의 메소드가 상황에 따라 다르게 동작하는 것
- 오버로딩, 오버라이딩이 있음

# 자바 문법
## 주석문
자바의 주석문에는 세 가지가 있다.
- // : 한 행을 주석으로 한다.
- /* */ : 여러 행을 주석으로 한다.
- /** */ : 클래스나 인터페이스 선언 바로 앞에서 설명을 위해 사용한다.

## 조건문
- if(조건식) { 조건이 참이라면 실행할 코드 }
- if(조건식) { 조건이 참이라면 실행할 코드 } else { 조건이 거짓이라면 실행할 코드 }
- switch(변수) case 값1 : 값1이라면 실행할 코드 작성, break로 탈출가능, 아무것도 해당하지 않으면 default 부분 실행

## 반복문
- for(초기식; 조건식; 증감식) { 반복 실행할 코드 }
- for(변수타입 변수 : 배열명) { 반복 실행할 코드 }
- while(조건식) { 반복 실행할 코드 }, break로 탈출하거나 continue로 바로 조건식으로 건너뛸 수 있다.

## 예외처리문
- try catch
- try에서 문제가 발생하면 catch를 실행시킨다.
- finally절을 사용하면 예외 발생 여부와 상관없이 실행시킬 수 있다.

## 논리 연산자
- && : and
- || : or

## 비트 연산자
- & : and
- | : or
- ^ : exclusive or (xor)
` ~ : not

## 배열 Array
- 자료형의 집합을 의미
- 배열의 길이는 고정
- 배열의 길이를 생성 시 값을 넣으면서 생성
- 또는 배열의 길이를 생성 시 지정하고 값을 삽입 
- 배열명.length 사용시 배열의 크기 확인 가능
- for 조건에서 Array.length를 따로 변수에 저장해서 쓰는 이유는 바로 안정성
- 반복문 안에서 길이가 변경되면 문제가 발생할 수도 있다!

## 리스트 List
- 리스트는 배열과 비슷한 자바의 자료형
- 배열과 차이점은 크기가 정해져 있지 않고 동적으로 변한다는 것
- 리스트는 크기가 정해져 있지 않아 원하는 만큼의 값을 담을 수 있다.

**리스트 불러오기**     
import java.util.ArrayList;

**리스트 생성**     
ArrayList pitches = new ArrayList();

**리스트 메소드**
- add() 리스트에 값 삽입    
pitches.add("138");

- add() 리스트 첫번째 위치에 값 삽입    
pitches.add(0, "138");

- get() 리스트 원소 반환    
pitches.get(0);

- size()
//리스트 원소의 수 리턴     
pitches.size();

- contains() 리스트 안에 해당 항목이 있는지 판별하여 결과를 true/false로 리턴      
pitches.contains("138");

- remove(객체) 리스트에서 객체에 해당하는 항목을 삭제하고 삭제 결과를 true/false로 리턴      
pitches.remove("129");

- remove(인덱스) 리스트에서 인덱스에 해당하는 항목을 삭제하고 삭제된 항목을 리턴       
pitches.remove(0);

**리스트 정렬**
- sort 메소드는 자바8 버전부터 사용 가능
- Comparator 클래스 불러오기    
import java.util.Comparator;

- 오름차순 정렬     
pitches.sort(Comparator.naturalOrder());

- 내림차순 정렬     
pitches.sort(Comparator.reverseOrder());

## 제네릭스
- 버전5 이후부터 사용 권고
- 어떤 객체를 포함하는지 명확하게 표현
- 인텔리제이에서 제네릭스를 아쓰면 warning이 표시됨

ArrayList<String> pitches = new ArrayList<String>();    
ArrayList<String> pitches = new ArrayList<>();

- 뒷 부분의 자료형은 생략이 가능하므로 2번째 방식을 선호
- 인텔리제이에서는 생략안하면 경고

## aList 메소드
- 이미 존재하는 배열의 데이터를 담은 리스트를 만들기 위한 메소드  
String[] data = {"123", "456", "789"};

- Arrays 클래스 불러오기    
import java.util.Arrays;

- Arrays 클래스의 asList 메소드 사용하여 ArrayList 생성     
ArrayList<String> pitches = new ArrayList<>(Arrays.asList(data));

- 다른 방식으로 직접 자료형을 여러개 전달하여 생성 가능     
ArrayList<String> pitches = new ArrayList<>(Arrays.asList("138", "129", "142"));

**리스트 모든 원소 한줄로 출력**    
- 리스트 생성   
ArrayList<String> pitches = new ArrayList<>(Arrays.asList("138", "129", "142"));    

## 조인 메소드
- String.join("구분자", 리스트객체) 사용하여 원소를 문자열로 합치기     
- String result = String.join(",", pitches);

## 정적 필드/메소드
- 인스턴스를 생성하지 않고 클래스 자체에서 사용되는 변수나 메소드
- 변수나 메소드 앞에 static 키워드를 붙여서 만든다.
- 정적 필드는 인스턴스 없이 '클래스명.변수명' 으로 호출해서 사용가능
- 정적 메소드는 인스턴스 없이 '클래스명.메소드명()' 으로 호출해서 사용가능
- 상수 필드는 final static 키워드를 붙이고 변수명을 대문자로 구성한다.
- 정적 메소드의 대표적인 예로 java.lang.Math 클래스에서 제곱을 구하는 pow() 같은 경우가 있다.

## 상속 (inheritance)
- 기존 클래스가 가지고 있는 것을 그대로 물려받으면서 필요한 필드나 메소드를 추가로 정의하는 것
- 부모클래스와 자식클래스 / 슈퍼클래스와 서브클래스
- final 키워드를 사용하면 상속이 금지된다.
- 상속을 받은 서브클래스는 클래스명 뒤에 extends 키워드와 슈퍼클래스명을 쓴다. public class Sub extends Super

## 오버로딩
- 클래스 내에서 메소드의 이름은 같지만 매개변수의 개수나 타입을 달리해서 사용하는 것
- 메소드 네이밍의 고민을 덜어줌
- 클래스 내에서 메소드의 이름이 같아도 파라미터의 개수나 데이터형만 다르면 어러 개를 선언할 수 있는 것
- 대표적인 예로 생성자의 파라미터를 다르게 해서 만드는 경우가 있다.

## 오버라이딩
- 부모 클래스의 메소드를 자식 클래스에서 용도에 맞게 재정의하는 것
- 오버로딩과 다르게 매개변수가 동일해야함
- 부모 클래스의 메소드와 같거나 넓은 범위의 접근 제어자만 사용 가능
- 슈퍼클래스에 있는 메소드와 같은 이름의 메소드를 서브클래스에서 재정의 하는 것
- 슈퍼클래스의 메소드를 호출할 경우 super.메소드명()으로 호출한다.

## 추상 클래스/메소드 (abstract)
- 추상 클래스는 인스턴스화를 금지하는 클래스 (인스턴스 생성 금지)
- 클래스 앞에 abstract 키워드를 사용하면 추상 클래스로 지정된다.
- 추상 메소드는 메소드 본체가 없는 메소드
- 메소드 앞에 abstract 키워드를 사용하면 추상 메소드로 지정된다.
- 추상 메소드를 포함하는 클래스는 추상 클래스로 지정해야한다.
- 추상 메소드는 {} 괄호를 쓰지 않는다.
- 사용 목적 : 공통적으로 사용되는 기능을 추상 메소드로 선언해놓고 추상 클래스를 상속받은 후 추상 메소드를 오버라이딩해서 사용하기 위함이다.

## 인터페이스
- class 키워드 대신에 interface 키워드를 사용한다.
- 내부에는 추상 메소드를 선언한다.
- 인터페이스를 상속받을 때 extends 키워드가 아니라 implements 키워드를 사용한다.
- Java는 다중 상속을 지원하지 않지만 인터페이스로 비슷하게 작성할 수 있다.
- Ex) public class A extends B implements C

## 익명 내부 클래스
- 이름이 없는 내부 클래스
- 주로 한번만 사용하고 버려지는 클래스에 사용

## 접근제어자
- OOP 특징 중 캡슐화와 관련된다.
- 클래스 내부의 변수나 메소드의 사용 범위를 결정한다.
- 사용목적 : 클래스 내부 정보를 외부에서 접근하지 못하게하여 결합도를 낮춘다.

**접근제어자의 종류**
1. private : 내부에서 접근 가능
2. default : 패키지 안에서 접근 가능
3. protected : 패키지 안과 외부에서 상속받은 경우 접근 가능
4. public : 항상 접근이 가능

## 컬렉션 프레임워크
- 크기가 고정되어 있지 않고 여러 객체를 담을 수 있는 라이브러리
- Iterable : 컬렉션의 상위 인터페이스로 컬렉션들을 표준화해서 Iterator() 메소드만으로 데이터를 읽어올 수 있도록 구현되어 있다.
- List : 객체를 일렬로 관리하는 자료구조로 인덱스로 관리한다.
1. ArrayList : 원소를 배열로 관리하는 리스트, 미리 메모리 공간을 할당하고 참고하려는 객체의 주소를 관리한다.  
(단점) 리스트가 꽉 차서 리사이징을 위해서는 더 큰 공간에 데이터를 일일이 옮겨야하므로 O(N)의 시간복잡도를 가져서 데이터가 많을수록 리사이징에 불리하다.

2. LinkedList : 다음 객체의 주소 정보를 저장하는 식으로 연결되어 있는 리스트이다.

3. Vector : 배열을 통해서 값을 저장하지만 ArrayList와는 다르게 A 스레드의 작업이 끝날 때 까지 B 스레드가 대기하는 식으로 스레드를 동기화하여 멀티스레드 환경에서 Thread-safe가 보장된다.  
(단점) 스레드 동기화로 속도가 상대적으로 떨어진다.

- Set : 여러 객체를 저장하지만 중복 저장을 할 수 없다.
1. HashSet : 데이터를 숫자로 변환하는 것을 Hash라 하며, HashSet은 hashcode() 메소드를 통해 Hash값을 가져오고 비교하고 중복을 확인한다. Hash 값이 같을 경우 equals() 메소드로 다시한번 비교하여 같으면 저장하지 않는다.
2. TreeSet : compareTo()로 데이터를 비교하여 이중 구조로 저장한다. 삽입/삭제 시 트리 구조를 재배열하여 속도가 느리지만, 검색은 트리 높이만큼 하여 속도가 빠르다. Comparable 인터페이스를 구현한 객체에 대해서만 TreeSet을 사용할 수 있다.
3. LinkedHashSet : 클래스 내부의 LinkedList로 입력 순서까지 저장한다.

- Map : 컬렉션과는 다른 구조로 되어 있다. 키를 통해서 벨류를 저장한다.
1. HashMap : Hash코드를 사용해서 키를 저장하고 벨류를 저장한다. 조회에서 유리하다.
2. HashTableMap : HashMap과 비교하여 Thread-safe가 보장된다.
3. LinkedHashMap : 클래스 내부의 LinkedList로 입력 순서까지 저장한다. 
4. TreeMap : 이진 트리를 기반으로 하여, 트리에 키를 저장한다.

## 생성자 Constructor
- 클래스명과 동일한 이름을 가진 메소드
- 리턴 타입을 정의하지 않는다. (void도 안쓴다!)
- 객체가 생성될 때 자동으로 호출
- new 키워드가 사용될 때 호출
- 만약, 생성자를 구현하지 않으면 컴파일러가 기본 생성자(디폴트 생성자)를 추가한다.
- 메소드를 오버로딩하는 것처럼 생성자도 오버로딩 할 수 있다.

# 람다 함수
- 자바 8부터 사용
- 익명 함수를 지칭하는 용어
- 함수를 보다 단순하게 표현

## 람다의 특징
- 이름이 없는 익명 함수
- 파라미터가 있는 함수는 괄호 안에 지정하여 사용

## 람다식의 장점
- 코드의 라인수가 줄어든다. (불필요한 코드를 제거)
- 병렬 프로그래밍이 가능하다.
- 람다식으로 실행문을 바로 전달할 수 있다.
- 가독성이 높아진다.

## 람다식의 단점
- 재사용이 불가능하다. (일회용 함수 정의가 목적)
- 불필요하게 남발하면 가독성이 떨어진다. (같은 기능의 함수를 여러번 정의하는 상황이 발생할수도)

## 람다식의 표현
- 화살표를 사용한다
- Ex) (매개변수) -> {함수 구현부} 또는 () -> {함수 구현}
- 작성할 실행문이 한줄이면 괄호를 생략 가능하다.
- 하지만 리턴문이라면 생략할 수 없다.

# System.out.println()은 무엇인가?
- JAVA에서 콘솔창에 변수나 문자열을 출력하는 명령어
- public static final void printstream out; 을 가르키는 코드이다.
- 시스템 클래스가 초기화되면서 이 정적변수에 객체가 대입된다.
- 대입되기 전까지의 out은 참조타입만 가진 NULL이며, 이것은 하나의 static 객체로 재정의 된다.
- 즉, printstream의 객체를 정적변수 out에 넣어서 static 객체로 만든 것이다.
- 그래서 System.out이 가능하게 되고 이것은 클래스처럼 보이지만 이 자체로 하나의 객체라고도 볼 수 있다.
- 요약하자면 System.out은 간접 참조와 같고 다른 언어에서 import나 메소드를 찾아가는 과정과 매우 비슷하다.

# 자바 ArrayList와 비교한 Array의 장점
데이터의 크기를 미리 정해야하고 추가 및 삭제가 필요치 않을 경우 ArrayList보다는 Array가 유리하다.
- 문법적으로 ArrayList보다 Array가 구현하기가 쉽다.
- Array를 생성 시 메모리가 미리 할당되어 연속된 메모리 공간에 위치하므로 메모리 관리가 용이하다.
- 메모리 공간에 위와 같은 장점이 있어서 데이터를 읽는 속도가 빠르다.