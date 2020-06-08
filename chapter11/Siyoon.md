# item78) 공유 중인 가변 데이터는 동기화해 사용하라

## 정의
### 공유중인 가변 데이터
여러개의 쓰레드가 접근하여서 데이터를 수정(update)할 수 있는 데이터

### 동기화 (동시성에서의 동기화)
여러개의 쓰레드가 동시에 접근 할 때, 한개의 쓰레드만이 접근할 수 있도록 만드는 일종의 경계.
자바에서는 synchronized 키워드와 { } 를 사용한다.

### 배타적 (Exclusive)
- exclusive  : 독점적인, 전용의
위의 뜻이 더 알맞는다. 왜 어렵게 배타적이라고 쓸까..

- 배타적인 : 다른 것을 제외하고 독점적인 조건에서만 성립하는 것을 표시한다. 배타적인 것.「포함적(inclusive)」과 대비된다.

### 원자성
원자성은 어떤 것이 더 이상 쪼개질 수 없는 성질을 말한다. 어떤 것이 원자성을 가지고 있다면 원자적(atomic)이라고 한다. 어떠한 작업이 실행될때 언제나 완전하게 진행되어 종료되거나, 그럴 수 없는 경우 실행을 하지 않는 경우를 말한다.

## 동기화할때의 장점
1. 배타적 실행을 보장한다.
2. 쓰레드 사이의 안정적인 통신에 꼭 필요하다. 
    - (long과 doible 외의) 자바 변수를 읽고 쓰는 동작은 원자적이기 떄문에, 여러 쓰레드가 같은 변수를 동기화 없이 수정중이더라도, 정상적으로 저장한 값을 읽어온다.
    - 그러나, 어떤 값이 '이미' 수정 되었더라도, 특정쓰레드는 그 사실과 상관없이 이전에 저장되었던 값을 불러 올 수 있다.

## 동기화 처리하기
### 1. synchronized 키워드
동기화를 하기 위해선 **쓰기와 읽기 모두** 동기화처리를 해야한다.
```
...

private static synchronized void requestStop(){
    stopRequested = true;
}

private static synchronized boolean stopRequested() {
    return this.stopRequested;
}
...
```

### 2. volatile 키워드
- volatile : 1. 변덕스러운, 2. 불안한
- volatile을 사용하면 배타적 수행과는 상관없지만 항상 가장 최근에 기록된 값을 읽게 된다. (성능도 synchronized 보다 좋다.)

```
...
private static volatile boolean stopRequested;
...
```

### 3. java.util.concurrent.atomic
- AtomicLong을 사용하면,  synchronized와 같이 배타적 실행도 지원하며 성능도 좋다.
```
...
private static final AtomicLong nextSerialNum = new AtomicLong();
...
```

### 4. 가변데이터를 쓰레드간 공유하지 않느다.
가장 실무에서 많이 쓰이는 방법. 가변데이터는 단일 쓰레드에서만 사용한다.


# item79) 과도한 동기화는 피하라
> 교착상태와 데이터 훼손을 피하려면 동기화 영역 안에서 외계인 메서드를 절대 호출하지 말자. 일반화해 이야기하면, 동기화 영역 안에서의 영역은 최소한으로 줄이자.

# item80) 스레드보다는 실행자, 태스크, 스트림을 애용하라

## 정의
### 실행자 프레임워크 (Executor Framework)
java.util.concurrent 패키지에 있는 실행자 프레임워크는 인터페이스 기반의 유연한 태스크 실행 기능을 담고 있다.
```
ExecutorServie exec = Executors.newSinglethreadExecutor();

exec.execute(runnable); //실핼할 태스크를 넘김
```

### 태스크 (task)
실행자 프레임워크는 '작업 단위'와 '실행 매커니즘'이 분리된다. **'작업 단위'를 나타내는 추상 개념이 태스크**다. 태스크는 Runnable 인터페이스와 Callbalbe 인터페이스가 있다.)

### 포크-조인 (fork-join)
포크/조인 프레임워크 는 병렬화할 수 있는 작업을 재귀적으로 작은 작업으로 분할한 다음에 서브태스크에 각가의 결과를 합쳐서 전체 결과를 만들도록 설계 되어 있다.
divide-and-conquer 알고리즘의 병렬화 버전이라 생각하면 된다.
![fork_join](./img/fork_join.png)

- 이거 전에 자바8인 액션에서 봤던 개념이네!~

## 실행자, 태스크, 스트림을 사용해야 하는 이유
- (백그라운드) 스레드를 '직접' 다룰 경우 안전실패나 응답 불가가 될 여지를 없애는 코드를 추가해야하기 때문에 코드가 길어지게 된다.
- 실행자 프레임워크를 사용할 경우 1~2줄에 코드로 유연하게 구현가능하다.

# item81) wait과 notify보다는 동시성 유틸리티를 애용하라

## 정의
### wait, notify
Object에 기본적으로 내장되어있는 메서드로 동기화 작업에서 사용된다.

|메서드|기능 |비고|
|---|---|---|
|wait|갖고 있던 고유 락을 해제하고, 스레드를 잠들게 한다.|호출하는 스레드가 반드시 고유 락을 갖고 있어야 한다. 다시 말해, synchronized 블록 내에서 호출되어야 한다.|
|notify|잠들어 있던 스레드 중 임의로 하나를 골라 깨운다.|상동|
|notifyAll|호출로 잠들어 있던 스레드 모두 깨운다.|상동|

http://happinessoncode.com/2017/10/05/java-object-wait-and-notify/

### 동시성 유틸리티
java.util.concurrent의 고수준 유틸리티는 세 범주로 나눌 수 있다 바로 실행자 프레임워크, 동시성 컬렉션, 동기화 장치다.

- 실행자 : 아이템 80

- 동시성 컬렉션 : 표준 컬렉션 인터페이스에 동시성을 가미해 구현한 고성능 컬렉션이다. 동시성 컬렉션에서 동시성을 무력화하는건 불가능하며 외부에서 락을 추가로 사용하면 오히려 속도가 느려진다.

- 동기화 장치 : 스레드가 다른 스레드를 기다릴 수 있게 하여, 서루 작업을 조율할 수 있게 해준다. 대표적으로 CountDownLatch, Semaphore가 있다. (wait, notify와 가장 유사한 느낌이 든다!)

## 동시성 유틸리티를 사용해야 하는 이유
wait과 notify는 너무 저수준방식이기 때문에 코드가 지저분하고 길어진다. 동시성 유틸리티는 간편하고 강력하게 동시성을 구현해준다.

# item82) 스레드 안정성 수준을 문서화하라
- API 문서에 synchronized 키워드가 보이더라도 그 메서드는 스레드 안전하다고 볼 수 없다. API 문서느 구현 이슈 일뿐 API 속하지 않는다.
- 멀티쓰레드 환경에서도 API를 안전하게 사용하게 하려면 클래스가 지원하는 스레드 안정성 수준을 정확히 명시해야 한다.





