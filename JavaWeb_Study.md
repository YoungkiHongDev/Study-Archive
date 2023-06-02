﻿
> 자바 웹 개발 워크북
> http://www.yes24.com/Product/Goods/111136639

## 프로젝트 설정

**기본 도구**
- JDK 11
- Tomcat 9
- Gradle
- Java EE 8

**톰캣 한글 처리**
Help 메뉴 -> Edit Custom VM Options
Xmx는 인텔리제이가 사용할 최대 메모리를 의미
한글 처리를 위해 아래 2줄 추가 후 인텔리제이 재시작
```
-Dfile.encoding=UTF-8
-Dconsole.encoding=UTF-8
```

**프로젝트 경로 설정**
실행 버튼 옆 Tomcat
-> Edit Configurations
-> Deployment
-> .war를 '-' 눌러 제거
-> '+' 눌러 Artifact
-> (exploded) 선택
-> Application context 값 '/' 로 설정

**톰캣 재시작 최소화**
실행 버튼 옆 Tomcat
-> Edit Configurations
-> Server에서 다음과 같이 설정
```
VM options: -Dfile.encoding=UTF-8
On 'Update' action: Update classes and resources
On frame deactivation: Update classes and resources
```
이제 페이지를 새로고침하면 HTML, JSP 변경사항은 바로 반영
하지만 자바 코드는 하단의 Services의 Deploy All 클릭 후 새로고침하여 반영

## 웹의 동작
**GET 방식** : 주소창에 직접 원하는 데이터를 적거나 링크를 클릭하여 호출하는 방식

**POST  방식** : 입력 화면에서 필요한 내용을 작성 후 버튼을 클릭하여 호출하는 방식

**Request** : 브라우저가 서버에 데이터를 요청하는 것

**Response** : 서버가 브라우저의 요청에 대한 응답 데이터를 보내주는 것

**정적 데이터 static** : 고정된 데이터로 주로 HTML, CSS, 이미지 파일 등이 있다.

**동적 데이터 dynamic** : 매번 필요할 때마다 다른 데이터를 동적으로 구성하는 것으로 서버에서 데이터를 만들어 보내는 방식이라 서버 사이드 프로그래밍이라고도 한다.

**웹 서버** : 정적 데이터를 보내는 역할만 수행하는 서버

**웹 애플리케이션 서버 WAS** : 동적 데이터를 만들어 보내는 서버

> 톰캣의 경우 WAS지만 웹 서버 기능도 같이 포함되어 정적/동적 자원 모두 처리 가능

**프로토콜** : 브라우저의 요청과 서버의 응답으로 처리되는 데이터를 교환하기 위한 약속

**HTTP**: 웹에서 사용되는 프로토콜로 URL이 HTTP로 시작하면 HTTP 프로토콜로 데이터를 주고 받는 것을 의미한다.

**HTTPS** : HTTP에서 보안이 강화된 프로토콜이다.

**비연결성** : HTTP에서 최대한 많은 사용자에게 서비스를 제공하기 위한 방식으로 하나의 요청과 응답을 처리한 후 연결을 종료한다는 것을 의미한다. 새로고침을 하여 새로 요청과 응답을 받는 이유가 이것이며, 서버는 적은 리소스를 이용해서 많은 수의 요청을 처리할 수 있는 장점을 가진다.

## 자바 서버 사이드 프로그래밍
 서버를 개발할 때는 여러 요청, 문제 발생, 데이터 전송 최적화, 분산 환경, 분산 처리 등등 다양한 고민이 필요하다. 하지만 매번 개발할 때마다 그러면 소모되는 시간과 비용이 엄청나다.

이런 고민을 덜어주기 위해서 자바에서는 **JavaEE**라는 기술을 정리했다.
Servlet과 JSP도 JavaEE의 여러 기술 중 하나이다.

## 서블릿과 JSP
**서블릿**은 JavaEE에서 가장 기본적인 기술이다. 서버에서 동적으로 요청과 응답을 처리할 수 있는 API들을 정의한 것이라고 할 수 있다.

톰캣과 같이 서블릿을 실행 할 수 있는 환경을 **서블릿 컨테이너**라고 한다.

서블릿의 라이프 사이클 -> init(), doGet(), destroy()

**JSP**는 Java Server Pages의 약자로 서블릿과 동일하게 서버에서 동적으로 데이터를 구성한다. 자바 코드를 이용하여 HTML 문자열을 만드는 서블릿과는 달리 JSP는 HTML을 이용하여 자바 코드를 넣는다.

하지만 HTML 코드를 이용하는 JSP가 화면 개발이 더 쉬워서 화면 개발은 JSP, 데이터 처리는 서블릿으로 분담하여 개발한다.

또한 JSP는 서블릿 코드로 변환되어서 컴파일되고 실행되므로 서블릿과 동일하게 처리된다.

> **서블릿/JSP 요점정리**
> - 서블릿/JSP 모두 Java EE 스펙의 일부이다.
> - 서블릿/JSP 실행을 위해서는 톰캣과 같은 서블릿 컨테이너가 필요하다.
> - 서블릿 컨테이너는 서블릿/JSP 객체를 생성하고 생명주기를 관리한다.
> - JSP는 내부적으로 서블릿과 같은 방식으로 처리된다.
> - JSP는 HTML 코드 내에 자바 코드를 추가하는 방식
> - 서블릿은 자바 코드 안에 HTML 코드를 추가하는 방식

**JSP의 문제점**
JSP에 POST 방식으로 form 데이터를 전달하여 이것을 처리하여 결과로 보여줄 페이지를 
GET 방식으로 호출할 수 있다는 문제점이 있다.

유지 보수를 하면서 이 페이지를 다른 JSP로 교체할 경우 이 주소를 아는 사용자들에게 혼란을 줄 수 있다.

그래서 최근에는 JSP는 다음과 같이 제한한다.
1. JSP에서 쿼리스트링, 파라미터 처리 X -> 서블릿을 통해서 처리하자!
2. JSP는 입력 화면, 처리 결과를 보여주는 용도로만 사용
3. 브라우저에서 직접 JSP를 호출하지 않고 서블릿을 통해서 JSP를 보여주기

> 이 문제를 해결하기 위해서 웹 MVC 방식이 등장했다.
> 서블릿은 처리만 하고, JSP는 결과만 출력하는 방식이다.

## 서블릿 문법
**어노테이션**
@WebServlet -> 브라우저의 경로와 해당 서블릿을 연결하는 설정

**메소드**
doGet() -> 브라우저의 주소를 직접 변경해서 접근하는 경우 호출하는 메소드

**출력**
서블릿에서는 PrintWriter 객체로 브라우저에 출력 처리
```
PrintWriter out = resp.getWriter();  
out.println("<html><body>");  
out.println("<h1>MyServlet</h1>");  
out.println("</body></html>");
```

## JSP 문법
**출력**
다음과 같이 EL 이라는 기술로 form 데이터로 넘겨준 데이터를 출력할 수 있으며, EL은 param 객체를 이용해서 요청으로 전달된 파라미터를 추출한다.

전달 되는 모든 데이터는 문자열로 처리되므로 JSP로 복잡한 처리하기는 적합하지 않다.

```jsp
<h1>NUM1 ${param.num1}</h1>  
<h1>NUM2 ${param.num2}</h1>
<h1>SUM ${Integer.parseInt(param.num1) + Integer.parseInt(param.num2)}</h1>
```

# PRG 패턴
웹 MVC 구조에서 자주 사용되는 패턴으로 POST 방식과 Redirect를 결합한 패턴이다.  
PRG 패턴의 대표적인 예시로는 게시판이 있다.  
반복적인 POST 호출을 방지할 수 있는 장점이 있다.

1. 브라우저에서 POST 방식으로 데이터의 처리를 요청한다.
2. Controller에서 데이터를 처리하고 브라우저에 Redirect할 주소를 응답한다.
3. 브라우저는 이동할 주소를 받아서 GET 방식으로 서버를 호출한다.
4. Controller는 GET 방식의 데이터를 처리 후 브라우저에 응답 메시지를 전송한다.

# HttpServlet
Servlet을 작성할 때 HTTP 프로토콜에 특화된 기능을 처리하기 위해 상속받는 클래스이다.  

## HttpServlet 라이프 사이클
1. 브라우저가 톰캣에 서블릿이 처리할 경로를 호출한다.
2. 톰캣은 경로에 맞는 서블릿 클래스를 로딩하고 객체를 생성한다. 이 때, init() 메소드가 실행된다.
3. 생성된 서블릿 객체가 요청 정보를 분석하여 파라미터를 HttpServletRequest 타입으로 전달받으며, 응답 처리에 필요한 정보는 HttpServletResponse 타입 객체로 전달받는다.
4. 서블릿 내부에서 GET/POST 방식에 따라 doGet()/doPost() 메소드를 호출하며, 동일한 호출이 있을 경우 동일한 객체를 다시 호출하여 처리한다.
5. 톰캣이 종료되면 destroy() 메소드를 호출한다.

## HttpServletRequest 메소드
- getParameter(): 쿼리 스트링에서 키를 이용하여 값을 얻는 메소드로 항상 결과가 String이라 null에 주의해야 한다.
- getParameterValues(): 파라미터가 여러개 있는 경우에 사용하며, String[] 타입으로 반환된다.
- setAttribute(): JSP로 전달할 데이터를 추가한다. 키(문자열)와 값(모든 타입)의 형태로 저장할 수 있다.
- getRequestDispatcher(): RequestDispatcher 타입의 객체를 구할 수 있으며, 현재 요청을 다른 서블릿이나 JSP에게 전달한다.
- forward(): RequestDispatcher의 메소드로 현재까지의 모든 응답은 무시하고 JSP가 작성하는 내용만 브라우저로 전달한다.
- include(): RequestDispatcher의 메소드로 지금까지의 응답 내용과 JSP가 만든 내용을 브라우저로 전달한다. 실제 개발에서는 include 보다는 forward를 주로 사용한다.

## HttpServletResponse 메소드
- sendRedirect(): 브라우저에게 다른 주소로 가라는 응답 메시지를 전달한다. Location이라는 HTTP 헤더로 전달된다.