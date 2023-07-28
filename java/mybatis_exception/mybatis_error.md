## mybatis error

**spring and boot
The content of element type "mapper" must match "EMPTY"**
<br>
**xml**의 ( or mybatis-confifg.xml ) dtd확인하기. <!DOCTYPE> dtd에서의 mapper에 대한 정보가 없어서 발생하는 문제

```xml

<!DOCTYPE mapper

  PUBLIC "-//mybatis.org//DTD Mapper 3.0//EN"

  "http://mybatis.org/dtd/mybatis-3-mapper.dtd">

```