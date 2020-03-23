# 2장 객체 생성과 파괴

## 아이템 1. 생성자 대신 정적 팩터리 메서드를 고려하라

- 클래스는 public 생성자 말고도 **정적 팩터리 메서드(static factory method)**를 제공할 수 있다.
- 정적 팩터리 메서드(static factory method)
  - 클래스의 인스턴스를 반환하는 단순한 정적 메서드
  
  ```java
  // 기본 타입인 boolean 값을 받아 Boolean 객체 참조로 변환
  public static Boolean valueOf(boolean b) {
    return b ? Boolean.TRUE : Boolean:FALSE
  }
  ```

### 정적 팩터리 메서드가 생성자보다 좋은 점

1. **이름을 가질 수 있다.**
  - 생성자만으로는 반환될 객체의 특성을 제대로 설명할 수 없지만, 정적 팩터리 메서드는 목적에 맞게 적당한 이름을 지을 수 있다.
  - 한 클래스에 시그니처가 같은 생성자가 여러 개 필요하다면, 생성자를 정적 팩터리 메서드로 바꾸고 각각의 차이를 잘 드러내는 이름을 사용하자.
2. **호출될 때마다 인스턴스를 새로 생성하지는 않아도 된다.**
  - 생성자는 항상 새로운 객체를 생성하며(heap), 캐싱된 인스턴스를 리턴하는 방법은 없다.
  - 불변 클래스 (ex. `Boolean`, `Boolean.valueOf()`)
    - 불필요한 객체 생성을 피할 수 있다.
    - 인스턴스를 미리 만들어 놓거나(`public static final Boolean TRUE = new Boolean(true);`), 새로 생성한 인스턴스를 캐싱하여 재활용
    - 생성 비용이 큰 객체가 자주 요청되는 상황이라면, 성능을 상당히 개선할 수 있다.
  - 인스턴스 통제(instance-controlled) 클래스
    - 언제 어느 인스턴스를 살아 있게 할지를 통제
      - 반복되는 요청에 같은 객체를 반환
    - *값이 같은 인스턴스가 둘 이상 만들어지지 않음을 보장하는 클래스*
3. **반환 타입의 하위 타입 객체를 반환할 수 있는 능력이 있다.**
  - 반환할 객체의 클래스를 자유롭게 선택할 수 있게 한다.
  - 가령 정적 팩터리 메서드의 리턴 타입을 인터페이스로 만들면, 해당 인터페이스의 구현 클래스들을 공개하지 않아도 그 객체를 반환할 수 있다. 따라서 API를 작게 유지할 수 있다.
  (아이템 20. '인터페이스 기반 프레임워크' 참조)
  - 정적 팩터리 메서드를 사용하는 클라이언트는 얻은 객체를 (구현 클래스가 아닌) 인터페이스만으로 다룰 수 있게 된다.
4. **입력 매개변수에 따라 매번 다른 클래스의 객체를 반환할 수 있다.**
  - (반환 타입의 하위 타입이기만 하면) 어떤 타입의 객체를 반환하든 상관 없다.
  - ex) `EnumSet`: 정적 팩터리 메서드인 `noneOf()`는 매개변수의 수에 따라 다른 인스턴스를 반환한다.
  - 클라이언트 입장에서는 어떤 타입의 객체가 리턴되는지 알 필요도 없고 관심도 없다. 그저 반환 타입의 하위 객체이기만 하면 되는 것이다.
5. **정적 팩터리 메서드를 작성하는 시점에는 반환할 객체의 클래스가 존재하지 않아도 된다.**
  - 클라이언트 입장에서는 아직 존재하지 않는 구현체일지라도 정적 팩터리 메서드를 사용할 수 있다.

### 정적 팩터리 메서드의 단점

1. **정적 팩터리 메서드만 제공하면 하위 클래스를 만들 수 없다.**
  - 상속을 하려면 *public*이나 *protected* 생성자가 필요하기 때문이다.
2. **정적 팩터리 메서드는 프로그래머가 찾기 어렵다.**
  - 생성자 대신 정적 팩터리 메서드 방식을 사용하는 클래스를 인스턴스화 하려면, 프로그래머는 해당 메서드의 의미를 파악하는 시간이 필요하다.
  - API 문서를 잘 써놓고, 메서드 이름도 널리 알려진 규약을 따라 짓는 식으로 문제를 완화해야 한다.

### 정적 팩터리 메서드에 흔히 사용하는 명명 방식
| 이름                      | 설명                                                                                                                                                                             |
| ------------------------ |:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
| from                     | 매개변수를 하나 받아서 해당 타입의 인스턴스를 반환하는 형변환 메서드. ex) `Date d = Date.from(instant);`                                                                                         |
| of                       | 여러 매개변수를 받아 적합한 타입의 인스턴스를 반환하는 집계 메서드 ex) `Set<Rank> faceCards = EnumSet.of(JACK, QUEEN, KING);`                                                                   |
| valueOf                  | from과 of의 더 자세한 버전 ex) `BigInteger prime = BigInteger.valueOf(Integer.MAX_VALUE);`                                                                                          |
| instance 혹은 getInstance | (매개변수를 받는다면) 매개변수로 명시한 인스턴스를 반환하지만, 같은 인스턴스임을 보장하지는 않는다. ex) `StackWalker luke = StackWalker.getInstance(options);`                                          |
| create 혹은 newInstance   | instance 혹은 getInstance와 같지만, 매번 새로운 인스턴스를 생성해 반환함을 보장한다. ex) `Object newArray = Array.newInstance(classObject, arrayLen);`                                         |
| getType                  | getInstance와 같으나, 생성할 클래스가 아닌 다른 클래스에 팩터리 메서드를 정의할 때 쓴다. getType의 "Type"은 팩터리 메서드가 반환할 객체의 타입이다. ex) `FileStore fs = Files.getFileStore(path);`           |
| newType                  | newInstance와 같으나, 생성할 클래스가 아닌 다른 클래스에 팩터리 메서드를 정의할 때 쓴다. getType의 "Type"은 팩터리 메서드가 반환할 객체의 타입이다. ex) `BufferedReader br = Files.newBufferedReader(path);` |
| type                     | getType과 newType의 간결한 버전 ex) `List<Complaint> litany = Collections.list(legacyLitany);`                                                                                      |

---

## 아이템 2. 생성자에 매개변수가 많다면 빌더를 고려하라

- 정적 팩터리와 생성자의 제약
  - *선택적 매개변수*가 많을 때 적절히 대응하기 어렵다.
- 선택적 매개변수가 많을 때 활용할 수 있는 대안
  1. 점층적 생성자 패턴(telescoping constructor pattern)
      - 필수 매개변수만 받는 생성자부터 선택 매개변수를 일부 혹은 전부 포함하는 생성자까지 점진적으로 늘려가는 방식
      - 매개변수 개수가 많아지면 클라이언트 코드를 작성하거나 읽기 어렵다.
  2. 자바빈즈 패턴(JavaBeans pattern)
      - 매개변수가 없는 형태로 생성자로 객체를 만든 후, setter들을 호출해 원하는 매개변수의 값을 설정하는 방식
      - 객체 하나를 만들기 위해 여러 개의 setter를 호출해야 하고, 객체가 완전히 생성되기 전까지는 일관성(consistency)이 무너진 상태임
      - 매개변수의 값을 설정하지 않은 채 객체를 생성해도 컴파일 타임에 잡아낼 수 없어서, 버그를 런타임에 인지하게 되고 디버깅 비용을 높인다.
      - 클래스를 불변으로 만들 수 없고, 스레드 안전성을 얻으려면 추가 작업을 해줘야만 한다.
  3. 빌더 패턴(Builder pattern)

### 빌더 패턴

- 점층적 생성자 패턴의 안전성과 자바빈즈 패턴의 가독성을 겸비
- Builder 패턴 사용
    - 클라이언트는 필수 매개변수만으로 생성자(혹은 정적 팩터리)를 호출해 Builder 객체를 얻는다.
    - Builder 객체가 제공하는 일종의 setter 메서드들로 원하는 선택 매개변수들을 설정한다.
    - 매개변수가 없는 build 메서드를 호출해 객체를 얻는다(보통은 불변 객체).
    ```java
    public class NutritionFacts {
    	private final int servingSize;
    	private final int servings;
    	private final int calories;
    	private final int fat;
    	private final int sodium;
    
    	public static class Builder {
    		// 필수 매개변수
    		private final int servingSize;
    		private final int servings;
    
    		// 선택 매개변수 - 기본값으로 초기화한다.
    		private final int calories = 0;
    		private final int fat = 0;
    		private final int sodium = 0;
    
    		public Builder(int servingSize, int servings) {
    			// validate
    			this.servingSize = servingSize;
    			this.servings = servings;
    		}
    
    		public Builder calories(int val) {
    			// validate
    			calories = val;
    			return this;
    		}
    
    		public Builder fat(int val) {
    			// validate
    			fat = val;
    			return this;
    		}
    
    		public Builder sodium(int val) {
    			// validate
    			sodium = val;
    			return this;
    		}
    
    		public NutritionFacts build() 
    			return new NutritionFacts(this);
    		}
    	}
    
    	private NutritionFacts(Builder builder) {
    		// 불변식(invariant) 검사
    		servingSize = builder.servingSize;
    		servings = builder.servings;
    		calories = builder.calories;
    		fat = builder.fat;
    		sodium = builder.sodium;
    	}
    }
    ```
- `NutritionFacts` 클래스는 불변이다.
- Builder의 setter 메서드들은 Builder 자신을 반환하므로, 메서드 연쇄(method chaining) 방식으로 호출할 수 있다.
  ```java
  NutritionFacts cocaCola = new NutritionFacts.Builder(240, 8)
          .calories(100).sodium(35).build();
  ```
- 잘못된 매개변수를 최대한 일찍 발견하려면,
  - Builder의 생성자와 메서드에서 입력 매개변수를 검사
  - build 메서드가 호출하는 생성자에서 여러 매개변수에 걸친 불변식(invariant)을 검사
    - 불특정 클라이언트의 공격에 대비해 불변식을 보장하려면, Builder로부터 매개변수를 복사한 후 해당 객체 필드들도 검사해야 한다.
  - 검사해서 잘못된 점을 발견하면 **어떤 매개변수가 잘못되었는지를 자세히 알려주는 메시지를 담아 IllegalArgumentException**을 던진다.

---

## 아이템 3. private 생성자나 열거 타입으로 싱글턴임을 보장하라

- 싱글턴(singleton)
  - 인스턴스를 오직 하나만 생성할 수 있는 클래스
  - 클래스를 싱글턴으로 만들면, 이를 사용하는 클라이언트를 테스트하기가 어려워질 수 있다. 싱글턴 인스턴스를 mock 객체로 대체할 수 없기 때문이다.
- 싱글턴을 만드는 방식
  - 공통 사항
      - private 생성자
      - public static 멤버를 하나 마련한다(유일한 인스턴스에 접근할 수 있는 수단).
  1. public static 멤버가 final 필드인 방식
      ```java
      public class Elvis {
        public static final Elvis INSTANCE = new Elvis();
        private Elvis() { ... } // Elvis.INSTANCE를 초기화할 때 딱 1번만 호출
      
        public void leaveTheBuilding() { ... }
      }
      ```

      - public이나 protected 생성자가 없으므로, Elvis 클래스가 초기화될 때 만들어진 인스턴스가 전체 시스템에서 하나뿐임이 보장된다.
      - 장점
        - 해당 클래스가 싱글턴임이 API에 명백히 드러난다.
        - 간결하다.
  2. public static 멤버가 정적 팩터리 메서드인 방식
      ```java
      public class Elvis {
        private static final Elvis INSTANCE = new Elvis();
        private Elvis() { ... }
        public static Elvis getInstance() { return INSTANCE; }
      
        public void leaveTheBuilding() { ... }
      }
      ```
      - 장점
        - API를 바꾸지 않고도 싱글턴이 아니게 변경할 수 있다.
        - 원한다면 정적 팩터리를 제네릭 싱글턴 팩터리로 만들 수 있다.
        - 정적 팩터리의 메서드 참조를 공급자(supplier)로 사용할 수 있다.
  3. 원소가 하나인 Enum 타입을 선언하는 것
      ```java
      public enum Elvis {
        INSTANCE;
      
        public void leaveTheBuilding() { ... }
      }
      ```
      - public 필드 방식과 비슷하지만, 더 간결하고, 추가 노력 없이 직렬화할 수 있다.
      - **대부분 상황에서는 원소가 하나뿐인 Enum 타입이 싱글턴을 만드는 가장 좋은 방법**이다.
      - 단, 만들려는 싱글턴이 Enum 외의 클래스를 상속해야 한다면 이 방법은 사용할 수 없다.

---

## 아이템 4. 인스턴스화를 막으려거든 private 생성자를 사용하라

- 정적 멤버(메서드, 필드)만 담은 **정적 유틸리티 클래스**는, 인스턴스화 하지 않으려는 의도로 사용한다.
- 그런데 생성자를 명시하지 않으면, 컴파일러는 자동으로 기본 생성자를 만든다.
  - 클라이언트는 해당 생성자가 자동 생성된 것인지 의도된 것인지 알 수가 없다.
- 추상 클래스로 만들어도 인스턴스화를 막을 수 없다. 해당 클래스의 하위 클래스를 만들어 인스턴스화 할 수 있기 때문이다.
  - 해당 클래스를 상속해서 쓰라는 뜻으로 클라이언트가 오해할 수도 있다.

### 인스턴스화를 막으려면

- private 기본 생성자를 만든다.
    - 상속을 불가능하게 하는 효과도 있다. 하위 클래스가 상위 클래스의 생성자에 접근할 수 없게 되기 때문이다.
- 생성자가 존재하는데 호출할 수는 없는 것이 직관적이지 않을 수 있으니, 적절한 주석을 달아두자.
  ```java
  public class UtilityClass {
    // 기본 생성자가 만들어지는 것을 막는다(인스턴스화 방지용).
    private UtilityClass() {
      throw new AssertionError();
    }
  
    ...
  }
  ```

---

## 아이템 5. 자원을 직접 명시하지 말고 의존 객체 주입을 사용하라

  ```java
  // 정적 유틸리티를 잘못 사용한 예 - 유연하지 않고 테스트하기 어렵다.
  public class SpellChecker {
    private static final Lexicon dictionary = ...;
  
    private SpellChecker() {}
  
    public static boolean isValid(String word) { ... }
    public static List<String> suggestions(String type) { ... }
  }
  ```

  ```java
  // 싱글턴을 잘못 사용한 예 - 유연하지 않고 테스트하기 어렵다.
  public class SpellChecker {
    private final Lexicon dictionary = ...;
  
    private SpellChecker() {}
    public static SpellChecker INSTANCE = new SpellChecker(...);
  
    public boolean isValid(String word) { ... }
    public List<String> suggestions(String type) { ... }
  }
  ```

- 위의 두 방식 모두, dictionary를 단 1가지만 사용한다고 가정한다는 점에서 좋은 방식이 아니다.
- 사용하는 자원에 따라 동작이 달라지는 클래스에는, 정적 유틸리티 클래스나 싱글턴 방식은 적합하지 않다.

---

- 클래스(SpellChecker)가 여러 자원 인스턴스를 지원해야 하며, 클라이언트가 원하는 자원(dictionary)을 사용해야 하는 요구사항
  - 인스턴스를 생성할 때 생성자에 필요한 자원을 넘겨주자
    ```java
    public class SpellChecker {
      private final Lexicon dictionary;
    
      public SpellChecker(Lexicon dictionary) {
        this.dictionary = Objects.requireNonNull(dictionary);
      }
    
      public boolean isValid(String word) { ... }
      public List<String> suggestions(String type) { ... }
    }
    ```
  - 위 예제에서 dictionary가 아닌 다른 자원을 주입해서도 사용할 수 있다.
  - 불변(immutable)을 보장하여 (같은 자원을 사용하려는) 여러 클라이언트가 의존 객체들을 안심하고 공유할 수 있다.
  - 생성자, 정적 팩터리, 빌더 모두에 똑같이 응용할 수 있다.
  - TODO: <모던 자바 인 액션>에서 Supplier 읽고 29p 관련 내용 추가
- 의존성이 수천 개나 되는 큰 프로젝트에서는 코드를 어지럽게 만들기도 하지만, Spring 등의 의존 객체 주입 프레임워크를 사용하면 어지러움을 해소할 수 있다.

---

## 아이템 6. 불필요한 객체 생성을 피하라

### 똑같은 기능의 객체를 매번 생성하기보다는, **객체 하나를 재사용하는 편이 나을 때가 많다**.

- `String s = new String("bikini");`
  - 따라하지 말 것!
  - 실행될 때마다 새로운 String 인스턴스를 새로 만든다.
  - 생성자에 넘겨진 "bikini" 자체가 이 생성자로 만들어내려는 String 객체와 완전히 똑같으므로, 쓸데없는 짓이다.
- `String s = "bikini";`
  - 같은 가상 머신 안에서 이와 똑같은 문자열 리터럴을 사용하는 모든 코드가 같은 String 인스턴스를 재사용한다.

### 정적 팩터리 메서드를 사용해 불필요한 객체 생성을 피할 수 있다

- 생성자 대신 정적 팩터리 메서드를 제공하는 불변 클래스에서는 정적 팩터리 메서드를 사용해서 불필요한 객체 생성을 방지 ([아이템 2]() 참조)
  - ex) `new Boolean(String)` 대신 `Boolean.valueOf(String)` 팩터리 메서드 사용
- 팩터리 메서드는 생성자와는 달리 매번 새로운 객체를 만들지는 않는다.

### 생성 비용이 비싼 객체는 캐싱하여 재사용
  ```java
  static boolean isRomanNumeral(String s) {
    return s.matches("^(?=.)M*(C[MD]|D?C{0,3}"
          + "(X[CL]|L?X{0,3}(I[XV]|V?I{0,3})$");
  ```

- String.matches는 쉬운 방법이지만, 성능이 중요한 상황에서는 반복해 사용하기엔 적합하지 않다.
  - 이 메서드가 내부에서 만드는 regex용 Pattern 인스턴스는 인스턴스 생성 비용이 높은데, 한 번 쓰고 버려져서 곧바로 GC의 대상이 된다.
  - 성능을 개선하려면, 아래와 같이 Pattern 인스턴스를 클래스 초기화(정적 초기화) 과정에서 직접 생성해 캐싱해두고, 나중에 재사용한다.

  ```java
  public class RomanNumerals {
    private static final Pattern ROMAN = Pattern.compile(
          "^(?=.)M*(C[MD]|D?C{0,3}"
          + "(X[CL]|L?X{0,3}(I[XV]|V?I{0,3})$");
  
    static boolean isRomanNumeral(String s) {
      return ROMAN.matcher(s).matched();
    }
  }
  ```

### 박싱된 기본 타입보다는 기본 타입을 사용하고, 의도치 않은 오토 박싱이 숨어들지 않도록 주의하자
  ```java
  private static long sum() {
    Long sum = 0L;
    for (long i = 0; i < Integer.MAX_VALUE; i++)
      sum += i;
  
    return sum;
  }
  ```

- 위 예제는 sum 변수를 long이 아닌 Long으로 선언해서 불필요한 Long 인스턴스가 2^31개나 만들어진다.
- 오토 박싱(auto boxing)
  - 기본 타입과 박싱된 기본 타입을 섞어 쓸 때 자동으로 상호 변환해주는 기술

### 결론

- 무조건 객체 생성을 하지 말라는 것이 아니다.
- 프로그램의 명확성, 간결성, 기능을 위해서 객체를 추가로 생성하는 것이라면 일반적으로 좋은 일이다.
- 아주 무거운 객체가 아니라면, 단순히 객체 생성을 피하고자 나만의 객체 풀(pool)을 만들지는 말자.
  - 일반적으로는 자체 객체 풀은 코드를 헷갈리게 만들고 메모리 사용량을 늘리고 성능을 떨어뜨린다.
  - 요즘 JVM의 가비지 컬렉터는 최적화가 잘 되어 있어서, 가벼운 객체용을 다룰 때는 직접 만든 객체 풀보다 훨씬 빠르다.

---

## 아이템 7. 다 쓴 객체 참조를 해제하라

- Java를 쓴다고 해서 메모리 관리를 신경 쓰지 않아도 되는 것은 아니다.
  ```java
  public class Stack {
    private Object[] elements;
    private int size = 0;
  
    ...
  
    public Object pop() {
      if (size == 0)
        throw new EmptyStackException();
      return elements[--size];
    }
  
    ...
  }
  ```

- 위의 코드를 오래 실행하다보면, **메모리 누수(memory leak)**가 발생할 수 있다.
  - 스택에서 꺼내진 객체들을 GC가 회수하지 않는다.
  - 이 스택이 그 객체들의 '**다 쓴 참조(obsolete reference)**', 즉 **앞으로 다시 쓰지 않을 참조**를 여전히 갖고 있기 때문이다.
- 객체 참조 하나를 살려두면, 가비지 컬렉터는 그 객체뿐 아니라 그 객체가 참조하는 모든 객체들을 회수해가지 못한다.

### 해결책

- 해당 참조를 다 썼을 때 null 처리(참조 해제)하면 된다.
  ```java
  public Object pop() {
    if (size == 0)
      throw new EmptyStackException();
    Object result = elements[--size];
    element[size] = null;
    return result;
  }
  ```
  - null 처리한 참조를 실수로 사용하려 하면 즉시 NPE를 던지며 종료되므로, 에러를 빨리 찾아낼 수 있게 된다는 장점도 있다.
- null 처리는 언제 해야 하는가
  - 어떤 객체가 비활성 영역에 들어가는지 GC는 알 수 없다.
  - 프로그래머는 **비활성 영역이 되는 순간 null 처리를 해서 해당 객체를 더이상 쓰지 않을 것임을 GC에 알려야** 한다.
  - 일반적으로 **자기 메모리를 직접 관리하는 클래스라면, 프로그래머는 항상 메모리 누수에 주의해야 한다**.
  - 단, 객체 처리를 null 처리하는 일은 예외적인 경우여야 한다.

---

## 아이템 8. finalizer와 cleaner 사용을 피하라

- Java 9에서는 finalizer를 deprecated API로 지정하고, cleaner를 그 대안으로 소개했다.
- cleaner는 finalizer보다는 덜 위험하지만, 여전히 예측할 수 없고, 느리고, 일반적으로 불필요하다.
- cleaner는 안전망 역할이나 중요하지 않은 네이티브 자원 회수용으로만 사용하자. 물론 이런 경우라도 불확실성과 성능 저하에 유의해야 한다.

---

## 아이템 9. try-finally보다는 try-with-resources를 사용하라

- close 메서드를 호출해서 자원을 직접 닫아줘야 하는 경우가 있는데, 클라이언트가 실수로 놓치기 쉬워서 예측할 수 없는 성능 문제로 이어지기도 한다.
  ```java
  static void copy(String src, String dst) throws IOException {
    InputStream in = new FileInputStream(src);
    try {
      OutputStream out = FileInputStream(dst);
      try {
        byte[] buf = new byte[BUFFER_SIZE];
        int n;
        while ((n = in.read(buf)) >= 0)
          out.write(buf, 0, n);
      } finally {
        out.close();
      }
    } finally {
      in.close();
    }
  }
  ```
- try-with-resources (Java 7에서 등장)
  ```java
  static void copy(String src, String dst) throws IOException {
    try (InputStream in = new FileInputStream(src);
          OutputStream out = FileInputStream(dst)) {
        byte[] buf = new byte[BUFFER_SIZE];
        int n;
        while ((n = in.read(buf)) >= 0)
          out.write(buf, 0, n);
    }
  }
  ```
  - 실수로 놓치기 쉬운 close 메서드, 마지막에 발생한 예외 외의 다른 예외들에 관한 정보는 남지 않는 문제 등이 해결됨
  - 이 구조를 사용하려면 **해당 자원이 AutoCloseable을 구현**해야 한다.
    - 닫아야 하는 자원을 뜻하는 클래스를 작성한다면, 반드시 AutoCloseable을 구현하자.

---

[↑ 맨 위로]()