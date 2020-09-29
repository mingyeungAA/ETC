# 🍞OAuth 2.0

- 외부서비스의 **인증** **(Authentication)** 및 **권한부여** **(Authorization)**를 관리하는 범용 프레임워크
- 이용하려는 서비스마다 회원가입 할 필요없이 기존의 사용하던 타사의 정보를 이용하여 로그인 진행가능

- 서버와 클라이언트 사이에 인증을 완료하면 서버는 권한부여의 결과로써 access tocken을 전송합니다.

<br>

## 🍰주요 4가지 객체(Roles)

🍭**resource owner** (자원 소유자, 사용자) 

​	👉 자원의 주인

🍭**resource server** (자원 서버) 

​	👉 보호된 resource를 가지고 있는 서버, 액세스하려는 API.

🍭**client** (클라이언트) 

​	👉 제 3의 서비스. 

​	👉 구글or페이스북 아이디로 로그인이 가능한 서비스. 

​	👉 resource owner를 대신해서 resource에 접근하려는 서비스.

🍭**authorization server** (권한 서버) 

​	👉 로그인을 통해 인증 후 권한을 부여하는 서버 (ex.구글 or 페이스북). 	👉 resource owner를 인증하고 권한을 얻은 후 access token을 발행하는 서버

<br>

### 🍰절차 protocol flow

1. client가 resource owner에게 권한 요청을 하게 된다.

   이때 권한 요청은 resource owner에게 직접하거나, resource server를 통해 간접적으로 이루어 질 수도 있다.

2. resource owner가 권한을 허가하면, client는 권한증서(Authorization Grant)를 발급받는다.

3. 권한증서(Authorization Grant)를 받은 client는 최종 목적인 access token을 authorization server에 요청한다.

4. 요청을 받은 authrization server는 client가 보내온 권한증서(Authorization Grant)의 유효성을 검증한다. 

   유효하다면, access token을 발급하고 결과를 client에게 알려준다.

5. access token을 받은 client는 resource server에 자원을 요청할 수 있게 된다.

6. 요청을 받은 resource server는 access token의 유효성을 검증하고 유효하다면 요청을 처리해준다.

<br>

## 🍰Access and Refresh Token

### 🍭Access Token

- 요청 절차를 정상적으로 종료한 client에게 발급된다.
- 보호된 자원에 접근할 때, 권한 확인용으로 사용된다.
- 문자열 형태
- 계정 아이디와 비밀번호 등 계정인증에 필요한 형태들을 이 토큰 하나로 표현함으로써, resource server는 여러가지 인증방식에 각각 대응하지 않아도 권한을 확인할 수 있게 된다.

<br>

### 🍭Refresh Token

- 한번 발급받은 access token은 사용할 수 잇는 시간이 제한되어 있다.
- 사용하고 있던 access token의 유효기간 종료 등으로 만료되면, 새로운 access token을 얻어야 하는데, 이때 refress token이 활용된다.
- authorization server가 access token을 발급해주는 시점에, refresh token도 함께 발급하여 client에게 알려주기 때문에, 전용 발급 절차 없이 refresh token을 미리 가지고 있을 수 있다.
- 단, authorization server에서만 활용되며, resource server에는 전송되지 않는다. 

<br>

## 🍰Access Token 발급받는 방법

🍭**Authrization Code**

- resource owner가 authorization server에게 자신이 누구인지 인증을 받고 접근 권한을 부여한다.
- 그러면 authorization code를 발급받고, client에게 전달한다.
- client는 authorization server로 가서 access token으로 변환하게 된다.
- access token을 바로 client로 전달하지 않아 잠재적 유출을 방지한다.
- authorization server가 client와 resource server간의 중재 역할을 한다.
- 로그인 시에, 페이지 url에 `response_type=code` 로 설정한다.

<br>

🍭**Implicit**

- OAuth 2.0에서 가장 많이 사용하는 방식.
- 권한 코드없이 바로 발급되어 보안에 취약하다.
- 주로 read only 서비스에 사용된다.
- 로그인 시에, 페이지 url에 `response_type=token` 로 설정한다.

<br>

🍭**Resource Owner Password Credentials**

- client에 계정 정보를 저장 후 직접 access token을 받아오는 방식.
- 로그인 시에, API에 `grant_type=password`로 전달됨.

<br>

🍭**Client Credentials**

- 애플리케이션이 confidential client일때, id와 secret을 가지고 인증하는 방식.
- 로그인 시에, API에 POST로 `grant-type=client_credentials` 로 전달된다.

<br>

---

참고

- https://nakanara.tistory.com/148
- https://medium.com/@jjhyuk15/oauth-2-0-%EA%B0%9C%EB%85%90-1c7e31ea58de
- http://blog.weirdx.io/post/39955