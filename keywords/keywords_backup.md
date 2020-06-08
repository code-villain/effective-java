<img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 3. 18. 오전 12:19:57)

• 의존 객체 주입은 재사용성, 테스트 용이성을 엄청나게 개선해준다.


---
<img src="https://avatars.slack-edge.com/2020-03-27/1018578473235_c54a3abd6a62b582c41d_48.jpg" width="30px"> **윤지수** (2020. 3. 18. 오전 11:58:58)

열거 타입의 싱글턴 (p.25)


---
<img src="https://avatars.slack-edge.com/2020-03-27/1018578473235_c54a3abd6a62b582c41d_48.jpg" width="30px"> **윤지수** (2020. 3. 18. 오전 11:59:16)

WeakHashMap (p.38)


---
<img src="https://avatars.slack-edge.com/2020-03-27/1018578473235_c54a3abd6a62b582c41d_48.jpg" width="30px"> **윤지수** (2020. 3. 18. 오전 11:59:34)

오토박싱 함부로 하지 말 것 (p.34)


---
<img src="https://avatars.slack-edge.com/2020-03-27/1018578473235_c54a3abd6a62b582c41d_48.jpg" width="30px"> **윤지수** (2020. 3. 18. 오후 12:00:45)

재귀적 타입 한정???? (p.20)

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 3. 20. 오전 9:56:01)

재귀적 + 타입 한정 합성어 같은데,

재귀적이란 키워드는 addTopping()에서 builder 자신을 계속 리턴해서 붙은거 같고,

타입 한정은 제네릭으로 제한시켰다는 말인거 같습니다

---
<img src="https://avatars.slack-edge.com/2020-03-27/1018578473235_c54a3abd6a62b582c41d_48.jpg" width="30px"> **윤지수** (2020. 3. 18. 오후 12:02:10)

빌더 타입은 왜 계층적 설계된 클래스와 함께 쓰기 좋은가? (p.19)

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 3. 19. 오후 7:41:42)

예제로 사용된 피자와 이를 상속받은 뉴욕피자 칼초네 피자를 빌터패턴을 안쓰고 구현해보는 걸 해봅시다.

- <img src="https://avatars.slack-edge.com/2020-03-27/1018578473235_c54a3abd6a62b582c41d_48.jpg" width="30px"> **윤지수** (2020. 3. 19. 오후 7:42:37)

넹


---
<img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 3. 18. 오후 9:38:16)

자바빈즈 (페이지15)

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 3. 18. 오후 9:50:09)

<https://ko.wikipedia.org/wiki/자바빈즈>


---
<img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 3. 18. 오후 9:39:11)

Supplier<> (페이지 24)


---
<img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 3. 18. 오후 9:40:18)

Q) 페이지34 예제에 인스턴스가 231개가 만들어 진다는데 왜 231개 일까요? Integer.MAX_VALUE 라면 2,147,483,647개 아닐까요


---
<img src="https://avatars.slack-edge.com/2020-03-16/990341146515_d92b916914008ef26f7b_48.png" width="30px"> **Jaehee** (2020. 3. 18. 오후 10:27:43)

P16 자바빈즈 패턴 객체가 완전히 생성되기 전까지 일관성이 무너진 상태에 놓이게 된다..!!!

---
<img src="https://avatars.slack-edge.com/2020-03-16/990341146515_d92b916914008ef26f7b_48.png" width="30px"> **Jaehee** (2020. 3. 22. 오전 9:09:37)

P52 인스턴스의 논리적 동치성을 검사할 일이 없다

---
<img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 3. 23. 오후 12:50:34)

이유를 찾았읍니다 껄껄


---
<img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 3. 23. 오후 12:50:50)

언넝말해


---
<img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 3. 23. 오후 12:50:54)

231개가 아니라 2^31개였읍니다… ㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋ


---
<img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 3. 23. 오후 12:50:59)

아항


---
<img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 3. 23. 오후 12:51:06)

번역이 잘못한거?


---
<img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 3. 23. 오후 12:51:57)

![image.png](https://files.slack.com/files-pri/T01003247A8-F010KTFPK1V/image.png?t=xoxe-1000104143348-1167940520277-1169528043971-0ed5c57b67aca1b8a64557c068baf582)


---
<img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 3. 23. 오후 12:52:49)

오


---
<img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 3. 23. 오후 12:53:09)

2의 31승은 2147483647이 맞아


---
<img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 3. 23. 오후 12:53:43)

-2^31 - 1 ~ 2^31


---
<img src="https://avatars.slack-edge.com/2020-03-16/990341146515_d92b916914008ef26f7b_48.png" width="30px"> **Jaehee** (2020. 3. 24. 오후 7:49:30)

P66 사람이 직접 작성하는 것보다는 IDE에 맡기는 편이 낫다 - 16페이지나 할애했지만 작성하지 말라는 결론^^

- <img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 3. 24. 오후 11:50:59)

IDE의 equals and hashcode 기능을 간단한 예제에 적용해봤더니, 62~63p에 정리된 사항들이 대부분 적용된 것을 확인할 수 있네요!!

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 3. 25. 오전 9:41:28)

인텔리제이?

- <img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 3. 25. 오전 9:41:40)

네

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 3. 25. 오전 9:42:06)

짱짱맨 AutoValue는 안해봤지

- <img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 3. 25. 오전 9:42:40)

찾아보기는 했는데 클래스 위에 @AutoValue 붙이는거 같더라구여?

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 3. 25. 오전 9:42:48)

롬복같이 쓰는거구나

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 3. 25. 오전 9:49:11)

와 짱텔리제이 미쳤다

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 3. 25. 오전 9:49:36)

성능까지 고려해서 참조타입보다 기본타입 먼저 비교함

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 3. 25. 오전 9:53:27)

찐따 롬복은 이런거 고려안하네

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 3. 25. 오전 9:53:31)

으휴


---
<img src="https://avatars.slack-edge.com/2020-03-16/990341146515_d92b916914008ef26f7b_48.png" width="30px"> **Jaehee** (2020. 3. 24. 오후 8:01:33)

P68 두 인스턴스를 같은 버킷에 담았더라도 - 같은 버킷에 담는다는게 뭐지????!!!!

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 3. 25. 오후 10:44:08)

쉽게 말해 배열의 인덱스라고 생각하시면 됩니다.

- <img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 3. 25. 오후 10:45:39)

![image.png](https://files.slack.com/files-pri/T01003247A8-F010CJCCU3C/image.png?t=xoxe-1000104143348-1167940520277-1169528043971-0ed5c57b67aca1b8a64557c068baf582)

- <img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 3. 25. 오후 10:46:14)

key를 input으로 해서 hash 함수를 돌려서 나온 값이 버킷입니당


---
<img src="https://avatars.slack-edge.com/2020-03-16/990341146515_d92b916914008ef26f7b_48.png" width="30px"> **Jaehee** (2020. 3. 24. 오후 8:23:00)

P75 정적 유틸리티 클래스(아이템4)는 toString 을 제공할 이유가 없다 - 왜??

- <img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 3. 25. 오후 1:29:15)

객체 상태를 가지는 클래스가 아니라서?

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 3. 25. 오후 10:46:03)

정적 유틸리티 클래스는 (출력할만한)값이 없잖소.


---
<img src="https://avatars.slack-edge.com/2020-03-16/990341146515_d92b916914008ef26f7b_48.png" width="30px"> **Jaehee** (2020. 3. 24. 오후 8:49:18)

P86 기본 원칙은 복제 기능은 생성자와 팩터리를 이용하는게 최고 ... 배열만은 ... 합당한 예외 - 그래서 클론을 어디에 쓰냐!!고 생각이 들때쯤 배열에만 추천하며 마무리^^

---
<img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 3. 25. 오후 9:37:22)

페이지71 코드11-4 쓰레드 안정성을 고려해서 hash code를 바로 안쓰고 별개의 변수를 선언했나봐

---
<img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 3. 25. 오후 9:38:29)

페이지77 "cloneable방식은 널리 쓰이고 있어서 잘 알아두는 것이 좋다"


---
<img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 3. 25. 오후 9:40:26)

아이템14 compare시에 - < >를 사용하면 안되는구나


---
<img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 3. 25. 오후 10:53:24)

p52. “본질적으로 고유한 인스턴스“란, 값이 같은 인스턴스는 무조건 1개만 존재하는 클래스를 의미?

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 3. 25. 오후 10:54:57)

얘도 위에서 말한 정적 유틸 클래스 처럼 값이 의미 없고 동작만 하는 객체 클래스를 의미하는듯


---
<img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 3. 25. 오후 10:53:28)

p62. “자신을 구현한 서로 다른 클래스끼리도 비교할 수 있도록 equals 규약을 수정” 했는지를 어떻게 알 수 있지? 여기서의 규약이란 어떤 규약을 말하는 걸까?

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 3. 25. 오후 11:06:09)

List 코드에 equals가 어떻게 되어 있나요?

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 3. 26. 오전 10:03:38)

지금 보니까 List 인터페이스에 equals() 메소드가 선언되어 있고, 어떤식으로 equlas()를 선언해야 하는지 주석으로 적혀있는데 이걸 ‘규약’이라고 보는거 같아요. 실제로 이를 구현한 AbstractList를 보면 이퀄스를 재정의 해두었고 인터페이스에서 주석으로 써둔 방식으로 재정의 해두었네요 호호호


---
<img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 3. 25. 오후 11:08:52)

p85. 코드 13-7 복사 생성자 예제는


```
public Yum(Yum yum) {

String foo = yum.getFoo();

String bar = yum.getBar();

return new Yum(foo, bar);

}
```


대략 이런 방식인걸로 생각하면 ~맞겠죠?~ 틀림

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 3. 25. 오후 11:10:19)

네 그런가봐요. 근데 같은 클래스라면 getter안쓰고 바로 접근 가능해요. 개념적으로 다른 객체라도

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 3. 25. 오후 11:10:41)


```
public Yum(Yum yum) {

String foo = yum.foo;

String bar = yum.bar;

return new Yum(foo, bar);

}
```


- <img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 3. 25. 오후 11:18:25)

어 아니네요

- <img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 3. 25. 오후 11:18:30)

getter 안써도 되는건 맞는데

- <img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 3. 25. 오후 11:18:38)

복사 생성자는

- <img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 3. 25. 오후 11:19:15)


```
public Yum(Yum yum) {

this.foo = yum.foo;

this.bar = yum.bar;

}
```


그냥 이런 애들인가봅니다

- <img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 3. 25. 오후 11:19:49)

제가 처음에 쓴 예제는 컴파일 에러남..

- <img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 3. 25. 오후 11:25:09)

위 예제는 shallow copy고, 객체 참조가 있는 경우엔 deep copy로 이렇게.


```
public class Yum {



private String foo;

private String bar;

private LocalDate startDate;



public Yum(final Yum yum) {

this.foo = yum.foo;

this.bar = yum.bar;

this.startDate = LocalDate.of(yum.startDate.getYear(), yum.startDate.getMonth(), yum.startDate.getDayOfMonth());

}

}
```





---
<img src="https://secure.gravatar.com/avatar/740c8f12b8529b5906b1a7be082a1afa.jpg?s=48&d=https%3A%2F%2Fa.slack-edge.com%2Fdf10d%2Fimg%2Favatars%2Fava_0014-48.png" width="30px"> **김근영** (2020. 3. 28. 오후 12:30:25)

<@U010XKK2LMN> has joined the channel


---
<img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 3. 30. 오후 12:54:19)

p98. “상위 클래스의 메서드를 재정의할 때는 그 접근 수준을 상위 클래스에서보다 좁게 설정할 수 없다”

<https://docs.oracle.com/javase/specs/jls/se7/html/jls-8.html#jls-8.4.8.3> [JLS, 8.4.8.3]

- <img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 3. 30. 오후 12:54:27)

*The access modifier (<https://docs.oracle.com/javase/specs/jls/se7/html/jls-6.html#jls-6.6|§6.6>) of an overriding or hiding method must provide at least as much access as the overridden or hidden method, as follows:*

• *If the overridden or hidden method is `public`, then the overriding or hiding method must be `public`; otherwise, a compile-time error occurs.*

• *If the overridden or hidden method is `protected`, then the overriding or hiding method must be `protected` or `public`; otherwise, a compile-time error occurs.*

• *If the overridden or hidden method has default (package) access, then the overriding or hiding method must _not_ be `private`; otherwise, a compile-time error occurs.*


---
<img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 3. 30. 오후 12:58:05)

p99 세번째 문단. “클래스가 표현하는 *추상 개념을 완성*하는 데 꼭 필요한 구성요소로써의 상수”

이게 무슨 말일까요..??

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 4. 1. 오전 9:48:36)

99페이지에서 계속 하고자 하는 말은 필드를 public으로 노출시키지 말라라는 건데, 중간에 이 얘기는 약간의 예외를 둔다면 정말정말로 `public static final` 을 붙일정도로 분명하고 명확하고 꼭! 필요한 구성요소인 경우는 *어느정도 허용*해 줄 수 있다. 라는 의미인거 같아요

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 4. 1. 오전 9:50:34)

추상 개념이라는 키워드가 확 와닿진 않지만 원서를 보면 좀 도움이 될 수도


---
<img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 3. 30. 오후 1:16:46)

• p99. “필드가 수정될 때 (락 획득 같은) 다른 작업을 할 수 없게 되므로 public 가변 필드를 갖는 클래스는 일반적으로 스레드 안전하지 않다“.

• p102. public 필드가 존재하는 클래스 → “외부에서 필드에 접근할 때 부수 작업을 수행할 수도 없다“.

• p103 마지막 문단. “필드를 읽을 때 부수 작업을 수행할 수 없다는 단점”

‘부수 작업’이란 예를 들어 어떤 것들이 있으며, public 필드에 접근할 때 왜 부수 작업을 수행할 수 없다는 것인지?

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 4. 1. 오전 9:27:04)


```
class Person1 {

public String name;

}



class Person2 {

private String name;



public String getName() {

return this.name;

}

}
```


- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 4. 1. 오전 9:30:02)

이런 예제가 있을 때, 요구사항이 `name은 반드시 소문자로 반환해야 한다.`  라고 변경된다면, Person2에서는 return 시에 name을 소문자로 반환하는 `return this.name.toLowerCase()` 라고 부수작업을 넣을 줄 수 있지만 Person1은 저런 작업을 해줄 수 없음,, 요규사항을 만족시키기 위해서 새로운 메소드 `getLowerCaseName()` 을 만들어 주더라도, 이를 `person.name` 으로 접근하고 있던 모든 클라이언트들이 `person.getLowerCaseName()` 이라는 별도의 API로 접근해야 하는 참사가 발생

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 4. 1. 오전 9:35:59)

99페이지 경우도 프로퍼티 메서드에 설정하는 `synchronized` 를 말하는 것 같음

- <img src="https://avatars.slack-edge.com/2020-03-15/1002431586407_ca2faf9276742c005ef6_48.jpg" width="30px"> **JDragon** (2020. 4. 1. 오전 9:58:10)

필드를 읽게 안하고. 게터같은걸로 읽게 하면 로직을 추가할 수 있어서 라고 메모 해놨네

- <img src="https://avatars.slack-edge.com/2020-03-16/990341146515_d92b916914008ef26f7b_48.png" width="30px"> **Jaehee** (2020. 4. 1. 오후 10:57:18)

메모는 누가한거야?? 

- <img src="https://avatars.slack-edge.com/2020-03-15/1002431586407_ca2faf9276742c005ef6_48.jpg" width="30px"> **JDragon** (2020. 4. 1. 오후 11:43:53)

내가 나에게

- <img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 4. 2. 오전 12:31:30)

ㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋ

- <img src="https://avatars.slack-edge.com/2020-03-15/1002431586407_ca2faf9276742c005ef6_48.jpg" width="30px"> **JDragon** (2020. 4. 2. 오전 12:57:04)

부수설명이 부족했군 크흠


---
<img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 3. 30. 오후 2:14:05)

페이지 97 `자바는 정보 은닉을 위한 다양한 장치를 제공한다.` -> 접근 제어자 말고 또 무슨 장치가 있지?


---
<img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 3. 30. 오후 2:15:13)

페이지 97 `톱레벨 클래스와 인터페이스에 부여할 수 있는 접근 수준은 package-private ...` -> 인터페이스에 패키지 접근제어자가 안되지 않습니까?


---
<img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 3. 30. 오후 2:27:51)

페이지 99~100 소개된 2가지 해결책 모두다. Thing배열은 안전하지만 Thing 값을 수정하게 되는 위험이 있으니 딥카피를 하는게 좋을거 같아요.


---
<img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 3. 30. 오후 2:28:00)

페이지 100 자바9의 모듈 시스템


---
<img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 3. 30. 오후 2:29:29)

페이지 111 중간 `만약 신뢰할 수 없는 클라이언트로부터 BigInteger나 ..` 어떤 시나리오가 있을까 도저히 감이 안잡히네.. 같이 코드를 공유하지만 믿을수 없는 클라이언트라..

- <img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 4. 1. 오전 1:50:22)

어떤 객체에서 파라미터로 받은 BigInteger나 BigDecimal 객체의 특정 메서드들이 재정의되어 있어서 예상과는 전혀 다르게 동작한다면 보안상 위험할 수 있다는 말 아닐까요? 가령 원래 BigInteger의 `pow(int exponent)` 메서드는 꽤나 복잡한데 파라미터로 들어온 BigInteger 객체는 사실 pow 메서드가 전혀 엉뚱하게 재정의되어 있을 수 있으니…

그래서 파라미터를 받아서 방어적 복사를 통해 새 인스턴스를 만드는게 안전하다는 말인듯 합니다.

- <img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 4. 1. 오전 9:36:10)

지금 다시 보니 요지는 "같은 애플리케이션에 존재하는 코드끼리의 협력인데 신뢰할 수 없는 경우가 언제 생긴다는 것인가?"인 것 같네요...

어쨌든 결론은 애플리케이션의 규모가 커질수록 잘못될 여지가 생길 수 있으니 안전하게 방어적 복사를 하라는 말 아닐까요?

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 4. 1. 오전 9:42:42)

직장동료를 의심하라는 말일까요

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 4. 1. 오전 9:42:51)

:evildaram:

- <img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 4. 1. 오전 9:44:09)

그것도 하나의 케이스가 될수 있지 않을까요? 예를 들어 레이어별로 개발 역할을 나눴는데 인자를 넣어주는 쪽에서 이상하게 재정의한 객체를 넣어줄수도 있고...

- <img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 4. 1. 오전 9:48:05)

앞에서 봤던 아이템 어딘가에서 클라이언트는 악의적이고 뭔가 이상한 짓을 하려고 안달난 놈이라고 가정하고 API를 만들어야 한다.. 뭐 이런 얘기 했던거 같은데...


---
<img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 3. 30. 오후 2:30:14)

페이지 112 `다른 합당한 이유가 없다면 모든 필드느 private final이어야 한다.`


---
<img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 4. 1. 오전 1:15:33)

p110. “원하는 객체를 완성하기까지의 단계가 많고”

=> “한 객체를 생성할 때 복잡한 과정을 거치는 경우“를 의미하는 듯?


---
<img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 4. 1. 오전 1:15:50)

p110. BigInteger에서의 “가변 동반 클래스“란 아마도 `UnsafeHolder`를 의미하는 듯 한데, private class인데 책에서는 package-private이라고 하네요?

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 4. 1. 오전 10:01:42)


```
MutableBigInteger
```


를 말하는거 같아요


---
<img src="https://secure.gravatar.com/avatar/740c8f12b8529b5906b1a7be082a1afa.jpg?s=48&d=https%3A%2F%2Fa.slack-edge.com%2Fdf10d%2Fimg%2Favatars%2Fava_0014-48.png" width="30px"> **김근영** (2020. 4. 1. 오후 6:06:26)

p100. "클래스에서 public static final 배열 필드를 두거나 이 필드를 반환하는 접근자 메서드를 제공해서는 안된다." 이 부분에 배열 뿐만아니라 컬렉션 객체에 대해 setter를 닫아두고 getter를 열어두는 것 또한 불변성을 위반하는 방법인 것 같습니다. 컬렉션 객체 또한 접근자를 통해 의도치 않은 수정이 일어날 여지가 있으니 불변객체로 만들기 위해서는 아얘 접근자 메소드도 제공하지 않고 캡슐화된 메소드를 통해 의도하고자 하는 연산을 진행하는 방향이 바람직할거 같아요

- <img src="https://avatars.slack-edge.com/2020-03-15/1002431586407_ca2faf9276742c005ef6_48.jpg" width="30px"> **JDragon** (2020. 4. 1. 오후 6:24:20)


```
List<Order> orders = Arrays.asList( ~~~ );

orders.get(1).cancelDelivery();
```


이런식으로 Order 객체를 가져온 후에 Order 객체의 상태를 변화시키는 수정자를  무분별하게 호출할 우려가 있기 때문에 아예 접근자 메서드도 제공을 하지 말자는 건가용?

- <img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 4. 1. 오후 7:36:11)

달리 말하면 컬렉션을 wrapping하는 일급 컬렉션 객체를 만들고 캡슐화된 public 메서드를 제공함으로써 불변을 보장하자 라는 말인거죠?

- <img src="https://avatars.slack-edge.com/2020-03-15/1002431586407_ca2faf9276742c005ef6_48.jpg" width="30px"> **JDragon** (2020. 4. 1. 오후 11:04:05)

뢥핑~ 응 맞엉.


---
<img src="https://avatars.slack-edge.com/2020-03-16/990341146515_d92b916914008ef26f7b_48.png" width="30px"> **Jaehee** (2020. 4. 1. 오후 10:39:30)

P99 ‘public static final’ ... ‘다른 객체를 참조하지는 못하지만 침조된 객체 자체는 수정될 수 있으니’


---
<img src="https://avatars.slack-edge.com/2020-03-16/990341146515_d92b916914008ef26f7b_48.png" width="30px"> **Jaehee** (2020. 4. 1. 오후 10:48:19)

P100 추억의 `clone()` 꼭 배열한테만 쓰기

- <img src="https://avatars.slack-edge.com/2020-03-15/1002431586407_ca2faf9276742c005ef6_48.jpg" width="30px"> **JDragon** (2020. 4. 1. 오후 11:02:43)

추억 ㅋㅋ


---
<img src="https://avatars.slack-edge.com/2020-03-27/1018578473235_c54a3abd6a62b582c41d_48.jpg" width="30px"> **윤지수** (2020. 4. 1. 오후 11:15:27)

p97 패키지 외부에서 쓸 이유가 없다면 package-private 선언하자  (package-private 이 뭔가요)

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 4. 1. 오후 11:24:36)

패키지 접근자요.


---
<img src="https://avatars.slack-edge.com/2020-03-27/1018578473235_c54a3abd6a62b582c41d_48.jpg" width="30px"> **윤지수** (2020. 4. 1. 오후 11:18:00)

p100 모듈은 자신에 속하는 패키지 중 공개 (export)할 것들을 (관례상 module-info.java 파일에) 선언한다 . protected 혹은 public 멤버라도 해당 패키지를 공개하지 않았다면 모률 외부에서는 접근할 수 없다. (자바 9에서 추가된 모듈이란 건 뭐지?)


---
<img src="https://avatars.slack-edge.com/2020-03-27/1018578473235_c54a3abd6a62b582c41d_48.jpg" width="30px"> **윤지수** (2020. 4. 1. 오후 11:19:42)

p107 이처럼 피 연산자에 함수를 적용해 그 결과를 반환하지만, 피연산자 자체는 그대로인 프로그래밍 패턴을 함수형 프로그래밍이라 한다. (예제로 나온 코드가 왜 함수형 프로그래밍인가)

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 4. 1. 오후 11:26:57)

예제코드에 메서드들은 인풋이 같다면 10억번을 호출해도  같은 아웃풋을 반환하지요,

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 4. 1. 오후 11:27:07)

그것은 함수형!


---
<img src="https://avatars.slack-edge.com/2020-03-15/1002431586407_ca2faf9276742c005ef6_48.jpg" width="30px"> **JDragon** (2020. 4. 1. 오후 11:20:23)

P111 어떤 메서드도 객체의 상태 중 외부에 비치는 값을 변경할 수 없다.



외부에 비치는 값의 대표적인 것이 파라미터인데, 메서드 내부에서는  이 값(파라미터)에 대한 수정을 해서는 안 된다는 말. 파라미터로 넘어간 값을 저장(ex:DB)하거나 또는 그 값을 이용해 다른 값을 도출해 리턴하거나, 또는 DB에 조회를 해서 값을 조회할 수는 있지만 그 파라미터 값 자체를 수정해서는 안된다.



메서드에서 외부에 비치는 값을 변경해버리면 클라이언트는 그 메서드 구현부(HOW)를 필수적으로 까봐야만 한다. 파라미터로 썼던 변수를 다른 곳에서 재사용하려고 하면 변경된 값이 적용되어 버리기 때문에 클라이언트 단을 개발하는 개발자는 그 메서드를 반드시 까봐야 한다. 캡슐화와도 관련이 있고 CQRS와도 관련된 개념인 것 같다.

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 4. 1. 오후 11:33:44)

저는 외부의 비치는 값이라는게 객체 값중에서 외부에 노출되는 값으로 이해했는데요. 말씀하시는 파라미터는 외부에서 들어오는 값을 말하는 건가요? 외부에서 들어온 값은 아무리 수정을 해도 메서드가 실행되는 객체 자체의 불변성을 깨트리는게 아니잖아요

- <img src="https://avatars.slack-edge.com/2020-03-15/1002431586407_ca2faf9276742c005ef6_48.jpg" width="30px"> **JDragon** (2020. 4. 1. 오후 11:51:48)

외부에서 들어오는 값 맞음. 아 이 경우에는 메서드를 실행하는 객체 자체의 불변성은 안 깨지겠지만 외부에서 들어온 값을 메서드 내부에서 수정해버리면. 클라이언트 입장에서 객체(파라미터로 사용된 객체를 가지고 있는) 불변성이 깨지는 것이라는 의미에서 씀

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 4. 2. 오전 8:18:46)

클라이언트가 보내는 객체의 불변성을 깨뜨리고 싶지 않다면, 불변객체를 만들어서 보내야 하지 않은까요? 사용하는 다른 객체 로직에 따라 불변성이 깨진다면 너무 불안정한거같아요

- <img src="https://avatars.slack-edge.com/2020-03-15/1002431586407_ca2faf9276742c005ef6_48.jpg" width="30px"> **JDragon** (2020. 4. 2. 오전 9:52:27)

그치 불변객체를 만들어서 보내야지. 위에 말한건 불변성을 깨는 예를 말한거궁

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 4. 2. 오전 10:09:33)

왜 CQRS를 떠올린건지 준비해서 발표해주실수있나요

- <img src="https://avatars.slack-edge.com/2020-03-15/1002431586407_ca2faf9276742c005ef6_48.jpg" width="30px"> **JDragon** (2020. 4. 2. 오전 10:11:22)

명령과 조회를 분리해야 하는데 위에 설명한 예제는 명확히 구분이 되지 않고 뒤섞여 버렸기 때문에 CQRS 가 생각 난겁니다

- <img src="https://avatars.slack-edge.com/2020-03-15/1002431586407_ca2faf9276742c005ef6_48.jpg" width="30px"> **JDragon** (2020. 4. 2. 오전 10:11:25)

발표 못 합 니 다

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 4. 2. 오전 10:11:34)

왜죠!

- <img src="https://avatars.slack-edge.com/2020-03-15/1002431586407_ca2faf9276742c005ef6_48.jpg" width="30px"> **JDragon** (2020. 4. 2. 오전 10:12:00)

준비할 시간이 읍슴돠

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 4. 2. 오전 10:12:14)

아니 뭐 대단하게 하라는게 아니고

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 4. 2. 오전 10:12:16)

한번 소개를

- <img src="https://avatars.slack-edge.com/2020-03-15/1002431586407_ca2faf9276742c005ef6_48.jpg" width="30px"> **JDragon** (2020. 4. 2. 오전 10:12:40)

Let me introuduce

- <img src="https://avatars.slack-edge.com/2020-03-15/1002431586407_ca2faf9276742c005ef6_48.jpg" width="30px"> **JDragon** (2020. 4. 2. 오전 10:19:04)

CQRS 가 명령과 조회의 분리를 뜻하는 건 맞는데 뭔가 다른 차원에서 사용하는 용어네. 저 예는 CQRS 와 상관없는듯. 그냥 불변성을 위반하는 예제라고 하고 넘어가면 될듯


---
<img src="https://avatars.slack-edge.com/2020-03-27/1018578473235_c54a3abd6a62b582c41d_48.jpg" width="30px"> **윤지수** (2020. 4. 1. 오후 11:21:38)

p110 다단계 연산????

- <img src="https://avatars.slack-edge.com/2020-03-15/1002431586407_ca2faf9276742c005ef6_48.jpg" width="30px"> **JDragon** (2020. 4. 1. 오후 11:23:05)

예로 곱하기, 플러스 ,마이너스  연산을 필요로 하는 기능이 있으면. 곱하기 하나 하고 값 객체 하나 생성하고. 마이너스 연산하고 객체 하나 생성하고. 플러스 연산하고 객체 생성하고… 이러지 말고 한번에 연산을 해버리고 객체를 하나만 만들자는 말인듯

- <img src="https://avatars.slack-edge.com/2020-03-27/1018578473235_c54a3abd6a62b582c41d_48.jpg" width="30px"> **윤지수** (2020. 4. 1. 오후 11:23:24)

아하~


---
<img src="https://avatars.slack-edge.com/2020-03-27/1018578473235_c54a3abd6a62b582c41d_48.jpg" width="30px"> **윤지수** (2020. 4. 1. 오후 11:22:18)

p114 메서드 호출과 달리 상속은 캡슐화를 깨뜨린다.


---
<img src="https://avatars.slack-edge.com/2020-03-15/1002431586407_ca2faf9276742c005ef6_48.jpg" width="30px"> **JDragon** (2020. 4. 1. 오후 11:37:58)

p114. 메서드 호출과 달리 상속은 캡슐화를 깨뜨린다.



상속은 기능 확장의 용도로 사용하면 좋은 방법이 될 수도 있지만 자식 클래스와 부모 클래스의 결합도를 높여버린다. 왜냐하면 상속을 하게 되면 자식클래스는 부모클래스의 구현에 강하게 의존하게 만들기 때문에~? 자식클래스는 부모클래스의 변경에 취약해진다. 부모클래스의 인터페이스(오퍼레이션?)가 아닌 구현을 변경하더라도 자식클래스는 영향을 받기 쉬운 구조로 된다.  이렇게 되면 캡슐화를 약화시킨다.


---
<img src="https://avatars.slack-edge.com/2020-03-16/990341146515_d92b916914008ef26f7b_48.png" width="30px"> **Jaehee** (2020. 4. 2. 오전 9:28:24)

P106 자신 외에는 내부의 가변컴포넌트에 접근할 수 없도록 한다


---
<img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 4. 3. 오전 9:03:04)

p119 첫번째 문단. "래퍼 객체가 내부 객체에 자기 자신의 참조를 넘기는 경우" ⇒ `InstrumentedSet`의 생성자에서 `super(s)` 부분?


---
<img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 4. 3. 오전 9:03:08)

p120. "가장 심각한 문제는 클라이언트에서 상위 클래스를 직접 수정하여~" ⇒ 그 밑에 문장들을 봤을 때는 '상위 클래스가 다음 릴리즈 때 뭔가 변경이 일어나면 하위 클래스도 덩달아 영향을 받고 불변식이 깨지고 하위 클래스의 사용자까지도 영향을 준다'는 의미로 이해가 됐는데. '클라이언트에서 상위 클래스를 수정'한다는 건 무슨 말이지..?

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 4. 3. 오전 10:16:22)

Properties는 `setProperty(String, String)` 할때 파라미터로 `스트링만` 받도록 설계했는데, 상위 클래스인 HashTable의 메서드를 사용하면 `스트링이외에` 다른 값도 막 넣을 수 있음.



예를들어

`HashTable<Object, Object> myProperties = new Properties();`

클라이언트가 인스턴스 생성을 이렇게 하고,

`myProperties.put(10, 10.0);` 이렇게 HashTable의 `put()` 을 호출하면 String 이외에 타입이 들어감.



아래는 Proeprties와 HashTable 코드를 간소화한 거

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 4. 3. 오전 10:30:21)

`상위클래스를 직접 수정한다` 는 말에 대한 원서를 찾아봐야할듯 약간 발번역 냄새. ‘상위클래스의 메서드를 사용하여 수정한다.’ 로 느낌이 옵니다.


---
<img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 4. 3. 오전 9:31:03)

페이지128 3번째 문단. `구체클래스가 표준 인터페이스를 구현하지 않았는데 상속을 금지하면 사용하기에…` -> 여기서 말하는 표준 인터페이스가 뭐죠..?


---
<img src="https://secure.gravatar.com/avatar/740c8f12b8529b5906b1a7be082a1afa.jpg?s=48&d=https%3A%2F%2Fa.slack-edge.com%2Fdf10d%2Fimg%2Favatars%2Fava_0014-48.png" width="30px"> **김근영** (2020. 4. 8. 오후 7:38:03)

p146. "중첩클래스는 자신을 감싼 바깥 클래스에서만 쓰여야 하며" 굳이 중첩클래스를 써야하는 경우가 있을까요?

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 4. 8. 오후 8:31:30)

필요한 클래스가, 절대적으로 바깥클래스에서만 사용된다면 중첩시키고 접근제어자를 잠궈버려서 시용할 수 있지 않을까요?

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 4. 9. 오후 11:45:03)

![image.png](https://files.slack.com/files-pri/T01003247A8-F011SP973C1/image.png?t=xoxe-1000104143348-1167940520277-1169528043971-0ed5c57b67aca1b8a64557c068baf582)

- <img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 4. 10. 오전 12:40:40)

이 책은 무슨 책인가여

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 4. 10. 오전 9:06:21)

갓 오브 자바

- <img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 4. 10. 오전 9:06:55)

세번째 항목은 좀 사람마다 주관적일수 있을듯요..?

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 4. 10. 오전 9:07:53)

첫번째 항목을 확장시켜서 생각해본다면 납득 될수도?

- <img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 4. 10. 오전 9:09:38)

회사에서 중첩 클래스를 직접 만들어본적이 없는거같네요.. 본적도 별로 없기도 하고

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 4. 10. 오전 9:10:09)

우리회산 짱많은뎀 ㅎㅎ

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 4. 10. 오전 9:10:39)

너무 과도하게 쓰는것 같음


---
<img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 4. 8. 오후 8:40:25)

페이지 147 하단. `더 심각한 문제는 가비지 컬렉션 바깥 클래스의 인스턴스를 수거하지 못하는 메무리 누수가 생길 수 있다는 점이다.`  -> 같이 모각코 하신분 회사 컨벤션중에 하나가 내부 클래스를 만들지 말라였는데, 이유가 ‘원인을 알 수 없는’ 메모리 누수가 계속 발생해서라고 전해들었음. 아마도 이러한 이유가 아닐까 하고 얘기했던 기억이 나요. 그러니까 중첩클래스는 가능한한 정적으로 선언합시다.


---
<img src="https://avatars.slack-edge.com/2020-03-16/990341146515_d92b916914008ef26f7b_48.png" width="30px"> **Jaehee** (2020. 4. 8. 오후 11:09:52)

147 static을 생락하면 바깥 인스턴스로의 숨은 외부 참조를 갖게된다. 


---
<img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 4. 8. 오후 11:14:44)

아이템 26, 28 “Type Erasure(소거)“라는 개념이 낯설어서 찾아보았읍니다.

<https://www.baeldung.com/java-type-erasure>


---
<img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 4. 8. 오후 11:36:18)

p165 밑에서 3번째 줄 오타

“`List<Integer>[]` 인스턴스의 타입은 ~” ➜ `List<String>[]`


---
<img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 4. 9. 오전 9:37:58)

실체화 불가 타입 : `Non-reifiable types are types where information has been removed at compile-time by type erasure`



<https://docs.oracle.com/javase/tutorial/java/generics/nonReifiableVarargsType.html>


---
<img src="https://avatars.slack-edge.com/2020-03-15/1002431586407_ca2faf9276742c005ef6_48.jpg" width="30px"> **JDragon** (2020. 4. 13. 오전 8:51:04)

카프카

- <img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 4. 13. 오전 9:16:25)

카프카 - 변신

- <img src="https://avatars.slack-edge.com/2020-03-15/1002431586407_ca2faf9276742c005ef6_48.jpg" width="30px"> **JDragon** (2020. 4. 13. 오전 9:59:14)

벼어어어어언신?


---
<img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 4. 15. 오후 8:32:15)

페이지 173 힙오염

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 4. 15. 오후 8:42:51)

페이지 191 `매개변수화 타입의 변수가 타입이 다른 객체를 참조하면 힙 오염이 발생한다.`

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 4. 16. 오전 10:03:16)

<https://www.geeksforgeeks.org/what-is-heap-pollution-in-java-and-how-to-resolve-it/>


---
<img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 4. 15. 오후 8:34:30)

페이지 177 항등함수 (identity function)

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 4. 16. 오전 7:21:05)

항등함수: 집합 X의 임의의 원소 x에 대하여 f(x) = x인 함수

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 4. 16. 오전 7:26:51)

프로그래밍에서는 input과 return 값이 같은 function을 말하는 것 같습니다. 어디다가 써먹는 지는 좀 더 찾아 봐야겠네요.


---
<img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 4. 15. 오후 8:35:27)

페이지 177 제네릭 싱글턴 팩토리


---
<img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 4. 15. 오후 8:38:55)

페이지 184 생산자와 소비자의 기준은 뭘까요


---
<img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 4. 15. 오후 8:43:55)

페이지 198 타입 안정 이종 컨테이너


---
<img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 4. 15. 오후 9:46:06)

페이지 173 컴파일타임 vs 런타임

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 4. 17. 오전 9:43:05)

<https://spaghetti-code.tistory.com/35>


---
<img src="https://avatars.slack-edge.com/2020-03-16/990341146515_d92b916914008ef26f7b_48.png" width="30px"> **Jaehee** (2020. 4. 15. 오후 11:52:25)

178 비검사 형변환 경고 


---
<img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 4. 15. 오후 11:52:58)

• p173. 보통의 제네릭 클래스라면 코드 이곳저곳에서 배열을 자주 사용할 것이다. 

그냥 리스트를 쓰면 되는거 아닌가 생각했는데, 그 다음 페이지 설명을 보니 결국 어딘가에서는 배열을 써야만 하고 성능 때문에 의도적으로 배열을 쓰기도 하는군요~


---
<img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 4. 15. 오후 11:53:38)

• p213. 널리 쓰이는 열거 타입은 톱레벨 클래스로 만들고, 특정 톱레벨 클래스에서만 쓰인다면 해당 클래스의 멤버 클래스로 만든다. 

예시로 든 `RoundingMode`가 만약 `BigDecimal`에서만 쓰인다면 `BigDecimal`의 멤버 클래스로 만들 수도 있었는데, 실제로는 다른 곳에서도 유용하게 많이 쓰이니 톱레벨로 되어있다. 뭐 이런 이야기...?


---
<img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 4. 16. 오전 12:51:41)

p216. 빈 HashMap을 만들고 별도의 static 블록에서 `values()`의 리턴값으로 loop을 돌면서 {문자열, 열거타입 상수} 쌍을 맵에 넣는 방식으로도 구현이 가능한데 책에 그런 말은 없네요. 어쨌거나 34-7 예제처럼 스트림을 사용한 형태가 베스트이긴 하네요

- <img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 4. 16. 오전 9:40:22)

before

- <img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 4. 16. 오전 9:40:49)

after


---
<img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 4. 16. 오전 1:06:11)

p222. 대부분 프로그래머는 Enum의 `ordinal()` 메서드를 쓸 일이 없다.


---
<img src="https://avatars.slack-edge.com/2020-03-15/1002431586407_ca2faf9276742c005ef6_48.jpg" width="30px"> **JDragon** (2020. 4. 19. 오후 11:29:25)

이번주는 금요일에 야간작업 예정이어서 참석 못할듯. 그리고 어차피 발표 준비땜시 스터디 준비도 못할듯ㅠㅠ


---
<img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 4. 20. 오전 1:17:10)

p224. (모든 클라이언트가 argument로 특정한 구현체를 건네리라 짐작된다 하더라도) 이왕이면 인터페이스로 받는 게 일반적으로 좋은 습관이다.


---
<img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 4. 20. 오후 11:58:11)

p235. 반면, 특정 연산에서는 EnumSet과 EnumMap을 사용하지 못한다.

=> WHY?

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 4. 21. 오전 10:03:21)

첫번째 방법은 매개변수로 Enum을 받아들이니까 메서드 내부적으로 EnumSet이나 EnumMap을 사용할 수 있지만, 두번째 방법은 컬렉션이니까 사용못한다는 의미 인 것 같아요.

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 4. 21. 오전 10:07:40)

흠 근데 말에 뉘앙스가 한계가 있다는게 아니고 못한다고 하는거 보면 다른얘기 같기도 하고


---
<img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 4. 21. 오후 11:02:05)

p239~240. `RunTests`에서 `m5()` 메서드를 invoke할 때 Exception이 발생하는 원리는? 왜 static이 아니면 Exception이 발생?

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 4. 24. 오전 9:57:31)

static이 아니라 이를 실행할 객체가 별개로 필요한데, 그 객체가 없어요. invoke() 매개변수로 객체를 넣어주면 실행되는데 예제는 null을 넣음


---
<img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 4. 22. 오전 12:28:55)

p248. IDE에서 관련 설정을 활성화해놓으면 `@Override`가 달려있지 않은 메서드가 실제로는 재정의를 했다면 경고를 준다.

=> 인텔리제이에서 이 옵션 어디에 있을까요..


---
<img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 4. 22. 오전 8:31:01)

228쪽 groupingBy 유용해보여요. 이거 몰라서 개삽질하는 코드 많은데

- <img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 4. 22. 오전 9:14:11)

<https://github.com/gyumin-kim/effective-java-3rd/blob/master/src/main/java/chapter06/item37/PrintPlant.java>

- <img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 4. 22. 오전 9:23:12)

근데 인텔리제이에선 분명 1 tab = 4 spaces인데 깃헙에 올리면 indent가 겁나게 길어져버리네요 거의 2 tab

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 4. 22. 오전 9:32:05)

코드가 너무 우아해서 보기만해도 기분좋네요 :blush:

- <img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 4. 22. 오전 9:59:27)

허허 감사합니다

(제 코드인 척)


---
<img src="https://secure.gravatar.com/avatar/740c8f12b8529b5906b1a7be082a1afa.jpg?s=48&d=https%3A%2F%2Fa.slack-edge.com%2Fdf10d%2Fimg%2Favatars%2Fava_0014-48.png" width="30px"> **김근영** (2020. 4. 22. 오후 10:48:14)

p263. 템플릿 메서드  패턴의 매력이 크게 줄었다. 이를 대체하는 현대적인 해법은 같은 효과의 함수객체를 받는 정적팩터리나 생성자를 제공하는 것이다. => 이 문장에 대한 예시가 있을까요 감이 안잡히네요...

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 4. 23. 오전 12:00:49)

어떤 아이템인가요? 3판에는 내용이 없는데

- <img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 4. 24. 오전 12:34:51)

3판은 p263(아이템44)에 있네요. 다음주 내용입니다


---
<img src="https://avatars.slack-edge.com/2020-03-16/990341146515_d92b916914008ef26f7b_48.png" width="30px"> **Jaehee** (2020. 4. 23. 오전 12:01:16)

P249 예를 들어 ObjectOutputStream.writeObject 메서드는.... -> 마커인터페이스가 컴파일타임에 오류를 잡을 수 있는게 장점이라는데 왜 못잡는다는 예시를??? 내가 잘못 이해한건가:thinking_face:

- <img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 4. 23. 오전 12:36:49)

`ObjectOutputStream.writeObject`은 (논리적으로는) 인자로 Serializable을 구현한 객체가 올 것이라고 가정한다… 그러면 당연히 매개변수 타입을 Serializable로 해놨어야 하는데(그럼 Serializable의 구현체가 아닌 객체를 넣으면 컴파일 에러가 날테니), Object로 해버리는 바람에 아무거나 다 넣어도 컴파일 에러가 안난다… 이런 뜻 아닐까요?

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 4. 24. 오전 9:38:20)

마커인터페이스가 못잡는다기 보다는, ObjectOutputStream.writeObject가 오류를 잡을 수 있는 이 장점을 살리지 못했다고 봐야 될 것 같습니다.

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 4. 24. 오전 9:39:30)

글의 흐름상 좀 이상한 예제라곤 생각되네요. 이자바는 이런게 좀 많음. 예외되는 상황이라고 명시적으로 적어주던가.


---
<img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 4. 24. 오전 12:31:26)

p235 하단의 `java.nio.file.LinkOption`이 구현하는 `CopyOption`, `OpenOption`은 마커 인터페이스 (아이템 41)


---
<img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 4. 24. 오전 12:33:03)

p257. `DoubleBinaryOperator`의 자매품으로 `IntBinaryOperator`, `LongBinaryOperator`, `BinaryOperator` 등이 있습니다.


---
<img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 4. 24. 오전 9:36:03)

페이지 261 메서드 참조의 다섯가지 유형은 2번 읽어도 무슨말인지 모르겠어요. :blush:


---
<img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 4. 24. 오후 7:21:47)

페이지 225 `EnumSet의 유일한 단점이라연 (자바 9까지는 아직) 불변 EnumSet을 만들 수 없다는 것이다.` 는 무슨말일까요? 다른 Set은 불변이 되나요?

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 4. 24. 오후 9:04:05)

생각해보니 이건 다른 셋이랑 비교되는게 아니라 비트 필드와의 비교를 말하는거 같아요.


---
<img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 4. 24. 오후 8:12:59)

페이지 258 `람다에서의 this 키워드는 바깥 인스턴스를 가르킨다.` 첨엔 왜그럴까 생각해봤는데, 기능상의 한계가 이나고. 람다 자체가 펑셔널 인터페이스니 다른 필드나 메서드가 없고 결론적으로 this 키워드가 자신을 가르키는데 의미가 없으니 그런거 같아요.


---
<img src="https://avatars.slack-edge.com/2020-03-16/990341146515_d92b916914008ef26f7b_48.png" width="30px"> **Jaehee** (2020. 5. 3. 오후 2:04:44)

p298 아이템49 public과 protected 메서드는 매개변수 값이 잘못됐을 때 던지는 예외를 문서화해아 한다. -> 왜 public 이랑 protected만??

- <img src="https://avatars.slack-edge.com/2020-03-16/990341146515_d92b916914008ef26f7b_48.png" width="30px"> **Jaehee** (2020. 5. 3. 오후 4:56:59)

자답) p300 공개되지 않은 메서드라면 패키지 제작자인 여러분이 메서드가 호출되는 상황을 통제할 수 있다.


---
<img src="https://avatars.slack-edge.com/2020-03-16/990341146515_d92b916914008ef26f7b_48.png" width="30px"> **Jaehee** (2020. 5. 3. 오후 4:55:52)

p300 이 단언문들은 자신이 단언한 조건이 무조건 참이라고 선언한다는 것이다. ->무조건 참이 되는 단언문만 선언하게 된다는 뜻인가? 스스로 해당 메서드를 호출하고 매개변수를 전달하니까?


---
<img src="https://avatars.slack-edge.com/2020-03-16/990341146515_d92b916914008ef26f7b_48.png" width="30px"> **Jaehee** (2020. 5. 5. 오후 3:56:12)

p308 편의메서드?? 약칭메서드??

- <img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 5. 7. 오전 12:17:03)

아마도 메서드 추출을 통해 만든 헬퍼 메서드를 말하는 것 같고, 메서드 추출을 하면 호출하는 쪽에서는 메서드 이름으로 호출만 하면 되니 약칭 메서드(원서에서는 _shorthand_)라고 한것 같슴다

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 5. 7. 오후 11:00:32)

엉클밥 아조씨는 가독성과 유지보수를 위해서 메서드 추출을 권하는 편인데, 조슈아는 조금은 대립된 의견이라고 봐도 될까요?

- <img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 5. 8. 오전 8:35:18)

조슈아는 다만 반복적으로 쓰이는 로직만 추출하라는거 아닐까요?

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 5. 8. 오전 8:36:39)

네 근데 엉클밥은 반복적이지 않더라도 메서드를 추출하고, 그 메서드에게 적절한 ‘이름’을 부여해서 주석없이도 자연스럽게 읽히는 코드를 지향하는거 같은데, 이런 점이 좀 다른것 같아요.

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 5. 8. 오전 8:39:24)

클라이언트 입장에서 너무 많은 public 메서드가 혼란을 준다는거 같은니, 조슈아의 말도 private 메서드인 경우는 말고 public한 메서드만을 말하는거 같네요.

- <img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 5. 8. 오전 8:42:28)

구웃구웃


---
<img src="https://avatars.slack-edge.com/2020-03-16/990341146515_d92b916914008ef26f7b_48.png" width="30px"> **Jaehee** (2020. 5. 5. 오후 4:10:35)

p310 세번째는 앞서의 두 기법을 혼합한 것으로…. 모든 매개변수를 하나로 추상화한 객체를 정의하고 -> 매개변수를 하나로 추상화했다는게 무슨 말인지 모르겠다

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 5. 6. 오후 10:33:48)

2번쨰 방법에서 말한 것 처럼 하나의 객체로 만들라는 거죵.




```
class Card {

int rank;

String suit;

}
```


이런식으로


---
<img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 5. 6. 오후 10:30:15)

아이템55 옵셔날을 사용해야 하는 경우

페이지 328 `즉 반환값이 없을 수도 있음을 API사용자가에게 명확히 알려준다.`

페이지 330 `결과가 없을 수 있으며, 클라이언트가 이 상황을 특별하게 처리해야 한다면 Optional<T>를 반환한다.`



그래서 제생각엔 메서드를 사용하는 클라이언트가 메서드를 만든 사람과 다른 경우에만 의미가 있는 것 같아요. 본인이 만들고 본인이 쓸꺼라면 차라리 NULL을 반환해서 성능상의 이점을 갖는 것이 좋아보임.


---
<img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 5. 6. 오후 11:32:43)

300p. [<http://bit.ly/2NZ1l7u | Asserts>] 를 참고 해보면 “public 메서드에서는 매개변수 checking 목적으로 assertion을 사용하지 마라(Do _not_ use assertions for argument checking in public methods). 상황에 맞는 적절한 Runtime Exception을 던져줘야 하는데(erroneous arguments should result in an appropriate runtime exception) AssertionError는 그렇지 못하기 때문이다.“라고 하는데,

그게 왜 public 메서드에서만 허용되지 않는다는 것인지 잘 이해가 가지 않네요. 적절한 Exception이 던져져야 하는 것은 non-public 메서드에서도 마찬가지 아닌가..?

- <img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 5. 7. 오전 12:09:04)

> *정리*

• 300p line 3: “public이 아닌 메서드라면 assert를 사용해 매개변수 유효성을 검증할 수 있다.”

• 300p 코드 49-2 하단 “이 메서드가 포함된 패키지를 클라이언트가 어떤 식으로 지지고 볶든 상관없다.”

결국 *assert*란, 외부(클라이언트)와는 관련없이, 내가(개발자가) 작성한 코드와 관련한 어떤 가정이 실제로 true인지에 대한 확신을 가지기 위해 사용하는 것으로 이해되네요.

다만 assert를 disable 시켜버리면 assert에 포함된 expression은 아예 무시되기 때문에, argument checking을 assert로 하면 절대 안된다는 듯.


---
<img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 5. 6. 오후 11:33:14)

306p. 배열의 불변 “*뷰*”를 반환하는 방법

= 100p에서 배열을 private으로 만들고 복사본을 반환하는 public 메서드를 추가하는 방법 ?


---
<img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 5. 6. 오후 11:33:45)

310p. 매개변수 목록을 짧게 줄이는 3번째 방법은 빌더 패턴을 응용한 것이라고 했는데, 클라이언트가 setter를 호출해서 필요한 값을 설정한다는 건 무슨 말? 클라이언트는 ~setter~가 아니라 빌더를 호출하고 빌더의 내부에서 유효성 검사를 진행해주는 형태가 맞지 않을지..?

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 5. 7. 오전 9:35:05)

그러게여 맥락상 세터라는 말이 좀 이상하긴 하네요. 그냥 빌더패턴을 쓰라는 말 같은데


---
<img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 5. 6. 오후 11:33:53)

328p. 박성철님 [Java null survival guide] 중 Optional 관련 부분

<https://www.slideshare.net/gyumee/java-null-survival-guide/31?src=clipshare>


---
<img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 5. 7. 오전 9:10:20)

아이템 45 `시퀀스`

페이지 268 `스트림은 데이터 원소의 유한 혹은 무한 시퀀스를 뜻한다.`

페이지 273 `원소들의 시퀀스를 …`



시퀀스라는 키워드를 사용하는데, 무슨 말인지 잘 모르겠네요. 원소들의 추상적 묶음을 얘기하는 걸까요?

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 5. 8. 오전 8:58:54)

페이지 284 `원소 시퀀스, 즉 일련의 원소를 …` 이라고 말하는거 보면 원소들의 묶음정도로 생각해도 될  것 같아요.


---
<img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 5. 8. 오전 9:12:19)

페이지 312 코드 52-1에서 매개변수로 넘겨주는 타입을 Set이나 List로 하면 의도한 대로(?) 작동하긴하네요.


---
<img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 5. 20. 오후 9:44:55)

페이지 346 (마지막 코드) for문에서 종료조건 검사하는게 너무 무겁고 반복적이라고 느꼈을 때 (expensiveComputation처럼) 별도로 변수를 빼는 행위를 고민하다가도 막상 변수선언할려면 한줄 더 추가하게되고 꺼려졌는데 이런기법이 있었네요.


---
<img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 5. 20. 오후 9:50:31)

페이지 348 `foreach문을 사용해도 속도는 그대로다.`  LinkedList 시리즈 라면 향상된 for문이 훨씬 빠르고, arrayList는 오히려 일반 for문이 미세하게 빨라요. ~조슈아님 자바 공부좀 더 해야할듯?~ :blush:

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 5. 20. 오후 10:35:09)

사이즈가 100인 List를 차례대로 탐색해봤는데, ArrayList에 경우 for문이 for-each문에 비해서 1.1배정도 빨리나왔고, LinkedList는 for-each문이 for문에 비해서 8배정도 발리 나왔네요.

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 5. 20. 오후 11:03:01)

근데 linkedlist라도 이터레이터를 사용한다면 속도차이가 없네요. foreach문 자체가 이터레이터를 사용하는거니까 그런의미에서 차이가 없다라고 하신듯


---
<img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 5. 20. 오후 9:55:02)

페이지378 `구현상의 문제는 나중에 최적화해 해결할 수 있지만, 아키텍처의 결함이 성능을 제한하는 상황이라면 시스템 전체를 다시 작성하지 않고는 해결하기 불가능할 수 있다` 설계의 중요성을 말하는것 같아요


---
<img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 5. 20. 오후 9:56:53)

아이템69 `예외는 진짜 예외 상황에만 사용하라` 입사 초기 코드에 예외로 흐름을 제어한 적이 있었는데 반성하겠습니다.


---
<img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 5. 20. 오후 10:59:51)

p390. 검사 예외(checked exception)을 던지면 호출자가 그 예외를 catch로 잡아 처리하거나 더 바깥으로 전파하도록 *강제*하게 된다.

== 검사 예외는 호출자가 try-catch(혹은 try-finally)로 예외를 의무적으로 핸들링해야 하고, 그렇지 않으면 컴파일 에러가 난다. (런타임 예외는 그렇지 않고)



런타임 예외와 에러는 *프로그램에서 잡을 필요가 없거나 혹은 통상적으로는 잡지 말아야 한다*? 왜인지 잘 이해가 가지 않아요… 런타임 예외를 catch하는 코드들을 매우 흔하게 볼 수 있는데…

- <img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 5. 20. 오후 11:14:02)

![image.png](https://files.slack.com/files-pri/T01003247A8-F014PES64Q0/image.png?t=xoxe-1000104143348-1167940520277-1169528043971-0ed5c57b67aca1b8a64557c068baf582)

- <img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 5. 20. 오후 11:15:52)

“복구 가능하다“고 판단할 기준이 뭔지 감이 헷갈리네요… 위 예제에서 filename이 null인 상황도 클라이언트가 다른 string으로 재시도함으로써 복구 가능하다고 볼수도 있는거 아닌가…?


---
<img src="https://avatars.slack-edge.com/2020-03-16/990341146515_d92b916914008ef26f7b_48.png" width="30px"> **Jaehee** (2020. 5. 20. 오후 11:33:22)

P360 코드 61-3 그렇게 기이하진 않은데...


---
<img src="https://avatars.slack-edge.com/2020-03-16/990341146515_d92b916914008ef26f7b_48.png" width="30px"> **Jaehee** (2020. 5. 20. 오후 11:35:32)

코드61-4 끔찍이 느리다! 

얼마나 느린지 내일 해봐야겠다

- <img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 5. 21. 오전 12:58:53)

제 컴에서는 대략 6.5배 느린걸로 나오네요

- <img src="https://avatars.slack-edge.com/2020-03-15/1000835949088_e3d7d263f3f166d5ec3b_48.png" width="30px"> **김규민** (2020. 5. 21. 오전 12:58:56)

끔찍하다


---
<img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 5. 21. 오후 10:37:32)

ThreadLocal

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 5. 22. 오전 9:04:41)

<https://javacan.tistory.com/entry/ThreadLocalUsage|https://javacan.tistory.com/entry/ThreadLocalUsage>


---
<img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 6. 2. 오전 9:08:07)

p413 동시성

p414 동기화, 배타적 실행, 원자적

p420 응답불가, 안전실패

p428 실행자 프레임워크

p430 포크조인

p431 동시성 유틸리티 (실행자, 동시성 컬렉션, 동기화장치) + wait, notify

- <img src="https://avatars.slack-edge.com/2020-03-16/991778703521_3f474e667de9fb01937b_48.gif" width="30px"> **정시윤** (2020. 6. 2. 오전 9:42:33)

• 컴퓨터 프로세스에서 동시성과 동기화 및 병렬 처리의 차이점

<https://presmarymethuen.org/ko/dictionary/what-is-the-difference-between-concurency-and-synchronization-and-parallelism-in-computer-processes/>

- <img src="https://avatars.slack-edge.com/2020-03-16/990341146515_d92b916914008ef26f7b_48.png" width="30px"> **Jaehee** (2020. 6. 2. 오전 9:44:10)

키워드 ㅎㄸ 


---
