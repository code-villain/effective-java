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




