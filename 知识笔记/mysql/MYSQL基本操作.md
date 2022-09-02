## MYSQL 基本操作

1. 概念

  1. 表 叫做 实体、关系
  2. 列 叫做 属性、元组
  3. 行 叫做 对象、

2. 数据库操作

  1. 新建

```sql
  	CREATE DATABASE [IF NOT EXISTS] dbName
  	#设置编码格式
  	DEFAULT CHARACTER SET utf8
  	#设置校验格式
  	DEFAULT COLLATE utf8_bin;
```

  2. 移除

```sql
  	#数据库中的实体一并移除, 实体除了表还有索引，还有别的东西
  	DROP DATABASE [IF NOT EXISTS] dbName
```

3. 数据库管理

   1. 新建
```sql
    #新建
    CREATE TABLE IF NOT EXISTS tableName (
        属性1 数据类型 [约束1][约束2]...,
        属性2 数据类型 [约束1][约束2]...,
        ....
    ) [ENGINE INNODB|MYISAM] #可以手动选择搜索引擎
    # 建议创建完表结构后再创建约束
    
    #例子
    表名：tbldept
    字段	  说明		类型			约束  	备注
    deptno	部门号		 INT	   	   PK        自增列
    dname	部门名称	VARCHAR(50)    UQ
    loc		地址		 VARCHAR(255)
    
    #结构和约束分离(编码推荐)
    CREATE TABLE IF NOT EXISTS tbldept (
    	deptno INT NOT NULL,
        dname  VARCHAR(50),
        loc VARCHAR(255)
    ) ENGINE INNODB;
    
    
    #创建表2
    CREATE TABLE IF EXISTS tblemp (
    	empno INT PRIMARY KEY AUTO_INCREMENT,
        ename VARCHAR(50) NOT NULL,
        egener ENUM('M','F') DEFAULT 'M' NOT NULL,
        eage INT CHECK(eage>=18),
        deptno INT,
        FOREIGN KEY (deptno) REFERENCES tbldept(deptno)
    ) ENGINE INNODB;
    
    
    #单行添加（建议使用）
    INSERT INTO tbldept(deptno,dname,loc) VALUES (10, '生产部', '301');
    
    #全列匹配，可以省略列名
    INSERT INTO tbldept VALUES (10, '生产部', '301');
    
    #自增列 默认值列 NULL值列 可以省略
    INSERT INTO tbldept(deptno) VALUES(40);
    
    #MYSQL5.7 检查约束无效，枚举类型不匹配使用空白填充
    
    #多行添加不建议使用
```
  1. 修改

  	```sql
  	#增加一列
  	ALTER TABLE tbldept ADD ('desc' VARCHAR(255));
  	#移除一列
  	ALTER TABLE tbldept DROP ('desc' VARCHAR(255));
  	```

  3. 截断，删除表中所有数据，保留表结构

```sql
  	#截断
  	TRUNCATE TABLE tableName;
  	#有外键引用的表无法截断, 只要是主表都无法删除
  	#效率比DELETE FROM tableName 高很多
  	#主表中的数据，DELETE可以删除没有引用的数据
```

4. 数据约束管理

  1. 实体完整性

```sql
    #主键
    PRIMARY KEY
    #唯一键
    UNIQUE
```

  2. 域完整性

```sql
  #检查
  CHECK
  #非空
  NOT NULL
  #默认
  DEFAULT
  #枚举
  ENUM
```

  3. 引用完整性

```sql
  #外键
  FOREIGN KEY REFERENCES
```

  4. 自定义完整性

    1. 一般通过表单工具进行验证处理（正则表达式）

  5. 特殊：在MYSQL5.7版本中，域约束条件无效

5. 数据管理

	1. 添加一条数据

	2. 更新一条数据

	3. 删除一条数据

		只要没有外键引用的数据可以删除
---
