> 스프링과 JPA를 이용한 웹개발 - 금오공과대학교 김성렬 교수
> http://www.kocw.net/home/cview.do?cid=5e6aec4a9ae2dd45

**강의목표: JPA, 타임리프, 스프링부트 학습**

# ORM
ORM은 객체 관계 매핑을 뜻한다. ORM 역할은 자바 클래스와 데이터베이스 테이블 매핑한다. node.js에서는 ODM이라고도 한다.

# JPA
자바 진영의 ORM 표준이다. 자바 애플리케이션에서 관계형 데이터베이스를 사용하는 방식을 정의한 인터페이스이다. JPA 인터페이스를 구현하는 방식에는 여러가지가 있다. Hibernate, EclipseLink, DataNucleus 등등이 있지만 Hibernate를 많이 사용한다.

예전에는 JDBC를 이용해 자바 애플리케이션과 DB가 데이터를 주고 받았다. 그리고 DB마다 다른 JDBC 드라이버를 사용하여 SQLite, MySQL, Oracle 등 데이터베이스에 맞춰서 드라이버를 설치하여 사용했다. JPA 또한 JDBC를 사용하는데 JDBC와 각 데이터베이스의 드라이버가 내장되어 있어서 사용하는 데이터베이스에 맞춰 사용할 수 있다.

JPA의 1번째 장점으로 CRUD를 자동 생성하고 실행해 주는 것이 있다. 저장, 조회, 수정, 삭제 시 SQL문을 작성할 필요가 없다.

JPA의 2번째 장점으로 SQL 방언이 있다. DB에 따라 사용하는 SQL이 다르다. 예를 들면 MySQL이면 Limit을 쓰고, Oracle에서는 rownum을 쓴다. 하지만 JPA를 쓰면 DB를 변경해도 SQL을 바꿀 필요가 없이 JPA 설정만 변경하면 DB에 맞는 SQL이 생성된다. 이것은 JPA에서 제공하는 Dialect라는 추상화된 방언 클래스와 구현체를 제공해서 그렇다.

JPA의 3번째 장점으로 Auto DDL 기능이 있다. 기존에 테이블을 생성하고 객체를 정의하던 것과는 달리 Auto DDL을 사용하면 객체를 정의하고 테이블을 자동 생성한다. 그러면 테이블을 갈아엎을 필요 없이 테이블을 유지하면서 변경사항만 적용시킬 수 있어서 편리하다.

JPA의 4번째 장점으로 SQL을 모아서 한번에 보내서 성능 상 이점이 있다. SQL문은 트랜잭션 구간에서 전송을 하게 되는데 실패하면 롤백을 한다. JPA는 트랜잭션이 끝나기 전까지 SQL을 모아두고 트랜잭션이 끝나는 시점에 한번에 전송을 한다. 그래서 데이터베이스 응용 레벨에서 Repeatable Read 수준의 격리레벨을 제공하는데, 이것은 데이터베이스의 신뢰성을 높이는 것과 같다.

마지막으로 JPA의 가장 큰 장점은 객체지향 프로그래밍의 설계 원칙을 지키도록 도운다는 점이다. 데이터베이스에 맞게 프로그래밍을 하면 객체지향을 잃어버릴 수 있는데 JPA가 그러지 않도록 객체지향을 유지시켜준다. 이것은 Spring을 사용하는 이유와 같다.

JPA의 단점은 객체의 응집력을 약화시킨다. 엔티티의 목적은 테이블을 매핑하는 것이라 객체의 성향과 달라서 추가적으로 DTO를 정의해야한다. 또한 JPA를 사용하면 의도치 않은 SQL이 발생할 수도 있다.

# Spring Data JPA
Spring에서 JPA를 편하게 사용할 수 잇도록 제공하는 모듈이다. 보일러 플레이트 코드를 제거하고, CRUD 처리를 위한 공통 인터페이스를 제공한다. 이를 사용하기 위해서 JpaRepository를 상속하는 인터페이스를 정의해야한다.

# JPA CRUD 실습
- 사용환경 : Java 11, 인텔리제이, MySQL, Maven
- 실습순서 : MySQL 테이블 생성 -> Maven 프로젝트 생성 -> 라이브러리 의존 설정 -> persistence.xml 생성 -> 클래스 생성 -> 엔티티 어노테이션 설정

pom.xml 의존성 설정 (maven repository에서 검색)  
1. Hibernate EntityManager Relocation
2. MySQL Connector/J (MySQL 버전 맞추기)

persistence.xml 설정  
1. resources 폴더 안에 META-INF 폴더 생성
2. META-INF 폴더 안에 persistence.xml 생성
3. https://gist.github.com/halyph/2990769 사이트에서 복사해서 name, url, user, password 등을 변경 (name은 엔티티 팩토리 매니저가 참조)
4. dialect는 데이터베이스의 방언으로 MySQL8Dialect로 설정

Movie class 생성  
1. 테이블에 넣을 컬럼을 매핑할 private 변수 선언
2. getter setter 생성
3. 클래스에 @Entity 어노테이션 설정
4. id 변수는 @id, @Column 어노테이션 설정
5. 일반적인 데이터 변수는 @Column 어노테이션 설정
6. @Column 어노테이션 안에는 매핑할 DB 컬럼명 설정  
ex) @Column(name="MOVIE_ID")

Main class 생성  
1. Persistence.createEntityManagerFactory() 설정, 매개변수는 persistence.xml의 persistence-unit name
2. createEntityManager() 설정, DB를 관장하는 팩토리에서 제공하는 EntityManager
3. getTransaction() 설정, 트랜잭션을 가져오기
4. try catch finally 생성
5. try에서 begin으로 트랜잭션 수행, Movie 인스턴스 생성, setter로 DB에 넣을 데이터 세팅, EntityManager의 persist에 인스턴스 설정, 트랜잭션 commit()
6. catch에 트랜잭션이 비었을 경우 rollback() 설정
7. finally에서 EntityManager close() 설정