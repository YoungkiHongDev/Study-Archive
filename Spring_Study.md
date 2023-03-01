# Spring이란?
- 자바 엔터프라이즈 개발을 위한 오픈소스 경량 어플리케이션 프레임워크
- 프레임워크가 인프라 스트럭처를 제공하므로 개발자는 업무로직 개발에만 전념가능
- 스프링 프레임워크는 공통 프로그래밍 모델 및 Configuration 모델을 제공

# STS
- 이클립스 기반의 스프링 도구
- CTRL + SHIFT + O : import 단축키
- 로컬서버 실행방법  
1. 왼쪽 상단메뉴  
2. 녹색 육각형 전원버튼(Boot Dashboard)  
3. 왼쪽 하단에 Boot Dashboard에서 local 클릭  
4. local 아래의 프로젝트명 클릭  
5. Boot Dashboard 아래의 활성화된 서버 실행 버튼 클릭

# Spring Boot Devtools
- 클래스를 변경하면 서버가 자동으로 재기동하는 툴로 스프링부트 개발시 도움을 주는 도구
- Spring Boot Devtools 설치방법  
1. build.gradle 우클릭  
2. dependencies에 developmentOnly 'org.springframework.boot:spring-boot-devtools' 추가  
3. build.gradle 우클릭 후 Gradle - Refresh Gradle Project 클릭해서 라이브러리 설치  
4. 서버 실행 버튼 클릭 후 클래스 변경시 새로고침하면 변경사항이 적용되는지 확인하기

# Live Reload++
- 크롬 확장프로그램으로 설치, 브라우저를 새로고침할 필요 없이 변경 사항을 확인할 수 있게 해주는 도구
- https://chrome.google.com/webstore/detail/livereload%20%20/ciehpookapcdlakedibajeccomagbfab

# Lombok
- 자바 클래스에 Getter, Setter, 생성자 등을 자동으로 만들어주는 도구
- https://projectlombok.org/download
- 롬복 설치방법  
1. 다운로드한 곳에서 터미널 열고 java -jar lombok.jar 입력  
2. STS 설치경로를 선택하고 설치 후 종료  
3. STS를 다시 실행하고 build.gradle  
4. dependencies에 compileOnly 'org.projectlombok:lombok' 추가  
5. dependencies에 annotationProcessor 'org.projectlombok:lombok' 추가  
6. build.gradle 우클릭 - Gradle - Refresh Gradle Project 클릭해서 라이브러리 설치
- compileOnly : 해당 라이브러리가 컴파일 단게에서만 필요한 경우에 사용
- annotationProcessor : 컴파일 단계에서 어노테이션을 분석하고 처리하기 위해 사용

# 어노테이션
- @Controller : 이 클래스가 컨트롤러 기능을 수행한다는 의미, 스프링부트 프레임워크가 컨트롤러로 인식
- @RequestMapping("/hello") : "/hello" URL 요청이 발생하면 이 메소드가 실행됨을 의미, 즉 URL과 메소드를 매핑하는 역할
- @ResponseBody : 메소드의 응답 결과가 문자열 그 자체임을 의미

# Lombok 어노테이션
- @Getter : private 변수에 접근하기 위해서 사용, 변수값을 가져올 수 있다.
- @Setter : private 변수에 접근하기 위해서 사용, 변수값을 세팅할 수 있다.
- @RequiredArgsConstructor : 해당 속성을 필요로하는 생성자가 롬복에 의해 자동으로 생성 (final이 없는 속성은 생성자에 포함되지 않는다.), final을 쓰므로 Setter를 못쓰게 만듬, 의존성 주입(DI)시 사용된다.

# Servlet
Servlet은 자바 언어를 기반으로 웹 어플리케이션을 만들 때 사용하는 자바 클래스다.  
Servlet은 웹 서버에서 실행되며, HTTP 요청에 대한 응답을 생성한다.  
대부분의 웹 프레임워크는 내부적으로 Servlet을 기반으로 동작하며, 이를 활용하여 다양한 기능을 구현할 수 있다.

예를 들면 다음과 같은 기능을 구현할 수 있다.
1. 양식 데이터를 처리하여 이메일 전송할 수 있다.
2. 동적 웹 컨텐츠를 생성하기 위해 데이터베이스에서 데이터를 검색하고 웹 페이지에 표시할 수 있다.
3. 세션 관리를 위해 사용자가 로그인하면 새로운 세션을 생성하고, 로그아웃하면 세션을 처리할 수 있다.

## Servlet 기능
1. HTTP 요청 처리: 클라이언트로부터 HTTP 요청을 받아들이고, 이에 대한 응답을 생성한다.
2. 데이터 처리: 요청된 데이터를 처리하고, 데이터베이스의 데이터를 검색한다.
3. 비즈니스 로직 처리: 요청된 데이터를 기반으로 비즈니스 로직을 실행하고, 결과를 생성한다.
4. 동적인 웹 페이지 생성: Servlet은 HTML, XML, JSON과 같은 동적인 컨텐츠를 생성하여 클라이언트에게 제공한다.

## Servlet과 Spring의 차이점
Servlet은 HTTP 요청과 응답을 처리하기 위해 기본적인 API를 제공한다. 하지만 개발자가 스레드를 관리하고 요청을 응답처리하고 세션을 관리하는 등 세부 사항들을 직접 처리해야 한다는 불편함이 있다.  

Spring은 웹 어플리케이션을 구축하기 위한 다양한 기능을 제공하는 프레임워크이다. 개발에 필요한 작업들을 처리하기 위한 클래스들을 제공해서 개발자의 시간과 노력을 절약할 수 있어서 보다 효율적이고 생산적이다.