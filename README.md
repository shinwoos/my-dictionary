# my-dictionary
나만의 에러 및 세팅 사전


DB 테스트 코드

```java
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.SQLException;
import java.sql.Statement;

public class Test {
	  public static void main(String[] args) {
	        // TODO Auto-generated method stub

	        try {

	            Connection conn = DriverManager.getConnection("jdbc:mysql://localhost:3306/sampledb?serverTimezone=UTC", 
	                    "root","0000");
	            System.out.println("success");
	            Statement stmt = conn.createStatement();

	        } catch (SQLException ex) {
	            System.out.println("SQLException" + ex);
	        }



	    }

}


```

spring and boot
The content of element type "mapper" must match "EMPTY"
쿼리 작성하는 xml의 ( or mybatis-confifg.xml ) dtd확인하기. <!DOCTYPE> dtd에서의 ampper에 대한 정보가 없어서 발생하는 문제

```xml

<!DOCTYPE mapper

  PUBLIC "-//mybatis.org//DTD Mapper 3.0//EN"

  "http://mybatis.org/dtd/mybatis-3-mapper.dtd">

```

project에서 특정 bean을 찾지 못하는 에러

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
 
 
 jsp 에서 간단한 모달창 스타일 받아오기 및 모달창 생성
```html
	<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery-modal/0.9.1/jquery.modal.min.js"></script>
	<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/jquery-modal/0.9.1/jquery.modal.min.css" />
	
	<td><a href="#ex1" rel="modal:open" id="modal-up" onclick="update(${list.partNo})">수정</a></td>
	
	<div id="ex1" class="modal">
	  <a href="#" rel="modal:close" class="modal-text" onclick="RequestUpdate()">완료</a>
 	 <a href="#" rel="modal:close" class="modal-text" onclick="requestDelete()">삭제</a>
 	 <a href="#" rel="modal:close" class="modal-text">취소</a>
	</div>

```

session lib
```java
session.getId() // session ID 값
session.getMaxInactiveInterval() // session의 유효시간
session.isNew() // 새로 생성된 session 인지 과거에 만들어져있고, 클라이언트에서 서버로 sessionid를 요청해서 조회된 session인지 여부 
		    // new session 일 경우 true, 과거에 남아있는 session 일 경우 false
```


javascript 에서 math.random() 대체 crypto() 사용.

math.random()은 "적절하지 않은 난수값" 이라는 이유로 코드 보안에 걸려 crypto()를 사용해 보안을 강화해야한다.

```javascript

	crypto.getRandomValues(new Uint8Array(1)); // 8비트 랜덤 배열 1개
	crypto.getRandomValues(new Uint8Array(2)); // 8비트 랜덤 배열 2개
	crypto.getRandomValues(new Uint16Array(3)); // 16비트 랜덤 배열 3개
	crypto.getRandomValues(new Uint32Array(4)); // 32비트 랜덤 배열 4개

	crypto.getRandomValues(new Uint32Array(10)).join(''); 32비트 랜덤 배열10개를 1라인으로 출력

	crypto.getRandomValues(new Uint32Array(1))/4294967296 // Math.random() 과 동일한 포맷
```


java eclipse에서 classes folder가 없거나 Qclass 관련 세팅

BUildpath -> Add Folder -> generated-sources 체크를 통해 생성

target -> classes를 못 찾을 경우에
 * maven build -> goal = install 입력 후 실행하면
	- target folder에  classes folder 수동 생성


lombok 라이브러리 의존성 추가했는데 maven 인식 안될때

eclipse folder -> eclipse.ini open 해서 

-javaagent:D:\dev\tools\eclipse-jee-2020-06-R-win32-x86_64\lombok.jar

맨 뒤에 \lombok.jar 추가

<br>
<br>

# 개발환경에 맞는 Spring Profile 설정
spring boot에서 properties 다수로 나뉘었을 때 tomcat에 setting 값

-Dspring.profiles.active=dev //개발 <br>
-Dspring.profiles.active=local //로컬 <br>
-Dspring.profiles.active=prod  //운영 

active=dev 에서 dev는 properties의 name이다.

```java
	 String profile = System.getProperty("spring.profiles.active");

 propertyFile = new File(BASE_PATH, "/WEB-INF/config/setting/"+profile+"_set.config");
 //자바 환경에서 세팅하는 방법 System.getProperty("spring.profiles.active");로 불러옴.

```