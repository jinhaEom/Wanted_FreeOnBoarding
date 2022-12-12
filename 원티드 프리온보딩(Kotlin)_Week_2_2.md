클래스 활용 , Generic , Scope 함수 

## 클래스 활용
- data class
	- Any는 모든 Kotlin 클래스의 상위 클래스로 알려져있다.
	- Any 클래스 선언 및 함수에 모두 open 키워드가 추가되어 있다.

- Equality operator ==, === , !=, !==
- 람다의 인자로 확장함수의 수신 객체를 this로 참조할 수있다.

- ==,!= : 값이 같은지 비교, equals()를 호출하는것과 같다.
- equals 구현 조건 : 반사성, 대칭성, 추이성, 일관성, null이 아닌 값과 null은 같을 수 없다.

- Referential equality (===, !==) : 주소값이 같은지 비교, 기본타입은 == 연산 결과와 같다.

hashCode
- 해시값, 해시코드 ,해시 체크섬, 해시 : 해시 함수가 반환하는 값
- 해시함수 : 해시 테이블이라는 자료구조에서 빠른 검색을 위해 각 key에 숫자를 할당하는 함수 

HashSet
- Set을 구현한 클래스
- HashMap으로 해시테이블을 만들어 Set의 동작 구현
- element가 unique한지 확인 할 때 hashCode를 사용한다..

data class
- data class 는 equals, hashCode, toString을 재정의할 필요가 없다.

object
- object를 선언하는 방법은 class와 비슷
- object는 class와 다르게 생성자를 만들 수 없다.
- store는 생성자를 갖지 않으므로 Store의 변수/함수를 사용하기 위해 인스턴스를 만들지 않고, 변수명과 함수명으로 호출
-object 명을 생략하고 import를 활용할 수도 있다.
- object는 싱글톤 패턴을 구현한 결과와 같다.
- 싱글톤 패턴은 프로그램 전체에서 인스턴스를 하나만 만들어서 사용할 때 활용한다. 

object expressionss : 무명객체
- object로 무명객체를 만들어 변수에 할당 가능
- object expression 도 Any 를 상속받으므로 Any의 함수를 오버라이딩 할 수 있다. 
- 클래스나 인터페이스를 상속하는 용도로 사용 가능 

companion object
- companion object의 멤버는 클래스 이름을 사용해 호출 가능
- companion object의 생랴된 기본 이름은 Companion 이다.

Nested class / inner class
중첩 클래스 	/   내부 클래스
- outer 클래스의 멤버에 접근가능, outer 클래스에 대한 참조가 필요할 때 inner클래스 사용

this expression
- 1. 클래스의 멤버인 경우 : 클래스의 멤버가 this를 사용하는 경우 this는 이 클래스로만든 객체를 가리킴
- 2. scope이 여러개인 경우 : outer scope이 여러개인 경우 this는 가장 가까운 scope를 가리킴
- 특정 스코프를 쓸 경우 this@label 사용

enum class / sealed class

- enum class : 같은 타입의 여러 상수 정의 , comma로 구분
	- 생성자 ,프로퍼티 선언 가능, 함수 선언 가능

sealed class
- 클래스간 계층정의 , 같은 패키지 내에서만 subclass 선언

Generic
- 제네릭 클래스 : 클래스를 선언할 때 타임 파라미터와 함께 쓰는경우
	- (타임파라미터 : <>안에 타입을 정의한 것)
- 제네릭 타입 : 제네릭 클래스와 제네릭 인터페이스를 의미한다. 

Function types
- 표기 방식: (parameter) -> return type
	-파라미터 명과 타입을 선언하는 것도 가능
	- 파라미터는 여러개가 될 수 있다.
	- ex) (Int) -> Boolean..

함수타입과 람다 (함수표현식)
- 함수의 마지막 파라미터가 함수인 경우, 람다식을 함수의 인자로 전달할 수 있다.
- 람다의 인자는 it으로 접근할 수 있지만, 의미있는 이름으로 바꾸어 사용할 수 있다.

kotlin의 함수는 first class
- 함수를 다른 함수의 인자로 전달 가능
- 다른함수의 반환값이 될 수 있음
- 함수를 변수에 저장 가능

고차함수
- 함수를 인자 /반환값으로 다룰 수 있는 함수

let
- let은 확장함수이다.
- 람다의 인자로 확장함수의 수신 객체를 it으로 참조할 수 있다.
- let의 반환타입은 람다 본문의 마지막값으로 결정된다. 
- let은 확장함수이므로 수신객체의 함수처럼 사용할 수 있다.
	- it 은 의미있는 이름으로 바꿀 수 있다.
- ?.와 함께 사용하면, 람다의 인자로 null이 아닌 값을 받을 수 있다.

run
- run도 확장함수
- 람다의 인자로 확장함수의 수신 객체를 this로 참조할 수있다.
	-block은 수신 객체가 함수의 parameter와 함께 전달된다.
	- T.()는 parameter가 없으므로 수신 객체에 대한 참조 this만 전달된 것이다.
- run의 반환 타입은 람다 본문의 마지막 값으로 결정된다.
- run은 확장함수이므로 수신객체의 함수처럼 사용할 수 있다.

with
- with는 확장함수는 아니다
- 람다의 인자로 확장함수의 수신 객체를 this로 참조할 수 있다.
 
apply
- apply는 확장함수
- 람다의 인자로 확장함수의 수신 객체를 this로 참조할 수있다.
- apply는 수신객체를 반환한다.
	-람다 본문의 결과를 반환하지 않는다.

also
- also는 확장함수이다
- 람다의 인자로 확장함수의 수신 객체를 it으로 참조할 수있다.

수신객체가 업는 run
- run은 확장함수가 아니다
- block은 여러 코드를 실행할 수 있는 람다로 활용된다.
- run의 반환타입은 람다 본문의 마지막 값으로 결정된다.
