### 多条件查询
- 针对条件的进行组合处理
- sql语句拼接，在where 1=1 后面直接跟着 and
- 参数替换，定义参数列表记录非空参数，最后通过循环替换。替换位置从1开始

### 事务管理
在jdbc中关闭事务自动提交
connection.setAutoCommit(false);

提交事务
connection.commit();

事务回退
connection.rollback();

- 涉及两条以上的sql更新操作，可能会导致数据不一致，所以就得手动管理事务。


### 联表操作


### 自己的理解
1. 一定要分页。不然大量的内容你无法处理，分页好控制接收。也好处理
2. 尽量不要在数据库上排序（因为排序数量不会变），直接传过来处理就完事了
3. 操作能通过sql完成就通过sql完成，因为你把大量数据传过来再处理成小数据。我还得浪费网络空间来进行大量传输。而且我还得存储。