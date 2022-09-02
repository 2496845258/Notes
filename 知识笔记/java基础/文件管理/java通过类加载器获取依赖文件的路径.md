### 通过类加载的位置给全限定名来加载文件
```java
String name = Test.class.getClassLoader().getResource("priv/luzhao/mybatis/resource/mybatis-cfg.xml").toString();
//可能的中文
String path = URLDecoder.decode(name, StandardCharsets.UTF_8).substring(6);
```