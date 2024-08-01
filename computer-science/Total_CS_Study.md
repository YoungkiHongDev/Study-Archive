# 데이터 표현과 교환
## 데이터 포맷
복잡한 데이터를 주고받기위한 어떠한 약속을 데이터 포맷이라고 한다.

대표적으로 JSON, XML이 있다.

## JSON
자바스크립트 객체 문법을 따르는 문자열이다.

undefined를 제외한 기본 데이터 타입이나 다른 객체를 포함할 수 있다.

오직 key와 value만 담을 수 있으며, 큰 따옴표("")만 사용해야 한다.

JSON의 장점은 Text로 이루어져 있어서 컴퓨터와 사람 모두가 읽기 쉽고,
독립적이라 서로 다른 시스템 간에 통신이 용이하다.

주로 API, config 파일에 활용된다.

## XML
태그를 기반으로 구성되는 데이터 포맷이다.

최상단에 버전과 인코딩을 쓰고 태그를 열고 닫으며 작성한다.

대표적으로 sitemap.xml에 사용된다.

## sitemap.xml
검색 엔진 최적화(SEO)에 필수적인 파일이다.

사이트를 크롤링하여 데이터베이스에 저장하는 Bot이 페이지를 빠짐없이 수집할 수 있도록 서비스에 설정한다.

## JSON과 XML의 차이점
XML은 태그를 여러번 작성해야하므로 JSON에 비해 데이터가 무겁고 파싱에 JSON보다 더 많은 노력이 필요하다.

## API
API는 둘 이상의 컴퓨터가 통신할 때 어떤 방법을 사용할 지 정의하는 중계 계층이다.

API의 종류는 private, public 두 가지가 있다.

private은 내부적으로만 사용하며, 보안을 위해 해시키가 있어야만 볼 수 있다.

public은 모든 사람이 사용할 수 있지만 과도한 트래픽을 방지하기 위해 요청 횟수를 제한한다.

API는 메뉴판과 같다. 손님이 이미 만들어진 메뉴판에서 원하는 메뉴를 정해서 요청하면 그 메뉴가 나오는 방식과 같다.

파파고 API를 예로 들면, 요청URL에 HTTPS 프로토콜의 POST 방식으로 원본언어, 목적언어, 번역할 테스트까지 3가지의 파라미터를 적어서 보내주면 정해진 형태로 응답을 해준다.

그리고 이런 설명은 API 문서를 통해 보여주는데, API 문서는 백엔드에서 API 개발자가 만드는 문서로 이렇게 요청하면 이런식으로 응답해준다는 설명이 적혀있다.

API는 무조건 요청한다고 주는게 아니라 일반적으로 키를 발급받아야한다. 이 키는 API 요청이 너무 많으면 요금을 부과하기 위해 발급받게 한다. (빗썸 API의 경우 키를 발급받을 필요없이 API를 요청할 수 있다.)


## API의 장점
제공자는 중요한 부분을 드러내지 않을 수 있고 사용자는 필요한 정보만을 받을 수 있다.
Open API를 활용하여 개발 프로세스를 단순화 시키고 시간과 비용을 절약할 수 있다.


# 디자인 패턴
## 디자인 패턴 개요
프로그램 설계 시 발생했던 문제점들을 객체 간의 상호관계를 이용하여 해결할 수 있도록 하나의 '규약' 형태로 만들어 놓은 것이다.
규약을 정해서 기능을 모듈화 시키고, 디자인 패턴의 따라 하지 못하는 것들이 정해져 있어서 프로그래밍이 더 쉬워진다.
라이브러리, 프레임워크의 뼈대나 기초가 된다.

## 싱글톤 패턴
DI, Dependency Injection

싱글톤 패턴은 모듈 간 결합을 강하게 만든다는 단점이 존재하지만 의존성 주입을 통해 모듈 간 결합을 느슨하게 만들 수 있다.

직접적으로 하위 모듈에 의존성을 주지 않고, 의존성 주입자를 통해 간접적으로 주입한다.

서비스를 사용하는 클라이언트가 해당 서비스 구성방법을 알 필요가 없게 한다.

상위 모듈은 하위 모듈에 대한 의존성이 떨어지며, 이것을 **디커플링**이라고 한다.

**의존성 주입의 장점**
- 모듈들을 쉽게 교체할 수 있는 구조가 되어 테스팅이나 마이그레이션 하기가 수월하다.
- 애플리케이션 의존성 방향이 좀 더 일관되어 추론하기 쉬워진다.
- 객체들을 쉽게 교체할 수 있는 코드가 된다.

**의존성 주입의 단점**
- 모듈들이 더욱 분리되므로 클래스 수가 늘어나 복잡성이 증가한다.

> **마이그레이션** - 어떤 운영환경에서 좀 더 낫다고 여겨지는 다른 운영환경으로 옮겨가는 것  
> Ex1) 제이쿼리 기반 -> 뷰 기반  
> Ex2) MySQL -> MongoDB

## 싱글톤 패턴과 의존성 주입

싱글톤 패턴은 모듈 간 결합을 강하게 만든다는 단점이 존재하지만 의존성 주입을 통해 모듈 간 결합을 느슨하게 만들 수 있다.

직접적으로 하위 모듈에 의존성을 주지 않고, 의존성 주입자를 통해 간접적으로 주입한다.

서비스를 사용하는 클라이언트가 해당 서비스 구성방법을 알 필요가 없게 한다.

상위 모듈은 하위 모듈에 대한 의존성이 떨어지며, 이것을 **디커플링**이라고 한다.

**의존성 주입의 장점**
- 모듈들을 쉽게 교체할 수 있는 구조가 되어 테스팅이나 마이그레이션 하기가 수월하다.
- 애플리케이션 의존성 방향이 좀 더 일관되어 추론하기 쉬워진다.
- 객체들을 쉽게 교체할 수 있는 코드가 된다.

**의존성 주입의 단점**
- 모듈들이 더욱 분리되므로 클래스 수가 늘어나 복잡성이 증가한다.

> **마이그레이션** - 어떤 운영환경에서 좀 더 낫다고 여겨지는 다른 운영환경으로 옮겨가는 것
> Ex1) 제이쿼리 기반 -> 뷰 기반
> Ex2) MySQL -> MongoDB

## 팩토리 패턴
객체를 사용하는 코드에서 객체 생성하는 부분을 분리해서 추상화한 패턴이다.

상속 관계의 두 클래스 중 상위 클래스는 중요한 뼈대를, 하위 클래스는 객체 생성의 구체적인 내용을 결정한다.

상위 클래스와 하위 클래스가 분리되므로 결합이 느슨하다.

상위 클래스가 인스턴스 생성 방식을 알 필요가 없어서 더 유연해진다.

코드 리팩토링 시 한 곳에만 신경 쓰면 되므로 유지 보수성이 좋아진다.

## 이터레이터 패턴
이터레이터를 이용해 컬렉션의 요소에 접근하는 패턴이다.  
다른 자료구조를 이터레이터라는 인터페이스 하나로 순회가 가능하다.

> **컬렉션** - 컨테이너 혹은 동일한 요소들의 집합으로 예를들면, 배열이나 트리가 있다.  
> **이터레이터 프로토콜** - 이터러블한 객체들을 순회할 때 쓰이는 규칙  
> **이터러블한 객체** - 반복 가능한 배열을 일반화한 객체

## 전략 패턴
Strategy Pattern

전략 패턴은 정책 패턴이라고도 부른다.

객체의 행위를 바꾸고 싶은 경우 직접 수정하지 않고, 전략을 컨텍스트 안에서 상호 교체가 가능하게 만드는 패턴이다.

대표적으로 Node.js의 passport라는 라이브러리가 전략 패턴이 활용되었다.

passport는 인증 모듈 구현에 사용되는 미들웨어 라이브러리로, 아이디나 비밀번호를 기반으로 인증하는 LocalStrategy 전략과 네이버 같은 다른 서비스 기반으로 인증하는 OAuth 전략을 지원한다.

ex) 로그인 전략으로 페이스북? 네이버? 구글? 카카오?

> **컨텍스트** - 개발자가 어떠한 작업을 완료하는 데 필요한 모든 관련  
> **전략** - 캡슐화한 알고리즘

## 옵저버 패턴
주체가 어떤 객체의 상태 변화를 관찰하다가 상태 변화가 있을 때마다 메소드를 통해 목록에 있는 옵저버들에게 변화를 알려주는 패턴이다.

주체를 따로 두지 않고 객체만 두기도 한다.

MVC 패턴에도 사용되는데, 주체인 모델이 변경 사항이 생기면 메소드를 통해 옵저버인 뷰에 알리고 이를 통해 컨트롤러가 작동하도록 할 수 있다.

> **주체** - 객체의 상태 변화를 보는 관찰자  
> **옵저버** - 객체의 상태 변화에 따라 전달되는 메소드로 추가/변경 사항이 생기는 객체


# 자료구조
## 연결 리스트
자료 구조의 한 종류로 일렬로 연결된 데이터를 저장한다.
노드가 데이터와 다음 노드의 주소를 가지는 형태이다.

> **중간에 데이터를 삽입할 경우**
앞 노드가 가진 다음 노드의 주소를 중간에 삽입할 노드에 넣고 앞 노드에는 중간 노드의 주소를 넣는다.

> **중간의 데이터를 삭제할 경우**
중간 노드가 가진 다음 노드의 주소를 앞 노드에 넣는다.
그러면 중간 노드는 불러주는 앞 노드가 없어서 동작하지 않는다.
자바 같은 경우는 안쓰이는 변수를 자동으로 처리해준다.
하지만 C나 C++ 같은 경우는 반드시 안쓰겠다는 명시를 해주어야 한다.

## 단방향 연결 리스트
오직 다음 노드 주소만 가져서 한쪽 방향으로만 검색이 가능한 형태로 하나의 포인터만을 가진다.

## 양방향 연결 리스트
다음 노드 주소와 이전 노드 주소를 가져서 앞뒤 방향으로 검색이 가능한 형태로 두개의 포인터를 가진다.

> **중간에 데이터를 삽입할 경우**
1. 이전 노드의 다음 주소를 삽입 노드의 다음 주소에 넣는다.
2. 이전 노드의 다음 주소에 삽입 노드의 주소를 넣는다.
3. 다음 노드의 이전 주소를 삽입 노드의 이전 주소에 넣는다.
4. 다음 노드의 이전 주소에 삽입 노드의 주소를 넣는다.

> **중간에 데이터를 삭제할 경우**
1. 삭제할 노드의 다음 주소를 이전 노드의 다음 주소에 넣는다.
2. 삭제할 노드의 이전 주소를 다음 노드의 이전 주소에 넣는다.

## Array에 비교한 LinkedList의 장점
삽입, 삭제 과정이 필요한 데이터들을 배열로 구현한다면 데이터가 추가될때마다 배열을 다시 선언하여 재구성해야하므로 길이가 정해지지 않는 연결 리스트가 유리하다.

## ArrayList와 LinkedList의 차이점
ArrayList는 인덱스를 통해서 리스트를 구현한 자료구조이다.  
ArrayList의 수정/조회는 O(1), 삽입/삭제는 O(n)의 시간 복잡도를 가진다.

LinkedList는 앞뒤의 노드를 연결하는 리스트를 구현한 자료구조이다.  
LinkedList의 조회는 O(n), 삽입/수정/삭제는 O(1)의 시간 복잡도를 가진다.

ArrayList는 인덱스를 통한 빠른 조회가 가능하여 조회가 잦은 경우 사용하기에 적합하며, 무작위 접근이 가능하여 자료 검색이 필요한 경우에 용이한 자료구조이다.

LinkedList는 밀어주는 작업 없이 노드만 연결시켜 주면 되므로 삽입/삭제가 잦은 경우 사용하기에 적합하며, 순차적인 접근만 가능하여 자료 검색이 필요한 경우에 불리한 자료구조이다.


# 알고리즘
## 다익스트라 알고리즘
그래프에서 한 정점부터 다른 정점까지의 최단 경로를 구하는 알고리즘이다.  
정점 사이를 잇는 간선의 가중치가 양수일 경우에만 사용 가능하다는 특징을 가진다.  
최단 경로를 찾기 위해서 방문하지 않은 정점 중 가장 가까운 정점의 방문을 반복한다.  
이 과정에서 모든 정점을 최단 경로로 방문하여 각 정점까지의 최단 경로를 모두 찾게된다.

## 크루스칼 알고리즘
그리디 알고리즘의 일종이다.
간선의 가중치가 최소한이 되도록 모든 정점을 연결한다.
최소 신장 트리를 구하는 알고리즘이다.
정점의 개수가 N개일 경우 간선의 개수는 N-1개가 된다.
간선을 가중치의 오름차순으로 정렬하여 사이클이 형성되지 않도록 간선을 선택한다.

## 힙 정렬
완전 이진 트리의 일종으로 우선순위 큐를 위하여 만들어진 자료구조를 힙(Heap)이라고 하며, 이 자료구조를 기반으로 한 정렬 방식이다.  
최대값, 최소값을 구할 때 혹은 최대 K만큼 떨어진 요소들을 정렬할 때 유용하다.  
힙 정렬은 O(nlogn)의 시간 복잡도를 가지며, O(n)의 공간 복잡도를 가진다.  
내림차순 정렬에는 최대 힙을 구성하고, 오름차순 정렬에는 최소 힙을 구성한다.  
정렬하는 과정은 내림차순 기준으로 먼저, 정렬할 요소들로 최대 힙을 구성한다.  
다음으로 요소를 하나씩 힙에서 꺼내서 배열의 뒤부터 저장한다.  
그리하면 꺼낸 요소들은 값이 높은 순서로 정렬하게 된다.


# 네트워크
## 인터넷과 인트라넷
인터넷은 통신망들끼리 연결된 네트워크로 이를 관리하는 중앙 호스트나 조직이 존재하지 않는다.

인트라넷은 인터넷을 이용하여 조직 내부의 시스템을 구축한 것을 말한다.

공통점은 통신망을 이용한다는 점이다.

차이점은 인터넷은 모두 사용 가능하지만, 인트라넷은 특정 대상만 사용 가능한 것이다.

## 클러스터링 인덱스
클러스터링 인덱스는 키 값에 대한 테이블의 데이터 행을 정렬하는 인덱스다.  
테이블의 데이터를 정렬해서 저장되는 순서를 정의한다.  
테이블당 하나만 생성이 가능하다.  
리프 페이지가 모두 차있을 때 페이지 분할이 일어난다.

## 보조 인덱스
보조 인덱스는 데이터와 인덱스를 각각 다른 위치에 저장하는 인덱스다.  
해당 데이터의 위치에 대한 포인터가 인덱스에 포함된다.  
테이블당 여러개 생성이 가능하다.  
리프 페이지가 모두 차있어도 페이지 분할이 일어나지 않는다.

## 그래프와 트리의 차이점
그래프와 트리는 노드끼리 간선으로 연결하는 자료구조이다.

그래프는 네트워크 모델로서 순환 혹은 비순환 구조를 이루며, 방향성을 가지거나 무방향이다.
그래프는 루트 노드나 부모와 자식 개념이 없으며, 2개 이상의 경로를 가질 수 있다.

트리는 계층 모델로서 비순환 구조를 이루며, 방향성을 가진다.
트리는 루트 노드와 부모 노드가 존재하며, 1개의 경로만을 가진다.

## 회선 교환 방식
회선 독점을 통한 통신 방식이다.  
회선 교환 방식의 가장 큰 특징은 **전용선 할당**이다.  
예를들어, 전송할 데이터가 있다면 전송을 위한 전용선을 할당하고 해당 선으로 데이터를 전송한다.    
안정적인 통신이 가능하며, Point-To-Point 방식으로 연결된다.  
하지만 중간 경로에 문제가 발생하면 전체 연결이 끊어진다.  
대표적으로 음성 전화 시스템에 사용된다.

**회선 교환 방식 장점**
- 대용량 데이터 혹은 고속 데이터 처리에 우수하다.
- 고정적인 대역폭을 사용한다.
- 연속적인 데이터 처리에 우수하다.

**회선 교환 방식 단점**
- 대역폭을 낭비하여 회선 이용 효율이 떨어진다.
- 통신 과정에서 회선 문제가 생기면 회선 할당부터 다시 해야한다.
- 통신 비용이 비싸다.

## 패킷 교환 방식
전송 데이터를 패킷 단위로 나누어 네트워크 망으로 뿌려주는 통신 방식이다.  
패킷에는 해당 데이터의 몇번째 데이터인지와 최종 목적지에 대한 정보가 들어있다.  
이러한 패킷을 라우터가 확인하여 최적의 경로로 전달하며, 이 때 경로는 거리 뿐만 아니라 혼잡도, 연결 상태, 설정 등에 따라 수시로 변경된다.  
예를들어, 특정 데이터의 패킷이 100개로 나뉘어 전송된다면 라우터에 의해 서로 다른 경로로 전송될 수 있으며, 최종 목적지에서 원래 순서대로 다시 합쳐진다.  
패킷들의 전송 경로가 달라서 송신 패킷의 출발 순서와 수신 패킷의 도착 순서가 다를 수 있다.  
전송 속도와 흐름의 제어가 가능하다.  
패킷의 정보로 에러를 탐지할 수 있다.  
일반적인 인터넷 망에서 주로 사용된다.

**패킷 교환 방식 장점**
- 회선의 이용률이 높다.
- 라우터 고장 등의 장애가 발생하면 다른 경로로 즉각 전송 가능하다.
- 특정 패킷에 에러가 발생하면 그 패킷만 재전송이 가능하다.
- 다양한 통신망에서 사용이 가능하다.

**패킷 교환 방식 단점**
- 경로 탐색 과정에서 지연이 발생될 수 있다.
- 전송량 증가에 따라 지연률이 급격하게 상승한다.
- 패킷 헤더 추가로 인한 오버헤드 발생 가능성이 있다.

## 가상 회선 기술
패킷 교환 방식의 네트워크에서 회선 교환 방식처럼 통신하게 만들어주는 기술이다.  
패킷 단위로 데이터를 전송하지만, 사전에 구성된 특정 경로로 데이터를 전송하므로 모든 패킷을 같은 경로로 전송한다.  
따라서, 수신 측에서 패킷을 순차적으로 수신할 수 있다.  
하지만 경로를 선정하고 이를 위해 특수한 패킷을 네트워크에 전송해야하므로 첫 연결에 시간이 걸린다.  
또한, 경로는 일정하지만 전용 회선이 아니므로 다른 노드의 대량의 데이터가 유입될 경우 네트워크가 지연될 수 있다.


# 운영체제와 서버
## 운영체제
운영체제는 시스템의 자원을 관리하는 시스템 프로그램이다.  
사용자와 컴퓨터 간 인터페이스 역할을 한다.  
단일/다중 일괄 처리 시스템, 분산 운영체제, 실시간 운영체제로 분류된다.  
커널을 책임지는 동시에 시스템의 보호 및 보안도 담당한다.

## 커널
커널은 운영체제의 중요한 부분이다.  
소프트웨어와 하드웨어 간 인터페이스 역할을 한다.  
모놀리식 커널과 마이크로 커널로 분류된다.  
메모리, 프로세스, 작업 그리고 디스크를 관리한다.

## 서버의 이용 형태
1. 클라이언트의 요청에 대응하여 처리하는 형태  
일반적으로 클라이언트와 서버를 생각할 때 기대하는 기본적인 형태이다. 클라이언트가 서버에 요청하면 서버는 요청받은 처리를 수동적으로 실행한다.  

2. 서버에서 능동적으로 처리하는 형태  
서버 스스로 처리를 시작하고 실행하는 형태이다. 서버가 클라이언트나 산하 컴퓨터, 디바이스에 명령해서 처리한다.

3. 높은 성능을 활용하는 형태  
높은 성능을 가진 서버가 단독으로 구성되어, 독자적인 처리를 실행하는 형태이다. 향후 확대를 기대할 수 있는 분야인 AI 서버, 빅데이터 서버가 대표적이다.

## 대용량 트래픽 처리를 위한 서버 확장
이용자가 증가하거나 사업이 확장될 경우 서버의 용량과 성능을 증가시킬 필요가 있다.
이를 위한 방법으로 스케일 아웃과 스케일 업이 있다.

- **스케일 아웃** : 서버를 여러 대 추가하여 시스템을 확장시키는 방법이다. 각 서버에 걸리는 부하를 균등하게 나눠주는 로드밸런싱이 필수적이다. 서버 한 대가 장애가 일어나도 다른 서버가 서비스를 제공할 수 있는 장점이 있다. 하지만 모든 서버가 동일한 데이터가 있어야하므로 데이터의 변화가 적은 웹 서버에 적합하다.

- **스케일 업** : 서버를 고성능으로 교체하여 서버의 성능 자체를 높이는 방법이다. 부품을 추가하거나 서버 자체를 교체하는 방식으로 업그레이드 시킬 수 있다. 모든 부하가 한 서버에 집중되므로 장애 발생의 영향력이 클 수 있는 단점이 있다. 하지만 한 대의 서버에서 모든 데이터를 처리하므로 데이터의 변화가 많은 DB 서버에 적합하다.


# 라이브러리와 프레임워크
## Mybatis와 JPA
스프링(스프링부트)으로 개발할 때, 사용하는 데이터 엑세스 기술 중 대표적으로 사용하는 기술이 Mybatis, JPA이다.

1. Mybatis
Mybatis는 개발자가 SQL 쿼리를 직접 작성하고 매핑한다.
SQL 작성에 익숙한 개발자라면 세밀한 제어와 최적화가 가능하다.
또한, 레거시 데이터베이스와 연동하기가 쉽다.
레거시 데이터베이스는 예를 들면, IBM 혹은 버전이 오래된 Oracle, MS SQL Server 등이 있다.

2. JPA
JPA는 객체-관계 매핑으로 데이터베이스의 레코드와 자바 객체를 매핑한다.
객체지향 프로그래밍 방식으로 설계하는 데 유용하다.
개발자가 SQL 작성을 하는 대신에 객체를 조작하여 데이터베이스 작업을 수행하는 ORM 기술이다.

> 2가지 기술을 비교해보면 성능 최적화는 Mybatis, 개발 생산성은 JPA가 유리하다고 볼 수 있다.

## 라이브러리
라이브러리는 공통으로 사용할 수 있는 특정한 기능들을 모듈화 해놓은 것으로 폴더명, 파일명 등 규칙이 프레임워크에 비해 자유롭다.

## 프레임워크
공통으로 사용할 수 있는 특정한 기능들을 모듈화 해놓은 것으로 폴더명, 파일명 등 규칙이 라이브러리에 비해 엄격하다.

## 리액트와 뷰
리액트와 뷰는 둘 다 JavaScript 기반의 프론트엔드 라이브러리 또는 프레임워크이다.

**Vue.js**  
뷰는 주로 프레임워크로 여겨진다. 그렇지만 다른 프레임워크와 비교하면 가벼워서 라이브러리로도 사용된다.

뷰는 점진적으로 적용할 수 있어서 작은 부분에만 도입하거나 전체 애플리케이션에 적용한다.

뷰는 컴포넌트 기반의 아키텍처를 사용하며, 양방향 데이터 바인딩, 디렉티브 등을 통해 간편한 상태 관리를 제공한다.

**React.js**  
리액트는 주로 라이브러리로 여겨진다. 그 이유는 리액트 자체만으로는 전체 애플리케이션 구조를 정의하지 않고 상태관리, 라우팅 등 다른 기능을 위해 추가 라이브러리를 필요로 하기 때문이다.

리액트는 가상 DOM을 사용하여 성능을 최적화하고, 단방향 데이터 흐름을 강조하는 컴포넌트 기반 라이브러리이다.

리액트는 개발자에게 더 많은 자유를 주기 위해 명시적이고 간단한 API를 제공하며, 상태 관리와 라우팅은 개발자가 선택한 라이브러리나 프레임워크를 통해 처리한다.