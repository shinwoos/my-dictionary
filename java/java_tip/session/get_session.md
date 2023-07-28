## get session

session lib
```java
session.getId() // session ID 값
session.getMaxInactiveInterval() // session의 유효시간
session.isNew() // 새로 생성된 session 인지 과거에 만들어져있고, 클라이언트에서 서버로 sessionid를 요청해서 조회된 session인지 여부 
		    // new session 일 경우 true, 과거에 남아있는 session 일 경우 false
```