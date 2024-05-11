## REST

```
REST(Respresentatinal State Transfer)란 자원을 이름으로 구분해 해당 자원의 상태를 주고 받는 모든것을 의미
```

- 즉, HTTP URI(Uniform Resource Identifier)를 통해 자원(Resource)를 명시하고, HTTP Method(POST, GET, PUT, DELETE, PATCH 등)을 통해 해당 자원(URI)에 대한 CRUD  Operation을 적용하는 것을 의미한다.

#### CRUD
- Create, Read, Update, Delete를 묶어서 부름
- REST에서의 CRUD Operation 동작 예시
  - Create : 데이터 생성(POST)
  - Read : 데이터 조회(GET)
  - Update : 데이터 수정(PUT, PATCH)
  - Delete : 데이터 삭제 (DELETE)

#### REST 구성 요소

- 자원(RESOURCE) : HTTP URI
- 자원에 대한 행위: HTTP Method
- 자원에 대한 행위의 내용 : HTTP Message Pay Load

#### REST의 장단점
- 장점 :
  - 1. HTTP 프로토콜의 표준을 최대한 활용해서 여러 추가적인 장점을 함께 가져갈 수 있게 해준다.
  - HTTP 표준 프로토콜에 따르는 모든 플랫폼에서 사용이 가능하다.
  - REST API 메시지가 의도하는 바를 명확하게 나타내므로 의도하는 바를 쉽게 파악할 수 있다.
  - 여러가지 서비스 디자인에서 생길수 있는 문제를 최소화한다.
  - 서버와 클라이언트의 역할을 명확하게 분리한다.
- 단점 :
  - HTTP Method 형태가 제한적이다.
  - 브라우저를 통해 테스트할 일이 많은 서비스라면 쉽게 고칠수 있는 URL보다 Header 정보의 값을 처리해야하므로 전문성이 요구된다.
  - 구형 브라우저에서의 호환이 되지 않아 지원해주지 못하는 동작이 많다(익스플로어)

#### REST의 특징 
1. Server - Client ( 서버 - 클라이언트 구조)
2. Stateless(무상태)
3. Cacheable(캐시 처리 가능)
4. Layered System(계층화)
5. Uniform Interface(인터페이스 일관성)

## API
```
API(Application Programming Interface)는 다른 소프트웨어 시스템과 통신하기 위해 따라야하는 규칙을 의미합니다.
```

#### REST API

```
REST API(Representational State Transer API)란 REST의 아키텍처 스타일을 따르는 API를 의미합니다.
```

### REST API 설계 예시


REST API(Representational State Transfer API)란 REST의 아키텍처 스타일을 따르는 API를 의미합니다.

REST API 설계 예시

URI는 명사, 소문자를 사용해야한다.
Bad Example http://lsh98.com/Studying/
Good Example http://lsh98.com/study/
마지막에 슬래시(/) 포함하지 않는다.
Bad Example http://lsh98.com/study/
Good Example http://lsh98.com/study
언더바 대신 하이폰을 사용한다.
Bad Example http://lsh98.com/study_blog
Good Example http://lsh98.com/study-blog
파일 확장자는 URI에 포함하지 않는다.
Bad Example http://lsh98.com/photo.png
Good Example http://lsh98.com/photo
행위를 포함하지 않는다.
Bad Example http://lsh98.com/delete-post/1
Good Example http://lsh98.com/post/1
