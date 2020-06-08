# 2장 객체 생성과 파괴


## 아이템1 생성자 대신 정적 팩터리 메서드를 고려하라

### *정적 팩토리 메서드 패턴 장점*
1. 이름을 가질 수 있다.
2. 호출 될 때마다 인스턴스를 새로 생성하지 않아도 된다.
    - 언제 어느 인스턴스를 살아 있게 할지 통제할 수 있다.
3. 반환 타입의 하위 타입 객체를 반환할 수 있다.
4. 입력 매개변수에 따라 매번 다른 클래스의 객체를 반환할 수 있다.
5. 정적 팩터리 메서드를 작성하는 시점에는 반환할 객체의 클래스가 존재하지 않아도 된다.

### *정적 팩토리 메서드 패턴 단점*
1. 상속 하려면 public 이나 protected 생성자가 필요하기 때문에 정적 팩토리 메서드만 제공하면 하위 클래스를 만들 수 없다.
2. 정적 팩토리 메서드는 프로그래머가 찾기 어렵다.

## 아이템2 생성자에 매개변수가 많다면 빌더를 고려하라.

> 정적 팩토리와 생성자에는 선택적 매개변수가 많을 수록 적절히 대응하기 어렵다.

### *객체 생성 패턴*

1. 점층적 생성자 패턴
    - 필수 생성자, 선택적 매개변수 생성자, 매개변수 전부 받는 생성자 등 매개변수에 따라 생성자를 점차 늘리는 방식
    - 단점
        - 매개변수가 많아지면 클라이언트 코드를 작성하거나 읽기 어렵다.

2. 자바빈즈 패턴
    - 매개변수가 없는 생성자로 객체를 만든 후, setter 메서드들을 호출하여 매개변수 값을 설정하는 방식
    - 단점
        - 객체 하나를 만드려면 메서드를 여러개 호출해야하고, 객체가 완전히 생성되기 전까지는 일관성이 무너진 상태로 놓인다.
        - 클래스를 불변으로 만들 수 없으며 쓰레드 안전성을 얻으려면 추가 작업을 해줘야 한다.

3. **빌더 패턴**
    - 클라이언트는 필요한 객체를 직접 만드는 대신, 필수 매개변수만으로 생성자(혹은 정적 팩터리)를 호출해 빌더 객체를 얻는다. 
    - 빌더 객체가 제공하는 setter 와 비슷한 메서드들로 원하는 선택 매개변수를 설정한다. 
    - 마지막으로 build 메서드를 호출하여 객체를 만든다.
    - 빌더 패턴은 계층적으로 설계된 클래스와 함께 사용하기 좋다.
    - 점층적 생성자보다 클라이언트 코드 가독성이 좋고 자바빈즈보다 안전하다.

## 아이템 3 private 생성자나 열거 타입으로 싱글턴임을 보증하라
> 싱글턴이란 인스턴스를 오직 하나만 생성할 수 있는 클래스를 말한다.

### *클래스를 싱글턴으로 만들면 이를 사용하는 클라이언트를 테스트하기 어렵다.*
- 실글턴 인스턴스를 mock 구현으로 대체할 수 없기 때문

### *싱글턴을 만드는 방법*
1. public 한 static 멤버가 final 필드인 방식
    - 생성자는 private
    - ex. 클래스명.INSTANCE
    - 해당 클래스가 싱글턴임이 API 에 명확히 드러난다.
    - 간결하다

2. 정적 팩터리 메서드를 public static 멤버로 제공한다.
    - API 를 바꾸지 않고도 싱글턴임이 아니게 변경할 수 있다.
    - 정적 팩토리를 제네릭 싱글턴 팩터리로 만들 수 있다.
    - 정적 팩터리의 메서드 참조를 supplier 로 사용할 수 있다.

3. 열거 타입 방식의 싱글턴
    - 대부분 상황에서 원소가 하나뿐인 열거타입이 싱글턴 만드는 가장 좋은 방법이다.
    - 추가 노력 없이 직렬화가 가능하고, 복잡한 직렬화나 리플렉션 공격에도 제2의 인스턴스가 생기는 일을 막아준다.
    - 단, Enum 외의 클래스를 상속해야 한다면 이 방법은 사용할 수 없다.

## 아이템 4 인스턴스화를 막으려거든 private 생성자를 사용하라

- 생성자를 명시하지 않으면 컴파일러가 자동으로 기본생성자를 생성한다. 사용자는 자동생성된건지 구분할 수 없다
- 추상 클래스로 만드는 것으로는 인스턴스화를 막을 수 없다.
- private 생성자를 추가하면 클래스의 인스턴스화를 막을 수 있다.

## 아이템 5 자원을 직접 명시하지 말고 의존 객체 주입을 사용하라

### *인스턴스를 생성할 때 생성자에 필요한 자원을 넣어주는 방식*
- 클래스가 내부적으로 하나 이상의 자원에 의존하고, 그 자원이 클래스 동작에 영향을 준다면 정적 유틸리티 클래스나 싱글턴 방식이 적합하지 않다.
- 필요한 자원을 생성자에 넘겨주는 방식은 클래스의 유연성, 재사용성, 테스트 용이성을 개선해준다.

### *생성자에 자원 팩터리를 넘겨주는 방식*
- 팩터리란 호출할 때마다 특정 타입의 인스턴스를 반복해서 만들어주는 객체
- 팩터리 메서드 패턴
    - 자바 8의 Supplier<`T`>

## 아이템 6 불필요한 객체 생성을 피하라

> 똑같은 기능의 객체를 매번 생성하기보다는 객체 하나를 재사용하는 편이 나을 때가 많다. 재사용은 빠르고 세련되다. 특히 불변 객체는 언제든 재사용할 수 있다.

### *String은 new 생성자로 만들지 않는다.*
- 실행될 대마다 String 인스턴스를 새로 만든다.
    ```
    String s = new String("text");  // 하지 말 것
    ```
- 올바른 예
    ```
    String s = "text";  // 재사용성 보장
    ```
### *인스턴스 생성 비용이 높다면 캐싱하여 사용하라*

- 생성비용이 높은 인스턴스를 정적 초기화하여 캐싱해두고 필요할 때 재사용한다.
- 지연 초기화는 권장하지 않음(코드 복잡, 성능 개선 미미)

## 아이템 7 다 쓴 객체 참조를 해제하라

> 자칫 메모리 관리에 더 이상 신경 쓰지 않아도 된다고 오해할 수 있는데, 절대 사실이 아니다

### *가비지 컬렉션 언어에서는 메모리 누수를 찾기가 아주 까다롭다*
- 객체 참조 하나를 살려두면 가비지 컬렉터는 그 객체뿐 아니라 그 객체가 참조하는 모든 객체를 회수해가지 못한다.
- 해당 참조를 다 썼을 때 null 처리 하면 해결할 수 있다.
    - 객체 참조를 null 처리하는 일은 예외적인 경우여야 한다.
    - 문제상황
        - 배열의 경우 활성영역에 속한 원소들이 사용되고 비활성 영역은 사용되지 않는다.
        - 문제는 카비지 컬렉터는 그 사실을 모른다.
        - 가비지 컬렉터 입장에서는 비활성 영역의 참조 객체들도 유효한 객체이다.
        - 그러므로 비활성 영역이 되는 순간 프로그래머는 null 처리해서 가비지 컬렉터에게 알려야 한다.
- 객체 참조를 캐시해 놓고 잊어버리는 경우 (메모리 누수 주범)
    - 캐시 외부에서 키(key)를 참조하는 동안만 엔트리가 살아있는 캐시가 필요한 상황
    - WeakHashMap 사용하여 다쓴 엔트리를 자동으로 삭제
- 리스너 혹은 콜백
    - 클라이언트가 콜백을 등록만 하고 명확히 해지하지 않는 경우
    - 콜백을 약한 참조로 저장하면 가비지 컬렉터가 즉시 회수해간다.

## 아이템 8 finalizer 와 cleaner 사용을 피하라

### *finalizer 는 예측할 수 없고, 상황에 따라 위험할 수 있어 일반적으로 불필요*

### *cleaner 는 finalizer 보단 덜 위험하지만, 여전히 예측할 수 없고, 느리고, 일반적으로 불필요*

- finalizer 와 cleaner 는 즉시 수행된다는 보장이 없다.
- 제때 실행되어야 하는 작업은 절대 할 수 없다.
- 프로그램 라이프 사이클과 상관없는, 상태를 영구적으로 수정하는 작업에는 절대 둘 다 사용해선 안된다.
- 심각한 성능문제 동반

## 아이템 9 try-finally 보다는 try-with-resources 를 사용하라

> 자바 라이브러리에선 close 메서드를 호출해 직접 닫아줘야 하는 자원이 많다.

### *try-finally*
- 예외가 try 문 finally 문 양쪽 모두에서 발생할 수 있다.
- 두번 째 예외가 첫 번째 예외를 덮어씌워 디버깅을 어렵게 한다.
- close 할 자원이 많을 수록 문제가 일어날 가능성이 크다.

### *try-with-resources*
- AutoClosable를 구현한 라이브러리의 경우 따로 close 메소드를 호출하지 않아도 자동으로 클로징 된다.
- try-finally 문에 비해 코드도 짧고 문제 진단도 편하다.
- 꼭 회수해야 하는 자원을 다룰 경우 try-with-resources를 사용하라.