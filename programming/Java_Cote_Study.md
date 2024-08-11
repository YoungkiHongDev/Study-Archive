# Character
```java
// Character 변수가 숫자인지 확인
Character.isDigit(value);

// Character 변수를 정수형으로 변환
int num = Character.getNumericValue(value);
```


# String
```java
// 입력
BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
String s = br.readLine();
int n = Integer.parseInt(br.readLine());

// 출력
System.out.println();

// StringTokenizer 생성 및 사용
StringTokenizer st = new StringTokenizer(br.readLine(), " ");
st.countTokens();  // 토큰 개수 확인
st.nextToken();    // 토큰 하나씩 꺼내기

// 문자열 치환
String str = "Hello";
str = str.replace("Hello", "World");  // "World"

// 문자열 포함 여부 확인
str.contains("Hello");  // true

// 빈 문자열 체크
str.isEmpty();  // true

// 문자열 뒤집기
String reversedStr = new StringBuffer(str).reverse().toString();  // "FDSA"

// 정규표현식을 활용한 문자열 처리
str.replaceAll("[^0-9]", "");       // 숫자 제외한 문자 제거
str.replaceAll("[^a-zA-Z]", "");    // 영문자 제외한 문자 제거

// 문자열을 배열처럼 사용하기
char[] chars = s.toCharArray();
```


# Array
```java
// 배열 정렬
Arrays.sort(arr);                          // 오름차순 정렬
Arrays.sort(arr, Collections.reverseOrder());  // 내림차순 정렬

// 배열 초기화
Arrays.fill(arr, "defaultValue");

// 배열을 문자열로 변환
String arrayStr = Arrays.toString(arr);

// 배열 요소 사이에 문자 삽입하여 문자열 생성
String[] strArr = {"A", "B", "C"};
String result = String.join("@", strArr);  // "A@B@C"

// N*N 2차원 배열 초기화
for (int i = 0; i < n; i++) {
    StringTokenizer st = new StringTokenizer(br.readLine(), " ");
    for (int j = 0; j < n; j++) {
        doll[i][j] = Integer.parseInt(st.nextToken());
    }
}

// 배열 내 중복값 개수 세기
Collections.frequency(Arrays.asList(arr), "value");

// 배열의 값들을 특정 형식으로 출력
String formatted = Arrays.toString(arr).replaceAll("[\\[\\],]", "");  // "1 2 3 4 5"
```


# List
```java
// ArrayList 생성
ArrayList<Integer> list = new ArrayList<>();

// 리스트 간 중복 요소만 남기기
list1.retainAll(list2);

// 리스트 정렬
Collections.sort(list);  // 오름차순 정렬

// 리스트를 문자열로 변환
String listStr = list.toString();

// 리스트 내 중복값 개수 세기
Collections.frequency(list, "value");
```


# HashMap
```java
// HashMap 생성
HashMap<Character, Integer> map = new HashMap<>();

// HashMap에 데이터 입력
map.put(key, value);

// HashMap에서 값 얻기
int value = map.get(key);
```


# TreeSet
```java
// TreeSet 생성
TreeSet<Integer> tset = new TreeSet<>();

// TreeSet 내림차순 정렬
TreeSet<Integer> tset = new TreeSet<>(Collections.reverseOrder());
```


# Stack
```java
// Stack 생성
Stack<Integer> stack = new Stack<>();

// Stack에 값 삽입
stack.push(value);

// Stack에서 값 꺼내기
int topValue = stack.pop();

// Stack의 마지막 값 확인
int lastValue = stack.peek();

// Stack에 특정 값이 있는지 확인
boolean contains = stack.contains(value);
```


# etc.
```java
// 최대, 최소 값 구하기
Math.max(a, b);                             // 둘 중 높은 값
Math.min(a, b);                             // 둘 중 낮은 값
Math.max(Math.max(a, b), c);                // 셋 중 높은 값
Math.max(Math.max(a, b), Math.max(c, d));   // 넷 중 높은 값
```
