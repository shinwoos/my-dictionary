## project에서 특정 bean을 찾지 못하는 에러


Description:

Failed BoardDao in BoardService required a bean of type ' ** ' that could not be found.

Action:

Consider defining a bean of type 'com.spring.board.dao.BoardDao' in your configuration

해결 방법:
Main 클래스에 아래 어노테이션을 설정하여, 찾지 못하는 bean이 존재하는 package를 scan하도록 한다.
```java
@ComponentScan(basePackages = {"찾지 못하는 패키지루트"})

//둘 중 하나 등록하자.
@SpringBootApplication(scanBasePackages = {"찾지 못하는 패키지루트"})
```
 