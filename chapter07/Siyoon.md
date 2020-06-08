# item 42) 익명클래스보다 람다를 사용하라

## 익명클래스보다 람다를 사용해야 하는 이유
자질구레한 코드가 감추어 어떤 동작을 하는지 명확하게 드러난다.

## 람다의 한계
1. 문서화 해야 하는 경우. 람다는 이름이 없으므로 문서화하지 못한다. (이는 익명클래스에도 똑같이 적용되겠군)
2. 코드가 너무 길어지는 경우 (가능한 세줄 안에 끝내자)

## 람다를 사용할 수 없는 경우
1. 함수형 인터페이스가 아닌 경우
2. this 키워드를 사용해야 하는 경우. 람다의 this는 바깥 인스텉스를 가르킨다.
3. 직렬화 해야하는 경우.

# itme 43) 람다보다는 메서드 참조를 사용하라

메서드 참조는 매개변수조차 감추게 된다. 그래서 매개변수가 많은 경우에 메서드 참조를 사용하면 더 간결하게 표현할 수 있다.
만약 메서드 참조보다 람다식이 더 간결한 경우는 메서드 참조 외에 람다를 사용하자. 메서드 참조는 코드를 간결하게 만들기 위함이다.

# item 44) 표준 함수형 인터페이스

## 정의
### 표준 함수형 인터페이스
'함수형 인터페이스'는 (추상) 메서드가 1개뿐인 인터페이스를 말한다. (Single Abstract Method SAM 이라고 불리기도 함)

java.util.function 패키지에 많이 사용될 것이라고 예상된 43개의 함수형 인터페이스가 존재하고, 이를 '표준 함수형 인터페이스'라고 한다.

## (가능한) 표준 함수형 인터페이스를 사용해야하는 이유.
1. 불필요한 API를 줄일 수 있다. (클라이언트나 개발자 입장에서도 다루는 개념의 수가 준다.)
2. 표준 함수형 인터페이스들은 유용한 디펄트 메서드가 내장 되어 있다.

## 표준 함수형 인터페이스를 지양해야 하는 경우.
예를들어 Comparator<T>는 표준 함수형 인터페이스 ToIntBifunction<T, U>와 구조적으로 유사하지만, 
1. '이름'이 좀 더 직관적이다.
2. 이미 많이 쓰이고 있다.
3. 비교자들을 변환하는 과정의 유용한 디펄트 메서드를 갖고 있다.

## 함수형 인터페이스 사용시 주의사항
서로 다른 함수형 인터페이스를 같은 위치의 인수로 받는 메서드들을 다중 정의하지 말자. 클라이언트에게 모호함을 안겨준다.

# item 45) 스트림은 주의해서 사용하라.
스트림 API는 '다수의 데이터(원소)'들을 다루는 방법 중에 하나다.

스트림 존재 이전에 반복문으로 처리 되었던 과정을 스트림으로 변환할 수 있지만, **스트림은 모든 반복문을 대체 할 수 없다.**

스트림을 **적절하게** 사용 한다면 반복문 보다 가독성을 올릴 수 있지만, 오히려 가동성을 해치는 경우도 있다.

## 정의
### 스트림 파이프라인
원소들로 수행하는 연산 단계를 말한다. 스트림은 종단연산, 중간연산으로 나뉜다. 

### 시퀀스?
시퀀스 라는 키워드를 사용하는데 원소들의 묶음? 정도로 이해된다. (정확하지 않음)

## 스트림이 안성맞춤인 경우 :)
1. 원소들을 일관되게 변환한다. (map)
2. 원소들을 필터링한다. (filter)
3. 원소들의 연산을 결합한다. (sum, joining, min, max)
4. 원소들을 컬렉션에 모은다. (collect)
5. 특정 조건을 만족하는 원소를 찾는다. (findFirst)

## 스트림 보다는 반복문을 사용해야 하는 경우

### 함수 객체 (=람다 혹은 메서드 참조)의 한계
스트림 파이프라인에서의 반복되는 계산은 '함수 객체'를 사용하는데 함수객체가 할 수 없는 일들은 다음과 같다.

1. 지역변수를 읽고 수정할 수 없다. 오로지 final이거나 사실상(=로직상) final인 경우만 사용 할 수 있다.
2. return, continue, break를 사용할 수 없다.

### 스트림의 한계
스트림 파이프라인은 한 값을 매핑하고 나면 이전의 값은 잃는 구조를 갖는다. 이전 값들을 사용해야 하는 경우, 혹은 이전값들으 사용해야 성능상의 이점이 있는 경우는 스트림이 적절하지 않다. (메르센 소수)

# item 46) 스트림에서는 부작용 없는 함수를 사용하라

## 정의
### 순수 함수 (부작용이 없는 함수)
순수 함수는 결국 '참조 투명성'을 갖는 '참조 투명함수'를 말하는 것 같다.

> 프로그램 동작의 변경없이 관련 값을 대체할 수 있다면 표현식을 참조 상 투명하다고 할 수 있다. 그 결과, 참조 상 투명한 함수를 평가하게 되면 동일한 인자에 대해 동일한 값을 반환해야 한다. 그러한 함수를 순수 함수라고 부른다. 참조상 투명하지 않은 표현식은 참조상 불투명 하다고 한다. - 위키백관 '참조 투명성'

- 같은 input에 (다른 곳에 영향을 주지 않고) 같은 output을 주는 함수

## 스트림에서 순수 함수를 사용해야 하는 이유
스트림 패러다임의 핵심은 계싼의 일련의 변환으로 재구성 하는 부분이다. 이떄 각 변환 단계는 가능한 이전 단계의 결과를 받아 처리하는 순수 함수여야 한다.

Q) 스트림이 순수 함수를 사용하지 않으면 어떤 문제가 생기는 걸까.. 그리고 스트림에서 순수함수가 아닌 다른 함수를 사용할 수 있나?

# item 47) 반환 타입으로는 스트림보다 컬렉션이 낫다
> API를 작성할 때는 스트림 파이프라인을 사용하는 사람과 반복문(Iterable)에서 쓰려는 사람 모두를 배려해야 한다. 사용자 대부분이 한 방식만 사용할 거라는 그럴싸한 근거가 없다면 말이다.


# item 48) 스트림 병렬화는 주의해서 적용하라
병렬화는 어렵다. 스트림도 마찬가지다.
> 스트림을 잘못 병렬화하면 (응답 불가를 포함해) 성능이 나빠질 뿐만 아니라 결과 자체가 예상 못한 동작이 발생할 수 있다.

## 스트림 병렬화의 장점
스트림 병렬화는 성능의 최적화다. 그러므로 pallalel() 을 사용하여 파이프라인을 병렬화 했다면 그에 대한 효과가 있는지 반드시 테스트 해봐야 한다. 이러한 확신이 없다면 사용하지 않는 것이 낫다.

## 스트림 병렬화를 하면 안되는 경우
- 데이터 소스가 Stream.iterate거나 중간 연산으로 limit를 쓰는 경우
- collect 메서드로 가변 축소(mutable reduction)하는 경우

## 스트림 병렬화가 효과를 보는 경우
- 스트림의 소스가 ArrayList, HashMap, HashSet, Concurrent에ashMap 의 인스턴스거나 배열， int 범위，long 범위일 때
    - 다수의 스레드에 분배하기 좋은 경우
- 기본 타입을 배열을 사용하여 '참조 지역성'이 뛰어난 경우 병렬화하기 좋다. 참조 지역성이란 이웃한 참조들이 메모리에 연속해서 저장되 어 있다는 뜻이다.

- min, max, count, sum 같은 reduction 함수들
- anyMatch, allMaych, noneMatch처럼 조건에 맞으면 바로 반환되는 메서드들

