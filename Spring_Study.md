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