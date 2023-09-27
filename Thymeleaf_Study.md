# Thymeleaf란?
Java 진영에서 사용하는 서버 사이드 템플릿 엔진으로 Java와 유사한 문법을 사용하여 HTML 템플릿을 동적으로 생성할 수 있게 한다.

# namespace 선언
```html
<html lang="ko" xmlns:th="http://www.thymeleaf.org">
```
Thymeleaf 네임스페이스를 정의하는 선언이다. HTML에서 네임스페이스를 선언하여 Thymeleaf 템플릿 엔진을 HTML 문서에 가져와 사용한다. 네임스페이스 선언으로 HTML 문서는 특정 라이브러리나 프레임워크의 기능을 활용할 수 있다.

# ${변수}
Thymeleaf의 표현식으로 변수를 템플릿에 삽입하는 역할을 한다. 변수는 서버에서 클라이언트로 전달되거나 템플릿 엔진에서 생성된 데이터이다. 

# th:text
```html
<h1 th:text="${변수}">변수출력</h1>
```
th:text는 Thymeleaf에서 사용되는 속성으로 HTML 요소의 텍스트 내용을 동적으로 설정할 수 있다. 서버 측 데이터나 변수의 값을 HTML 페이지에 출력한다.

```java
// MyController.class
@Controller
public class MyController {
    
    @GetMapping("/example")
    public String example(Model model) {
        //message 변수에 getMassage() 메소드 할당
        model.addAttribute("message", getMassage());
        return "example_template";
    }

    public String getMessage() {
        return "Welcome, Thymeleaf!";
    }
}
```

```html
<!-- example_template.html -->
<!DOCTYPE html>
<html>
<head>
    <title>Example</title>
</head>
<body>
    <!-- 메소드를 호출하여 반환값 출력 -->
    <h1 th:text="${message}">메시지 출력</h1>
</body>
</html>
```
위의 예제처럼 변수가 아닌 메소드를 호출할 수도 있다.

# th:block
```html
<th:block>
    <!-- block으로 감쌀 HTML 태그 -->
</th:block>
```
Thymeleaf에서 HTML 요소를 감싸는 데 사용한다. 주로 조건문이나 반복문과 함께 사용하여 특정 조건에 따라 동적으로 HTML을 생성한다.

# th:if
```html
<!-- 변수가 true인 경우 요소 출력 -->
<span th:if="${isClear}">목표달성!</span>

<!-- 변수가 18보다 큰 경우 요소 출력 -->
<span th:if="${age > 18}">성인</span>
```
조건문을 나타내는 속성으로 주어진 조건이 참일 경우 HTML 요소를 생성하거나 화면에 표시한다. 조건이 거짓이라면 HTML 요소가 생성되지 않거나 화면에서 안보이게 한다.

# th:each
```html
<ul>
    <!-- 리스트의 각 요소를 순회하면서 출력 작업 반복 수행 -->
    <li th:each="item : ${itemList}" th:text="${item}">아이템</li>
</ul>
```
반복문을 나타내는 속성으로 주어진 컬렉션(리스트, 배열 등)을 순회하면서 HTML 요소를 생성한다. Java의 for-each문과 같이 각 요소를 순회하며 반복 작업을 수행한다.

# th:replace
```html
<!-- layout.html 템플릿을 현재 페이지에 적용 -->
<!-- layout.html의 main 프래그먼트를 현재 페이지로 대체 -->
<div th:replace="layout :: main"></div>
```
Thymeleaf 템플릿 엔진에서 사용되는 속성으로 템플릿 내에서 다른 템플릿이나 프래그먼트를 대체할 때 사용된다. 웹 페이지의 일부분을 동적으로 교체할 수 있다.