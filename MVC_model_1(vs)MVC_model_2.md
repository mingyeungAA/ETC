# 🍞MVC model 1 (vs) MVC model 2

- **Model**

  - 백그라운드에서 동작하는 로직을 처리

  - Dao(Data Access Object)

    👉 DB에 접근하는 객체이다.

    👉 DB를 사용해 데이터를 조회하거나 조작하는 기능을 한다.

    👉 Dao를 사용하는 이유는 효율적인 커넥션 관리와 보안성 때문이다.

  - Dto(Data Transfer Object) 

    👉 각 계층간 데이터 교환을 위한 자바 객체

    👉 데이터를 각 레이어 간에 전달하는 목적을 가지고 있으며, 객체의 속성과 getter, setter만 가지고 있다.

  - Biz(Business Logic) 

    👉 계산(연산) / 처리

    <br>

- **Controller**

  - 사용자의 입력처리와 흐름제어를 담당한다.
  - Model과 view사이의 상호작용을 관리한다.
  - 화면 제어

  <br>

- **View**

  - 사용자에게 제공할 화면
  - 화면 자체

<br>

## 🍰MVC model 1

- Controller에 view를 같이 구현하는 방식
- 사용자의 요청을 jsp가 전부 다 처리한다. (=Controller역할을 jsp가 담당한다.)
- 빠르고 쉽게 개발할 수 있다.
- jsp파일 자체가 비대해지고, Controller와 view가 분리되어 있지 않아, 유지보수에 어려움이 있을 수 있다.

<br>

## 🍰MVC model 2

- Controller와 view가 분리되어 있는 구현방식
- 클라이언트의 요청으 먼저 servlet이 받는다. (=Controller역할을 servlet을 담당한다.)
- 디자이너와 개발자의 분업이 가능하고 유지보수에 유리하다.
- 설계에서 어려움을 겪을 수 있고, 개발 난이도가 높다.

<br>