## develop doc
**처리했던, 또는 학습했던 내용들 정리**

---

📙 [*JAVA*](https://github.com/shinwoos/my-dictionary/blob/master/java/main.md)




📒 [*Java Script*](https://github.com/shinwoos/my-dictionary/blob/master/js/main.md)




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