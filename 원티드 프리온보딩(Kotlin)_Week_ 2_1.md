### interface

interface Walker{
	val name : String
	val stepCount = 0
	fun walk()
	}
}
val stepCount = 0

fun walk()
- 프로퍼티 정의 가능
- 프로퍼티 상태 저장 불가능
- 본문이 있는 함수도 정의 가능 
- 인터페이스도 클래스처럼 상속 가능 
- interface에서 정의만 했던 프로퍼티, 함수는 상속을 받으면 필수로 구현해야 한다. 

인터페이스 <-> 클래스 
- interface에서 정의만 했던 프로퍼티, 함수는 abstract class와 같은 동작을 한다. 
- 클래스 상속은 1개까지 가능하다. 
- but 인터페이스는 상속 갯수 제한이 없다.
- 상속받으면서 프로퍼티는 생성자가 될 수 있다.


클래스 / 인터페이스를 선택하는 기준 
- 클래스는 상속이 하나만 가능함 but 인터페이스는 여러개 가능 
- 변수는 선언만 가능 상태저장 불가 

### Visibility Modifier (가시성 변경자)
-  public(modifier) = 기본값, 어느 위치에서든 참조 가능(scope)
- private(modifier) = 선언한 클래스 내부에서만 참조 가능(scope)
- internal(modifier) = 같은 module 안에서만 참조 가능(scope)
- protected(modifier) = private과 동일 + subclass에서는 참조 가능(scope)
- const(modifier) = compile time에 값을 알 수 있는 read-only 프로퍼티, String/ 기본타입의 값을 
할당 할 수 있다.
	- const의 네이밍 컨벤션은 대문자로 쓴단어 _로 연결
	- top-level 프로퍼티가 될 수 있다.
	- custom getter를 정의할 수 없음 
- public 은 기본값이기 때문에 추가하지 않음 
- 다른 module의 코드도 가시성 변경자가 public인 경우 호출 가능 

### Null & 타입 검사 연산자
null 검사 관련 연산자
	-?. -> safe call
	-?: -> Elvis
	- !! : Not null assertion
- Type 검사 관련 연산자
	- is , !is -> Type check
	- as, as? : Type cast
	-as?는 타입 변환에 실패하면 null을 반환한다. 
- 연산자를 활용해 Exception이 발생 가능한 상황에 적절히 대응하는 코드를 추가해야함

### 컬렉션 
Collection : 같은 타입의 여러 객체를 저장하고 관리학 위해 설계된 자료구조

Collction types
- read-only( 읽기전용)
	- collection elements에 접근해 값을 읽을 수 있도록 지원
- mutable (쓰기 가능)
	- read
	-collection elements의 추가 수정 삭제 지원

List
- 순서를 갖고있는 collection
- index로 element에 접근 가능 
- 해당 index의 값이 없는 경우 exception을 발생시키는 대신에 다른 값을 반환하는 함수를 지원
	-ex) getOrNull ,firstOrNull...etc
- List는 element의 unique 여부를 판별하지 않는다.
- List가 같다 = 크기가 같고, 같은 위치에 동일한 element 를 갖는다.

MutableList
- 쓰기 가능한 List
- 지정한 위치(index) 에 element 추가,수정,삭제 가능

Set
-Set의 정의는 ordered collection 을 의미하지는 않지만, 코틀린에서 Set은 element의 순서를
유지하는 특징을 갖는다.
- 지정한 위치의 element에 접근할 수 있다.
- Set이 같다 = 크기가 같고, ㄷelemt가 모두 동일하다
- Set이 서로 같다는 의미는 element의 순서와는 무관하다.

Map
-a set of key-value pairs
- Map의 key 는 unique 하다
- Map은 Collection을 상속받지 않음
- 초기화 방법 : key, value 쌍의 collection element를 콤마로 구분해 인자로 제공
- 빈 Map로 생성 : key, value의 타입 정리 
- 해당 위치의 값이 없는 경우에도 Map은 Exception을 발생시키지 않는다. 
- 이미 추가되어있는 key라면 마지막에 추가한 값으로 변경됨
- key가 unique하다면 ,value는 같을 수 있다. 
- Map 이 같다 = 크기가 같고, element가 모두 동일하다
- Map이 서로 같다는 의미는 key,value 쌍의 순서와는 무관하다.

MutableMap
- 쓰기가 가능한 Map
- element 추가 수정 삭제 가능
