## Java

1. 변수 

- Java의 변수 -> 값을 저장하고 참조할 수 있는 것
선언방식 = {타입}{변수명} = {초깃값};
		String message = "Hello, World";
- 활용 - 처음에 선언한 값을 변경 가능, 
타입별로 지원해주는 여러 메서드를 사용해 원하는 결과 구현 가능

Naming Rules => Camel case 

2. 타입
primitive Types

- 정수 표현형 : byte, short, int ,long (뒤로갈수록 범위 높아짐)
- 실수 표현형(Floating point) : float , double 
float : 1.5f
double : 1.5

- Boolean 표현형 : 진리값(true, false)를 나타내는 타입 
ex) 
int age = 11;
boolean isTeenager = age >= 10 && age< 20;

- Char : 하나의 문자만 전달하는 타입
ex) char character = 'K';

String : 문자열을 double quotes 로 표기하는 타입 
- '+' 연산자는 문자열을 연결시키는 동작을 수행
- concat() 함수와 동일

Wrapper Class
- primitive type 에 대응하는 참조타입
- primitive type 에 앞글자를 대문자로 (byte -> Byte, short->Short...etc)

- boxing -> primitive type을 대응하는 wrapper class 객체로 변경
- unboxing -> wrapper class의 데이터를 대응하는 primitive type으로 변경
- Autoboxing -> primitive type 과 wrapper type을 함께 사용할 떄 컴파일러가 자동으로 변환
해주는 기술

- 기본값 : 클래스 변수는 초기값을 할당하지 않아도 기본값으로 초기화 됨
	  지역변수는 반드시 초기값을 할당해야 함..
```
ex) 
String message;
System.out.println(message); -> 에러 발생 message를 초기화 해야함 
```
Array
-같은 타입의 데이터로 구성되며, 생성할 때 배열의 크기 결정
- Array에 추가된 각 데이터를 element라고 부르며 index로 데이터에 접근 가능 

(1) 선언
	int [] intArray;
	int [] intArray = new int[3];
	int [] intArray = {1,2,3};

* Method(함수)
```
public           static        void      main      (String[]       args){
접근제어자		               반환타입 함수명     파라미터타입
```
- Java에서 함수는 클래스의 멤버로 추가해야 한다.
	+ 메서드 시그니처(signature) -> 메서드 이름과 파라미터 타입을 의미하며, 메서드를 구분하는 기준이 됨. 
	+ 오버로딩 : 메서드의 이름이 같고 매개변수의 갯수나 타입이 달라야 한다. (리턴값만 다르면 오버로딩 x)


## Kotlin

1. 변수 
- 선언 방식 : val message : String = "Hello World"
	Type 생략 , 초기화 : val userName = "jinha"

-	val : 변경 불가 (immutable)
	var : 변경 가능 (mutable)

2. 타입 

- 정수형 타입 : Byte, Short, Int, Long -> Number() 의 하위타입 

- String : 문자열을 "" 로 표기하는 타입

- Array : index와 index에 대응하는 데이터들로 이루어진 자료구조(IntArray, ShortArray, FloatArray 등 ) 
ex) val numbers= intArrayOf(2,5,8,12)..

3. 함수 
```
fun       main        (args: Array<String>)       {  //실행하는 시점에 데이터를 전달하고 싶을때 인자 전달. 
	     함수명	     파라미터 
}
fun main(){

}
```
- Trailing comma
```
ex) fun show(
	price : Int,
	deliveryCharge : Int,)
->  마지막에 추가 및 제거 할때 diff가 한 줄로 되어 히스토리를 깔끔하게 유지 가능 

```
- Null
	Nullable types : 변수에 null 할당을 허용하는 타입 
	ex) var userName : String ? = null

- Kotlin 코드는 Java코드를 사용 할 수 있다.
	-> Kotlin 코드가 Java코드에 접근하려면 public 을 추가해야한다.

	Java코드는 Kotlin 코드를 사용 할 수 있다.
		-> Java 코드가 Kotlin의 변수를 호출하려면 변수명에 자동으로 get이 추가된 함수를 호출하면 된다.

Getter, Setter




 