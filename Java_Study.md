# C언어와 JAVA의 차이점
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

# JAVA 버전
- 8버전부터 LTS / Non-LTS 버전으로 나뉘어 릴리즈
- LTS : 8년 동안 업데이트를 지원하는 버전
- Non-LTS : 새로운 버전이 출시되면 더이상 업데이트를 지원하지 않는 버전

# JAVA 주요 특징
- 객체지향 언어
- 멀티스레드 지원
- OS 플랫폼 독립성 : C언어의 경우 동일한 프로그램을 OS에 따라 달리 제작하지만 JAVA는 JVM 위에서 동작하므로 JVM을 OS에 맞게 설치해야 한다.
- 가비지 컬렉션 : 메모리에 인스턴스 객체를 만들면 사용 후 자동으로 해제한다.

# JAVA 동작 방식
**1. 에디터**  
소스코드 Hello.java 작성  

**2. 컴파일러**  
Hello.java를 컴파일하여 Hello.class 산출  

**3. 클래스로더**  
사용된 클래스들을 로딩해서 Hello.class 파일에 클래스들을 합침  

**4. 바이트코드 검증기**  
Hello.class 파일의 바이트코드를 검증

**5. 인터프리터**  
검증된 Hello.class를 한줄씩 번역

# JDK
- 자바 개발 도구
- 자바가 동작할 수 있는 실행환경
- 자바 프로그램을 개발하는 데 필요한 도구 Ex) 컴파일러

# JVM
- 자바 가상 머신
- 바이트 코드 파일로 구성되는 자바 프로그램
- JVM이 운영체제에 맞춰 해석
- 다양한 운영체제에서 사용 가능

# JAVA 설치 과정
- https://www.oracle.com/java/technologies/downloads/
- java -version //자바 버전 확인 명령어로 설치유무 확인
- 최근에는 자바 설치 시 자바 환경 변수가 자동 등록됨

# 자바 환경 변수
- JDK 안에는 java.exe 런처 파일, javac.exe 컴파일러 파일 등의 도구가 있음
- 도구를 어느 폴더에서도 실행 할 수 있도록 자바 환경 변수를 등록이 필요했지만 최근에는 자동으로 등록
- 그러나 버전을 변경하려면 환경 변수를 수동으로 등록하여 원하는 버전의 JDK를 지정

# JAVA 버전 변경
- 새로운 버전의 JDK를 설치
- 시스템 변수 Path에 자동 등록되어 있는 자바 환경 변수 삭제
- 시스템 변수 Path에 원하는 JDK의 bin 폴더 경로 등록
- java -version으로 버전 확인

# JAVA 개발 툴
통합 개발 환경 IDE
- 인텔리제이
- 이클립스

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

# OOP의 4가지 특징
**1. 캡슐화**
- 유사한 속성과 메소드를 하나의 클래스로 모은것
- 로직이나 변수를 감추고 API만 외부에 제공하는 정보 은닉이 가능

**2. 상속**
- 자식 클래스가 상속을 받아 부모 클래스의 멤버 변수나 메소드를 사용 가능
- 클래스의 재사용이 용이함

**3. 추상화**
- 클래스들의 공통적인 메소드들을 인터페이스로 정의하는 것

**4. 다형성**
- 같은 이름의 메소드가 상황에 따라 다르게 동작하는 것
- 오버로딩, 오버라이딩이 있음

**오버로딩**
- 클래스 내에서 메소드의 이름은 같지만 매개변수의 개수나 타입을 달리해서 사용하는 것
- 메소드 네이밍의 고민을 덜어줌

**오버라이딩**
- 부모 클래스의 메소드를 자식 클래스에서 용도에 맞게 재정의하는 것
- 오버로딩과 다르게 매개변수가 동일해야함
- 부모 클래스의 메소드와 같거나 넓은 범위의 접근 제어자만 사용 가능

# 자료형
## 배열 Array
- 자료형의 집합을 의미
- 배열의 길이는 고정
- 배열의 길이를 생성 시 값을 넣으면서 생성
- 또는 배열의 길이를 생성 시 지정하고 값을 삽입 

**숫자형 배열**     
int[] odds = {1, 3, 5, 7, 8};

**문자형 배열**     
String[] weeks = {"월", "화", "수", "목", "금", "토", "일"};

**문자형 배열 다른 방식**   
String[] weeks = new String[7];     
weeks[0] = "월";    
weeks[1] = "화";    
weeks[2] = "수";    
weeks[3] = "목";    
weeks[4] = "금";    
weeks[5] = "토";    
weeks[6] = "일";    

**배열을 for문과 같이 사용**
- Array.length를 따로 변수에 저장해서 쓰는 이유는 바로 안정성
- 반복문 안에서 길이가 변경되면 문제가 발생할 수도 있다!

String[] weeks = {"월", "화", "수", "목", "금", "토", "일"};    
String len = weeks.length;  
for (int i=0; i<len; i++) {     
&emsp; System.out.println(weeks[i]);   
}

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

**제네릭스**
- 버전5 이후부터 사용 권고
- 어떤 객체를 포함하는지 명확하게 표현
- 인텔리제이에서 제네릭스를 아쓰면 warning이 표시됨

ArrayList<String> pitches = new ArrayList<String>();    
ArrayList<String> pitches = new ArrayList<>();

- 뒷 부분의 자료형은 생략이 가능하므로 2번째 방식을 선호
- 인텔리제이에서는 생략안하면 경고

**aList 메소드**    
- 이미 존재하는 배열    
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

- String.join("구분자", 리스트객체) 사용하여 원소를 문자열로 합치기     
String result = String.join(",", pitches);


**리스트 정렬**
- sort 메소드는 자바8 버전부터 사용 가능
- Comparator 클래스 불러오기    
import java.util.Comparator;

- 오름차순 정렬     
pitches.sort(Comparator.naturalOrder());

- 내림차순 정렬     
pitches.sort(Comparator.reverseOrder());