
### 描述
半自动化 轻量级 持久化框架

### ORM
- 实体类
- OGNL
### 配置文件
### 三大核心类
- SqlSessionFactoryBuilder 类
- SqlSessionFactory 接口
- SqlSesssion 接口

### mybatis缓存
- 默认开启一级缓存。当前会话结束，缓存失效。
- 二级缓存需要手动打开。当前会话结束，缓存不会失效。 在某个接口对应的mapper文件中设置```<setting name="cacheEnabled" value="true"/> ```。
- 二级缓存的表，表被更新后缓存失效。