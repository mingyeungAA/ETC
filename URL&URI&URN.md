# 🍞URL? URI? URN?

### 👉URI=URL+URN

<br>

## 🍰URI (Uniform Resource Identifier)

- 통합 자원 식별자
- 인터넷에 있는 자원을 나타내는 유일한 주소이다.
- URI의 존재는 인터넷에서 요구되는 기본조건으로서, 인터넷 프로토콜에 항상 붙어다님.
- URI의 보편적인 형태가 URL인데, URI의 부분집합으로 볼 수 있다.
- **http://test.com/test.pdf?docid=111 이라는 주소는 URI이지만 URL은 아니다.**
  - http://test.com/test/pdf 까지만 URL이다.(주소의 위치)
  - docid=111 이라는 쿼리스트링의 값에 따라 결과가 달라진다. docid=111은 식별자 역할을 한다.
- http://test.com/test.pdf?docid=111 와 http://test.com/test.pdf?docid=112 는 같은 URL을 가지지만, 다른 URI를 가진다.

<br>

## 🍰URL (Uniform Resource Locator)

- 자원(자원의 위치)
- 예전에는 URL이 가르키는게 파일소스였다.
- 요즘은 Rewrite등의 아파치, 톰켓등의 핸들러 때문에 자원이라고 부름
- 웹사이트 주소가 요청하는 파일이라기 보다, 구분자로 보는것
- 웹 상에 서비스를 제공하는 각 서버들에 있는 파일의 위치를 표시하기 위한 것.
  - http://blong.com/work/test.pdf 는 blog.com서버에서 work폴더 안의 test.pdf를 요청한 것.

<br>

## 🍰URN (Uniform Resource Name)

- 위치와 상관없이 리소스의 이름값을 이용해서 접근하는 방식
- 해당 리소스의 위치정보가 아닌 실제 리소스의 이름으로 사용하는 방식

<br>

---

참고

- https://velog.io/@pa324/%EA%B0%9C%EB%B0%9C%EC%83%81%EC%8B%9D-URI-URL-%EC%B0%A8%EC%9D%B4-%EC%A0%95%EB%A6%AC

  <br>