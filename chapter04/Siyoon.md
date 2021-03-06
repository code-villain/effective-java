# item15) 클래스와 멤버의 접근 권한을 최소화하라.

`잘 설계된 컴포넌트는 모든 내부 구현을 완벽히 숨겨, 구현과 API를 깔끔히 분리한다.`

## 장점
1. 시스템 개발 속도 향상. (병렬로 개발이 가능하기 때문)
2. 유지보수 비용 절약. (각 컴포넌트 별로 디버깅 가능)
3. 성능 최적화시에 특정 컴포넌트만 최적화하는 방식 사용 가능.

# item16) public 클래스에서는 public 필드가 아닌 접근자 메서드를 사용하라.

### 접근자 메서드
클래스 내부의 필드에 접근하게하는 메서드. 프로퍼티 getter/setter도 대표적인 예제다.

## 장점
클래스 내부 표현 방식을 언제든 바꿀 수 있는 유연성을 얻을 수 있다.
다만 package 클래스나 private 중첩 클래스라면 필드로 바로 접근하는 것이 깔끔하다.

# item17) 변경 가능성을 최소화하라.
변경가능성을 최소화하라는 것은 결국 불변 클래스를 사용하라는 말이다.

### 불변클래스, 불변객체
인스턴스 내부 값을 수정할 수 없는 클래스 (객체)

불변으로 만들기 위한 다섯가지 규칙
1. 객체의 상태를 변경하는 메서드를 제공하지 않는다.
2. 클래스를 확장할 수 없도록 한다. (상속을 금지시킨다.)
3. 모든 필드를 final로 선언한다.
4. 모든 필드를 private로 선언한다.
5. 자신 외에는 내부의 가변 컴포넌트에 접근할 수 없도록 한다.

## 장점
오류가 생길 여지가 적고 안전하다. 근본적으로 스레드에 안전하다.

# item18) 상속보다는 컴포지션을 사용하라

## 상속의 단점
캡슐화를 깨트린다.
1. 상위클래스는 내부 구현이 달라질 수 있으며 그 여파로 하위클래스가 오 작동 할 수 있다.
2. 상위클래스의 메서드가 추가된다면 하위클래스에서 허용되지 않은 기능이 추가될 수 있다.
3. 하위클래스에서 사용하던 메서드 이름이 상위클래스에 추가된다면 오버라이딩 에러가 발생 될 수 있다.

# item19) 상속을 고려해 설계하고 문서화하라. 그러지 않았다면 상속을 금지하라.
`클래스를 상속용으로 설계하려면 엄청난 노력이 들고 그 클래스에 안기는 제약도 상담함을 알앗다. 절대 가볍게 생각하고 정할 문제가 아니다.`

- 아이템 18,19에서 상속의 문제점을 계속 설파하고 있다. 이럼에도 불구하고 상속이 반드시 필요한 경우는 '다형성'이 필요한 경우다. 완벽하게 문서화하고 고려하기 힘들 것 같다면 상속은 최대한 배제하고. '다형성'을 사용하고 싶은 경우만, 그리고 '다형성'을 편하게 사용하기 위해서 중복된 코드를 제거 하는 경우만 상위 클래스로 두자.

# itme20) 추상클래스보다는 인터페이스를 우선하라.
`자바는 단일 상속만 지원하니, 추상클래스 방식은 새로운 타입을 정의하는데 커다란 제약을 안게 되는 셈이다.`

## 그럼에도 불구하고 추상클래스가 필요한 경우
1. 디폴트 메서드로 Object의 메서드들을 제공해서는 안된다. (규약을 제공하는 정도로만 해야함)
2. public이 아닌 정적 멤버를 가질 수 없다. (private 정적 메서드는 가능해짐)
3. 직접 만든 인터페이스가 아니라면 디펄트 메서드를 제공할 수 없다. (그러나 이경우는 상속받은 인터페이스를 구현할 수 있지 않은가?)

# item21) 인터페이스는 구현하는 쪽을 생각해 설계하라

### 디펄트메서드
인터페이스에 선언이 아닌 구현을 만들어 둘 수 있는 '디펄트메서드'가 추가되었다.

장점 : 인터페이스에 새로운 기능이 필요해지면 디펄트메서드로 추가가 가능해졌다. 이전에는 새로운 인터페이스 명세가 나오면 이를 구현한 **모든**클래스들은 이를 다시 구현해서 배포해야 했다. 그렇지 않으면 새로운 인터페이스와의 호환성이 꺠지기 때문이다. 자바의신에서도 디펄트메서드를 하위호환성을 위해서 만들어진 개념이라고 소개했다.

단점: 이는 상속의 단점과 같은 문제를 야기 시킨다. 아무리 고민 하더라도 모든 구현 클래스들을 해치지 않는 디펄트메서드르 작성하기란 어려운 법이기 떄문이다. 그러므로 디펄트메서드의 추가는 더더욱 신중해야 한다.

`핵심은 명백하다. 디폴트 메서드라는 도구가 생겼더라도 인터페이스를 설계할 때는 여전히 세삼한 주의를 기울여야 한다.`

# item22) 인터페이스는 타입을 정의하는 용도로만 사용하라

인터페이스를 `상수`를 담는 방식으로 사용하는 건 안티패턴이다. (상수 인터페이스)

오해할 수 있는게 상수를 담지 말라는 것이 아니다. 인터페이스 명세에 반드시 필요한 상수는 사용해도 좋다. 오롯이 상수를 담기위한 방식으로 사용하지 말아야 한다.

인터페이스는 명세를 알려주는 용도로만 사용해야 한다.

상수 인터페이스는 열거타입 enum이나 인스턴스화를 막은 정적 클래스로써 대체되어야한다.

# item23) 태그 달린 클래스보다는 클래스 계층 구조를 활용하라.

### 태그
여기서 말하는 태그란 '인스턴스의 타입 혹은 의미'를 알려주는 필드를 말한다.

`태그달린 클래스는 장황하고, 오류를 내기 쉽고, 비효율적이다.`

위에서 정의한 태그를 보면 알다싶이, 태그는 인스턴스의 타입을 하나의 필드로써 나타낸다. 비슷한 인스턴스를 구분하고 싶다면 상속을 사용하여서 다형성으로 구분해야한다.

예제는 쉽다고 느껴졌지만 혹시 이런 클래스가 실제로 존재하진 않은지 항상 경계하자.

# item24) 멤버 클래스는 되도록 정적(static)으로 만들라

## 정의

### 중첩 클래스
클래스 안에 정의된 또 다른 클래스다. 중첩클래스는 `정적 멤버 클래스` `(비정적) 멤버 클래스` `익명 클래스` `지역 클래스` 이렇게 네 가지다.

### 멤버 클래스
중첩클래스 중에서 `정적 멤버 클래스` `(비정적) 멤버 클래스`를 말한다. 마치 다른 필드와 메소드 멤버처럼 존재하여서 붙여진 이름 같아.

### 내부 클래스
중첩클래스 중에서  `(비정적) 멤버 클래스` `익명 클래스` `지역 클래스`를 말한다. 정적 멤버 클래스는 바깥 인스턴스와 상관없이 존재할 수 있어서 붙여진 이름이 아닐까 생각한다.

### 정적 멤버 클래스 vs (비정적) 멤버 클래스
정적 멤버 클래스는 외부 클래스의 인스턴스 없이도 생성된다. 반면에 비정적 멤버 클래스는 외부 클래스의 인스턴스로 부터 파생되어서 만들어진다. 그러므로 비정적 멤버 클래스는 자신을 만들어준 인스턴스에 대한 숨은 참조를 갖게된다.

이 숨은 참조가 공간적 시간적 성능 저하를 유발 시킬 수 도 있고, 가장 문제가 되는건 이 숨은 참조로 인하여 외부 클래스 인스턴스가 가비지 컬렉터의 대상이 되지 않을 수 있다.

이러한 단점이 분명하기 때문에 가능한 '멤버 클래스'는 정적으로 만들어야 한다.

(비정적)멤버 클래스의 장점은 외부 인스턴스로의 접근이 가능하다는 것이다. (숨은 외부 참조가 존재하기 떄문에!) 외부 인스턴스의 접근이 반드시 필요하다면 (비정적) 멤버 클래스를 사용해야 하지만 그렇지 않다면 정적 멤버 클래스가 좋다. Map의 Entry는 (비정적) 멤버 클래스로 만들어졌는데, Map 인스턴스의 참조 없이도 정상적으로 동작하기때문에 정적 멤버 클래스로 만들어 졌어애 한다.

# item25) 톱레벨 클래스는 한 파일에 하나만 담으라

## 정의
### 톱레벨 클래스
중첩클래스가 아닌 클래스를 톱레벨 클래스라고 한다.

톱레벨 클래스가 여러가지 인 경우 컴파일 순서의 따라 의도하지 않은 동작을 하게 된다. 





