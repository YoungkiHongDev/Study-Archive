/* 캐릭터 */
//캐릭터 변수가 숫자인지 확인
Chracter.isDigit(value);

//캐릭터 변수인 숫자를 정수형으로 변환
int num = Character.getNumericValue(value);


/* 문자열 */
//입력문
BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
String s = br.readLine();
int n = Integer.parseInt(br.readLine());

//출력문
System.out.println();

//토크나이저 생성
StringTokenizer st = new StringTokenizer(br.readLine(), " ");

//토크나이저 토큰 개수
st.countTokens();

//토크나이저 토큰 하나씩 꺼내기
st.nextToken();

//문자열 치환
String str = "Hello";
str = str.replace("Hello", "World"); //World

//문자열 포함여부 확인
String str = "Hello";
str.contains("Hello"); //true

//빈 문자열 체크
String str = "";
str.isEmpty(); //true

//문자열 뒤집기
String str = "ASDF"
String reversStr = new StringBuffer(str).reverse().toString(); //FDSA

//문자열 정규표현식 활용
str.replaceAll("[^0-9]", "") //숫자를 제외한 문자들 제거
str.replaceAll("[^a-zA-Z]", "") //영문자를 제외한 문자들 제거

//문자열 배열처럼 쓰기 (캐릭터로 한글자씩)
String s = "Hello";
s.toCharArray();


/* 배열 */
//배열 오름차순 정렬
Arrays.sort(arr);

//배열 내림차순 정렬
Arrays.sort(arr, reverseOrder());

//배열 한번에 초기화
Arrays.fill(arr, "defaultValue");

//배열 문자열로 만들기
Arrays.toString(arr);

//배열 문자열로 만들면서 사이사이에 문자삽입
String[] str = {"A", "B", "C"};
String result = String.join("@", str); //A@B@C

//N*N 2차원 배열에 값넣기
for (int i=0; i<n; i++) {
    StringTokenizer st = new StringTokenizer(br.readLine(), " ");
    for (int j=0; j<n; j++) {
        doll[i][j] = Integer.parseInt(st.nextToken());
    }
}

//배열 중복값 개수 세기
Collections.frequency(Arrays.asList(arr), "value");

//배열의 값 전부를 괄호와 쉼표 빼고 숫자와 공백만 출력하기
Arrays.toString(arr).replaceAll("[\\[\\],]", "") //[1, 2, 3, 4, 5] -> 1 2 3 4 5


/* 리스트 */
//어레이리스트 생성
ArrayList<Integer> list = new ArrayList<>();

//리스트 2개를 비교하고 arr1에 arr2와 중복인 값만 남기기
arr1.retainAll(arr2);

//리스트 오름차순 정렬
Collections.sort(list);

//리스트 문자열로 변환
list.toString();

//리스트 중복값 개수 세기
Collections.frequency(list, "value");


/* 해시맵 */
//해시맵 생성
HashMap<Character, Integer> map = new HashMap<>();

//해시맵 입력
map.put(key, value);

//해시맵 벨류값 얻기
map.get(key);


/* 트리셋 */
//트리셋 생성
TreeSet<Integer> tset = new TreeSet<>();

//트리셋 내림차순으로 저장하도록 생성
TreeSet<Integer> tset = new TreeSet<>(Collections.reverseOrder());


/* 스택 */
//스택 생성
Stack<Integer> stack = new Stack<>();

//스택 삽입
stack.push(value);

//스택 꺼내기
stack.pop();

//스택 마지막 값 확인
stack.peek();

//스택 안에 값이 들어있나 확인
stack.contains(value);


/* 기타등등 */
//최대 최소 값 구하기
Math.max(a, b) //2개 중 높은 값
Math.min(a, b) //2개 중 낮은 값
Math.max(Math.max(a, b), c) //3개 중 높은 값
Math.max(Math.max(a, b), Math.max(c, d)) //4개 중 높은 값

//2차원 배열 헷갈릴때 보기
00	01	02	03	04
10	11	12	13	14
20	21	22	23	24
30	31	32	33	34
40	41	42	43	44