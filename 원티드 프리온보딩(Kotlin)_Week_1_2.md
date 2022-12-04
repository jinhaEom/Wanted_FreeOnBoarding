## Java

1. Condition

자바의 조건문 :
- if~else
- switch(조건값) : 가능한 경우의 수를 case 절로 표현 (break 포함)
	-> switch 조건에 허용하는 값 타입 : char ,byte ,short, int, + Wrapper 클래스, String ,enum
	-> switch문의 조건값의 타입과 동일해야함 .

```
switch(month){
	case 1 ->{
		~~~
}
	case 2 ->{

		~~~
}
```

2. loop

반복문(iteration) : 코드를 반복적으로 수행하도록 하는 구문


```

for(int index = 0;     index < size'     	index++){
	   init			termination     increment

}
```
- initialization : loop 초기화, 시작할떄 한번 실행
- termination ; 조건이 false 가 되면 loop 종료
- increment: 반복문을 실행해 증감식 실행 

while loop
-> while(조건) { ...}
break : 가장 가까운 loop 종료

3. 클래스

- class 키워드 : 여러정보를 묶어서 표현할 수 있음.
- 클래스 멤버변수(field): 클래스 멤버변수 추가, 변수에 직접접근 X, 함수를 호출해야함

+ 기본생성자 ( 자동으로 생성 ) 
	- Object : 모든 자바의 클래스는 object를 슈퍼클래스로 가지고 있음. 
		즉 모든 클래스의 상위 클래스

- 인스턴스 생성
	- 인스턴스 : 클래스로 만드는 객체
	- 여러정보를 전달하고, 변수에 할당할 수 있다.
	- 변수에 할당한 클래스의 정보를 읽어올 수 있다. 

- 상속(extends)
	- 클래스는 상위클래스, 하위클래스를 만들 수 있다.
	- 하위클래스가 상위클래스의 기능을 사용할 수 있다. 
	- 클래스 생성시 상위 클래스 생성에 필요한 인자를 전달 해야함.

## Kotlin

1. Conditions

- 코틀린의 조건문 : if ~ else

- 함수 Coding convention 
	1. 반환타입 : 반환타입이 없는 경우 Unit 생략
	2. 공백/ 줄바꿈 규칙 지키기
	3. 함수의 파라미터 추가로 재사용성 높이기 

- 코틀린엔 switch 가 없고 if와 when 이 있음
	-> if & when 은 서로 대체할 수 있음. 
- when 은 여러개의 branch로 조건식을 정의 

- If expression(식)
	- 프로그래밍에서 하나의 값을 반환하는것을 expression 이라고 한다. 
	- if는 block의 마지막 값을 반환해 변수에 할당 가능, 이때 else 블럭은 반드시 필요

- for loop
	- ex) in 키워드 ex) for(name in names)
	- index 활용 및 range 지정  ex) for (index in 0 until nameSize)
	-> until, .. , downTo ,step 

- while , do while 의 차이점 
	-> do while 은 무조건 한번이상 실행 
- break : 가장 가까운 loop 종료 
- continue@{label} : 실행지점을 @{label}위치로 이동, 다음 loop 실행 

- 코틀린의 최상위 클래스 : Any ( 슈퍼클래스)
	- 클래스 앞에 open 키워드 ( open class Any )

- Superclass, subclass
	+ init블럭 : 클래스 생성시 실행되는 블럭


