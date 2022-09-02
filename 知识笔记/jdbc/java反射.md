### jvm工作流程
1. 编译
2. 加载
3. 释放
### 双亲委派机制
- 类加载器
  - AppClassLoader 当前应用程序加载器
  - ExtClassLoader 拓展应用程序加载器
  - BootstrapClassLoader 系统应用程序加载器
- 加载机制
  - 先通过BootstrapClassLoader根据类全限定名加载类 如果不存在找拓展应用程序加载器，再找不到就找当前应用程序加载器。如果还找不到就抛异常
- 优势：保证类的单一加载，保证顶级类不被干扰或覆盖
- 补充
  - BootstrapClassLoader 加载类（class文件）的位置  %java_home%/jre/classes/
  - ExtClassLoader 加载类的位置 %java_home%/jre/lib/ext/classes/
### 类加载源码
### jdbc解析
java定义关于数据库连接的一套接口标准，数据库运营商根据jdbc接口，开发类实现java语言与本数据库的连接
### jdbc连接mysql数据库