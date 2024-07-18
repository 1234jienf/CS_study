### OAuth

- OAuth는 제3자 애플리케이션이 사용자의 비밀번호를 직접 취급하지 않고, 안전하게 자원에 접근할 수 있도록 해주는 인증 프로토콜

#### OAuth 흐름 개요

1. 사용자 권한 요청 : 사용자가 애플리케이션을 통해 리소스 서버 (예: 구글, 페이스북 등)에 접근을 요청한다.
2. 사용자 인증 : 리소스 서버에서 사용자가 로그인 하고, 애플리케이션이 접근할 수 있는 권한을 부여한다.
3. Authorization Code 수신 : 리소스 서버가 애플리케이션에 Authorization Code를 전달
4. Access Token 요청: 애플리케이션이 Authorization Code를 이용해 리소스 서버에 Access Token을 요청
5. Access Token 수신: 리소스 서버가 애플리케이션에 Access Token을 전달한다.
6. API 요청: 애플리케이션이 Access Token을 이용해 보호된 리소스에 접근한다.

#### 프론트엔드에서의 구현

1. 권한 요청

- 사용자가 로그인 버튼을 클릭하면, 권한 요청을 위해 리소스 서버의 인증 URL로 리디렉션한다. 이 URL은 클라이언트 ID, 리디렉션 URI, 요청 범위(scope) 등을 포함해야 한다.

2. Authorization Code 수신

- 사용자가 인증 및 권한 부여를 완료하면, 리소스 서버는 리디렉션 URI로 Authorization Code를 전달하고 프론트엔드에서 이를 처리한다.

3. Access Token 요청

- Authorization Code를 백엔드 서버에 전달하여 Access Token을 요청한다. 이는 보안상의 이유로 백엔드에서 처리하는 것이 일반적이다.

4. 보호된 리소스에 접근

- Access Token을 이용하여 보호된 API를 호출한다.

### OAuth 2.0과 OpenID Connect (OIDC)의 차이점

#### OAuth 2.0

- OAuth 2.0은 인증 및 권한 부여 프레임워크로, 제3자 애플리케이션이 사용자의 자원에 접근할 수 있도록 허용하는 프로토콜이다. OAuth 2.0의 주요 목적은 **자원 소유자(Resource Owner)로부터 허가를 받아 클라이언트 애플리케이션이 자원 서버(Resource Server)에 안전하게 접근하는 것입니다.**

#### OpenID Connect (OIDC)

- OpenID Connect는 OAuth 2.0을 기반으로 한 인증 레이어이다. OAuth 2.0은 자원에 접근하기 위한 권한 부여에 중점을 두지만, **OpenID Connect는 사용자의 인증을 다룬다. OIDC는 OAuth 2.0의 기능을 확장하여 ID 토큰(ID Token)을 사용해 사용자의 신원을 확인할 수 있도록 한다.**

- OAuth 2.0과 OIDC는 상호 보완적인 관계로, OAuth 2.0은 자원에 접근하기 위한 권한 부여를 다루고, OIDC는 OAuth 2.0을 확장하여 사용자 인증을 처리한다.
- OIDC를 사용하면 클라이언트 애플리케이션이 사용자의 신원을 확인할 수 있고, 이를 통해 사용자 인증과 권한 부여를 모두 안전하게 처리할 수 있다.

#### OIDC의 장점

1. 사용자 인증 포함: OIDC는 사용자 인증을 다루며, OAuth 2.0을 확장하여 ID Token을 사용해 사용자의 신원을 확인할 수 있다.
2. 표준화된 신원 확인: JSON Web Token (JWT) 형식을 사용하여 ID Token을 표준화된 방식으로 제공한다.
3. 보안 강화: 사용자 인증과 권한 부여를 함께 처리함으로써, 보다 통합된 보안 모델을 제공한다.
4. 사용자 정보 제공: OIDC는 사용자의 프로필 정보도 제공할 수 있어, 사용자 정보가 필요한 애플리케이션에 유용하다.

#### OIDC의 단점

1. 복잡성: OAuth 2.0에 비해 상대적으로 구현이 복잡하다.
2. 추가 설정 필요: OIDC를 구현하려면 OpenID Provider와의 추가 설정과 통합이 필요하다.
