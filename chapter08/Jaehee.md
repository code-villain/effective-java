# item 49) 매개변수가 유효한지 검사하라

- 메서드와 생성자 대부분은 입력 매개변수의 값이 특정 조건을 만족하기를 바란다. 이런 제약은 반드시 문서화해야 되며 메서드 몸체가 시작되기 전에 검사해야 한다.   
- 오류를 발생한 즉시 잡지 못하면 해당 오류를 감지하기 어려워지고, 감지하더라도 오류의 발생 지점을 찾기 어려워진다.
- 메서드 몸체가 실행되기 전에 매개변수를 확인한다면 잘못된 값이 넘어왔을 때 즉각적이고 깔끔한 방식으로 예외를 던질 수 있다.

## 매개변수 검사를 제대로 하지 못하면 발생하는 문제
    bad: 메서드 실패 + 모호한 예외
    worse: 메서드 실행 + 잘못된 결과를 반환
    worst: 메서드 실행 + 어떤 객체를 이상한 상태로 만들어서 이후에 해당 메서드와 관련 없는 오류 발생 ^*실패 원자성을 어기는 결과^

    ** 실패 원자성: 호출된 메서드가 실패하더라도 해당 객체는 메서드 호출 전 상태를 유지한다.

- public과 protected 메서드는 매개변수 값이 잘못됐을 떄 던지는 예외를 문서화해야 한다. 그 제약을 어겼을 때 발생하는 예외도 함께 기술해야 한다. 

- 클래스 수준 주석: 해당 클래스의 모든 public 메서드에 적용된다

## Java에서 제공하는 방법 
- Java7 java.util.Objects.requireNonNull 편리하게 null 체크
```java 
String a = null;
        Objects.requireNonNull(a, "null입니다");
```
```java 
Exception in thread "main" java.lang.NullPointerException: null입니다
	at java.util.Objects.requireNonNull(Objects.java:228)
	at com.example.java.objects.objects.main(objects.java:10)
```

- Java9 Objects
    checkFromIndexSize, checkFromToIndex, checkIndex 메서드 추가

## 공개되지 않은 메서드
 - 메서드 호출 상황을 통제할 수 있으니까 유효한 값을 넘기도록 보증하고 그렇게 만들어라!      
- 단언문(assert) 사용해서 매개변수 유효성 검증

## 단언문을 사용한 매개변수 유효성 검증
- 이 단언문들은 자신이 단언한 조건이 무조건 참이라고 선언한다.
- 단언문이 일반적인 유효성 검사와 다른점
    1. 실패하면 AssertionError
    2. 런타임에 아무런 효과, 성능 저하가 없다.

- 메서드가 직접 사용하지는 않으나 나중에 쓰기 위해 저장하는 매개변수는 특히 더 신경써서 검사해야 한다. 

## 생성자
- 생성자는 "나중에 쓰려고 저장하는 매개변수의 유효성을 검사하라"는 원칙의 특수한 사례다. 생성자 매개변수의 유효성 검사는 클래스 불변식을 어기는 객체가 만들어지지 않게 하는 데 꼭 필요하다. 

## 매개변수 유효성 검사 시점(메서드 실행 전) 예외
1. 유효성 검사 비용이 지나치게 높거나 비 실용적일 때
2. 계산 과정에서 검사가 수행될 때
    Collections.sort(List) - 비교할 수 없는 객체가 들어있다면 ClassCastException 발생

- 이번 아이템을 "매개변수에 제약을 두는 게 좋다"고 해석해서는 안된다. 메서드는 최대한 범용적으로 설계해야 한다. 


# item 51) 메서드 시그니처를 신중히 설계하라

- 메서드 이름을 신중히 짓자  
    - 애매하면 자바 라이브러리의 API 가이드를 참조
- 편의 메서드??를 너무 많이 만들지 말자
- 매개변수 목록은 짧게 유지하자  
    - 4개 이하가 좋다
    - 같은 타입의 매개변수가 여러 개 연달아 나오는 경우 특히 해롭다  

- 매개변수 목록을 짧게 줄여주는 기술 
    1. 여러 메서드로 쪼갠다.
        - 잘못하면 메서드가 많아질 수 있지만 `직교성(Orthogonality)`을 높여 오히려 메서드 수를 줄여주는 효과도 있다.  
        ( 직교성: "공통점이 없는 기능들이 잘 분리되어 있다" or "기능을 원자적으로 쪼개 제공한다" )
    2. 매개변수 여러개를 묶어주는 도우미 클래스(정적 멤버 클래스)
    3. 객체 생성에 사용한 빌더 패턴을 메서드 호출에 응용?? 

- 매개변수의 타입으로는 클래스보다 인터페이스가 더 낫다
    - 인터페이스 대신 클래스를 사용하면 클라이언트에게 특정 구현체만 사용하도록 제한하는 꼴!
- boolean 보다는 원소 2개짜리 열거 타입이 낫다
    ```java
     public enum TemperatureScale { FAHRENHEIT, CELSIUS } 


# item 52) 다중정의는 신중히 사용하라  

## 1. 다중정의 vs 재정의
```java
public Class CollectionClassifier {
    public static String Classify(Set<?> s) {
        return "집합";
    }
    public static String Classify(List<?> s) {
        return "리스트";
    }
    public static String Classify(Collection<?> s) {
        return "그 외";
    }
    
    public static void main(String[] args) {
        Collection<?>[] collections = {
            new HashSet<String>(),
            new ArrayList<BigInteger>(),
            new HashMap<String, String>().values()
        };
        for (Collection<?> c : collections)
            System.out.println(classify(c));
    }

}
```

- 출력: "그 외" 3회 
- 다중정의(overloading) 된 `classify()` 중 어느 메서드를 호출할지 컴파일 타임에 정해지고 컴파일 타임에 for문 안의 c 는 항상 `Collection<?>` 타입이다.
- 재정의(overriding): 동적으로 선택
  다중정의(overloading): 정적으로 선택

## 2. 다중정의는 헷갈리니까 다른 방법을 추천한다!
### 1) 예제 수정
```java
public static String classify(Collection<?> c) {
    return c instanceof Set ? "집합" :
            c instanceof List ? "리스트" : "그 외";
}
```

### 2) 다중정의가 혼동을 일으키는 상황을 피해야 한다.
    - 매개변수 수가 같은 다중정의는 만들지 말자.

### 3) 다중정의하는 대신 메서드 이름을 다르게 지어주는 방법
- `class ObjectOutputStream`  
    - 메서드마다 다른 이름 writeBoolean(), writeInt(), writeLong()
    - read 메서드와 짝 readBoolean(), readInt(), readLong()

# item 53) 가변인수는 신중히 사용하라  
- 가변인수(varargs) 메서드는 명시한 타입의 인수를 0개 이상 받을 수 있다.
- 인수의 개수 길이로 배열을 생성, 인수들을 배열에 저장해서 메서드에 전달
- 성능에 민감한 상황이라면 가변인수가 걸림돌이 될 수 있다.