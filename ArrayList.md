# 🍞ArrayList

## 🍰ArrayList

- 일반 배열과 인덱스로 객체를 관리한다는 점에서 동일하다.
- 크기를 동적으로 늘릴 수 있다.
- 내부에서 처음 설정한 저장용량(capacity)가 있다.
- 설정한 저장용량 크기를 넘어서 더 많은 객체가 들어오게 되면, 배열 크기를 1.5배 증가시킨다.
- 특정 인덱스의 객체를 제거하면, 제거한 객체의 인덱스부터 마지막 인덱스까지 모두 앞으로 1칸씩 앞으로 이동한다.
- 인덱스 값을 유지하기 위해서 전체 객체가 위치를 이동한다.
- 잦은 원소의 이동, 삭제가 발생할 경우에는 LinkedList를 사용하는 것이 좋다.

<br>

## 🍰배열과 ArrayList의 차이

- 배열은 크기가 고정되어 있지만, ArrayList 사이즈는 동적인 배열이다.
- 배열은 primitive type(int, byte, char등)과 object 모두를 담을 수 있지만, ArrayList는 object element만 담을 수 있다.
- 배열은 제네릭을 사용할 수 없지만, ArrayList는 타입 안정성을 보장해주는 제네릭을 사용할 수 있다.
- 배열의 길이는 length변수를 쓰고, ArrayList는 size() 메서드를 써야한다.
- 배열은 element들을 할당하기 위해 assignment(할당) 연산자를 써야 하고, ArrayList는 add()메소드를 통해 element를 삽입한다.

<br>

## 🍰List<> 와 ArrayList<>의 차이점

>List<> list = new ArrayList<>();   ->  도형 list = new 정사각형;

> ArrayList<> list = new ArrayList<>();  -> 정사각형 list = new 정사각형;

- List는 인터페이스이고 ArrayList는 List에 상속된 클래스이다. 
- 따라서 ArrayList는 단독으로 사용할 수 없다.

<br>

## 🍰LinkedList

- 노드 간에 연결을 통해서 리스트로 구현된 객체이다.
- 다음 노드의 위치 정보만가지고 있으며, 인덱스를 가지고 있지 않기 때문에 탐색시 순차접근만 가능하다.  -> 노드 탐색시 시간이 많이 소요됨
- 노드 추가/삭제는 위치정보의 수정만으로 가능하기 때문에 성능이 좋다.

<br>

## 🍰 Vector

- ArrayList와 동일한 내부구조를 가지고 있다.
- Vector 객체를 생성하기 위해서는 저장할 타입을 지정해야 한다.
- Vector 클래스는 동기화된(synchronized) 메서드로 구성되어 있다.
- 그렇기 때문에 멀티 스레드 환경에서 안전하게 객체를 추가, 삭제할 수 있다.

​       (Thread Safe)

- 동기화가 되어 있어서, ArrayList보다는 객체를 추가, 삭제하는 과정은 느릴 수 밖에 없다.
- 데이터 추가 시 공간이 부족한 경우 배열 크기를 2배로 증가시킨다.

<br>

## 🍰 노드 삽입 과정 비교

- ArrayList, Vector
  1. List의 크기를 삽입될 자료만큼 늘리는 연산을 수행합니다.
  2. 삽입될 자료의 위치를 기준으로 기존의 데이터들을 뒤로 혹은 앞으로  이동하는 연산을 수행합니다.
  3. 해당 위치에 자료를 입력한 후 삽입 연산을 마치게 됩니다.
- LinkedList ( 노드 생성 후 주소값만 변경됨)
  1. 추가될 자료의 node를 생성합니다.
  2. 추가될 자료의 해당 인덱스 이전의 node의 다음 node를 추가될 node로 설정합니다.
  3. 추가될 node의 다음 node를 인덱스 이전 node의 다음 node로 설정합니다.

<br>

**👉 ArrayList : 객체 검색, 맨 마지막 인덱스에 객체 추가에 좋은 성능을 발휘함**

**👉 LinkedList : 객체 삽임 및 삭제에 좋은 성능을 발휘함**

**👉 Vector : 멀티스레드 환경에서 사용**

<br>

---

참고

- https://velog.io/@adam2/Array%EC%99%80-List%EA%B7%B8%EB%A6%AC%EA%B3%A0-Java-List

<br>