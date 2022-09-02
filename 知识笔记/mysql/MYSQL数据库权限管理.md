## MYSQL数据库权限管理

### 查看权限

1. 查看可访问的数据库 show databases
2. 切换数据库 use mysql
3. 查看当前数据库的表 show tables
4. 会话权限表 user
  1. 复合主键：ip+用户名
  2. 列举一些权限控制
    1. 权限列
    	1. Select_priv 枚举类型
    	2. account_locked 枚举类型
  3. mysql 描述一次会话是通过 ip地址+用户名，管理也是通过会话。
  	 
     **用户名@ip地址 ip地址是登录地点的ip地址**
     
  4. mysql远程登录，mysql -u 用户名 -h 服务器ip地址 -p

---

### 修改权限

1. 锁定账号 ALTER USER 'luzhao'@'127.0.0.1' ACCOUNT LOCK;
2. 解锁账号 ALTER USER 'luzhao'@'127.0.0.1' ACCOUNT UNLOCK;