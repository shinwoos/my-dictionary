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
