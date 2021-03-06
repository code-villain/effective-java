# item57) 지역변수 범위를 최소화하라

## 장점
**코드 가독성 향상** -> 유지보수성 향상, 오류 가능성 감소

## 지역변수를 최소화하는 방법
1. 가장 처음 쓰일 때 선언하기
2. 반복문에서 사용한 변수를 반복문 이후에 사용할것이 아니라면 while문 보다는 for문을 사용한다.
3. for문에서 반복조건을 반환하는 메서드의 계산비용을 아끼기 위해서 별도의 변수를 사용하지 않아도 된다.
	```
	for (int i =0, **n = list.size()**; i < n; i++) {
		...
	}
	```
4. 메서드를 작게 유지한다.

# item58) 전통적인 for문 보단느 for-each문을 사용하라
- 전통적인 for문의 문제점 : 반복문을 사용하기 위한 인덱스나 반복자(이터레이터)를 사용하여 실제 '요소'와 관계없는 변수들이 노출되어 가독성이 나빠진다.
- for-each문의 장점 : 
	1. 다른 변수 없이 실제 '요소'에만 집중할 수 있게된다. 
	2. 내부적으로 iterator를 사용하기 때문에 LinkedList같은 자료형도 빠르게 순회가 가능하다.
		- 역설적으로 이러한 이유로 해당 요소를 파괴하거나 변형하는 일이 불가능하다. 아예 이터레이터를 직접 사용한다면 remove() 메서드를 사용할 수 있지만 for-each문을 내부에 숨겨져 있기 때문에 불가능하다.
		- 추가적으로 '인덱스'값을 사용하여 접근해야 하는 경우도 불가능 할 것이다.


# item59) 라이브러리를 익히고 사용하라

## 라이브러리를 사용시 장점
1. 그 코드를 작성한 전문가의 지식과 경험을 활용할 수 있다. (+ 그러기에 더 좋은 알고리즘을 적용할 수 있었을 것이다.)
2. 핵심적인 일과 관계 없는 문제를 빠르게 해결 할 수 있다.
3. (라이브러리가 좋아진다면) 추가적인 노력없이 성능이 지속적으로 개선된다.
4. (라이브러리가 좋아진다면) 추가적인 기능이 점점 추가 될 것이다.
5. 많은 사람에게 낯익은 코드가 되어 '다른' 개발자들이 더 읽기 좋고 유지보수하기 좋은 코드가 된다.

# item60) 정확한 답이 필요하다면 float와 double은 피하라
float와 double은 '빠르게 근사치'를 계산하도록 만들어 졌다. (과학, 공학용 계산기) 정확한 계산이 필요한 금융계산과는 맞지 않는다.
정확한 계산이 필요하다면 BigDecimal, int 혹은 long을 사용해야 한다. (int와 long을 사용하는 경우 소수점 부분을 별도로 계산)

BigDecimal은 정확하게 계산할 수 있지만, 기본타입에 비해 쓰기 불편하고 느리다.

cf) BigDecimal vs BigInteger
BigDecimal은 부동소수점을 다루고 BigInteger는 정수를 다룬다.

# itme61) 박싱된 기본 타입보다는 기본타입을 사용하라
##) 박싱된 기본타입의 단점
1. == 로 비교하는 식별성(identity) 속성을 갖기 떄문에, 같은 값이라도 다르게 식별 될 수 있다.
2. NPE의 위험성을 갖고 있다. (null을 다룰 수 있지만, 숫자로써 유효하지 않은 값을 다뤄야 한다는 것이다.)
3. 기본타입에 비해 시간과 메모리 사용면에서 비효율적이다. 
4. 오토박싱, 오토언박싱을 잘 예측하여서 사용해야 한다. 반복된 오토박싱으로 인해서 성능 저하가 올 수 있다. `기본타입과 박싱된 기본타입을 혼용한 연산에서는 박싱된 기본타입의 박싱이 자동으로 풀린다.`

##) 박싱된 기본타입을 써야하는 경우
매개변수화 타입 (제네릭 타입)에서 사용해야 하는 경우

# item62) 다른 타입이 적절하다면 문자열 사용을 피하라
문자열(String)은 "텍스트"를 표현하도록 설계되었고, 그러한 목적으로만 사용해야 한다.
문자열보다는 열거타입(enum), 클래스, 적절한 값을 사용해야 한다.

# item63) 문자열 연결은 느리니 주의하라
String은 불변이라서 새로운 문자열이 조합되면 계속 새로운 문자열 객체를 만들어 낸다. 간단한 문자열 연결 연산이 아니라면 StringBuilder의 append()를 사용해야한다.

# item64) 객체는 인터페이스를 사용해 참조하라

## 장점
인터페이스를 타입으로 사용하면 프로그램이 훨씬 유연해진다. 다른 구현 클래스로 교체하기 쉬워진다. (전략패턴)

# item65) 리플렉션보다는 인터페이스를 사용하라
리플렉션은 런타임에 존재하지 않을 수도 있는 클래스, 메서드, 필드와의 의존성을 관리할떄만 사용해야한다. 리플렉션의 기능적인 장점을 제외하고는 단점이 너무 많다.

## 리플렉션의 단점
1. 컴파일타임 검사가 되지 않는다.
2. 코드가 지저분하고 장황해진다.
3. 성능이 떨어진다.

# item66) 네이티브 메서드는 신중히 사용하라

## 정의
### 네이티브 메서드
C나 C++같은 네이티브 프로그래밍 언어로 작성한 메서드

## 네이티브 메서드를 신중히 사용해야하는 이유
리플렉션과 마찬가지고 네이티브가 주는 기능적인 이유를 제외하고 사용하기엔 이점이 없다.
네이티브 메서드를 써야하는 이유는 심각한(?) 플랫폼(OS) 특화 기능을 사용하거나, 기존 라이브러리가 네이티브로 되어있어서 부득히하게 사용해야하는 경우뿐이다.

예전에는 성능을 목적으로 사용되기도 했지만 JVM이 좋아지면서 이러한 이점은 없어졌다.

# item67) 최적화는 신중히 하라
`빠른 프로그램보다는 좋은 프로그램을 작성하라. 좋은 프로그램을 작성하다 보면 성능은 따라 나오게 마련이다.`

`구현상의 문제는 나중에 최적화해 해결할 수 있지만 아키텍처의 결함이 성능을 제한하는 상황이라면 시스템 전체를 다시 작성하지 않고는 해결하기 불가능할 수 있다.`

# item68) 일반적으로 통용되는 명명 규칙을 따르라
자바 언어 명세와 정립되어 있는 명명 규칙을 사용한다면, 다른 개발자들이 사용하기 쉬운 API가 만들어지고 읽고 유지보수하기 쉬워진다.
