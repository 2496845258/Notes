## MYSQL常用函数
### 数学函数
```sql
    #四舍五入, 默认保留到整数部分
    SELECT ROUND(5.1)

    #选择保留的2位小数， -2位小数，就是保留到百位
    SELECT ROUND(5.1, 2)

    #向上圆整
    SELECT CEIL(12.1)

    #向下圆整
    SELECT FLOOR(10.9)

    #随机数 [0, 1) 设值种子为5
    SELECT RAND(5)

    #取模 10 % 3
    SELECT MOD(10, 3)
```
### 字符函数
```sql
    #字符串长度
    SELECT CHAR_LENGTH('hello')

    #字符串截取，数据库中字符串第一个字符的下标为1，这描述从1开始，截取2个
    SELECT SUBSTR('hello', 1, 2)

    #字符转ASCII码
    SELECT ASCII('0')

    #ASCII转字符
    SELECT CHAR(65, using utf8mb4)

    #字符串连接
    SELECT CONCAT('1', 'A', '2')

```
### 日期函数
```sql
    #获取当前系统时间
    SELECT NOW()

    #时间截取
    SELECT YEAR(NOW())
    SELECT MONTH(NOW())
    SELECT DATE(NOW())

    #时间计算
    SELECT DATE_ADD(NOW(), INTERAL 1 DAY);
    SELECT DATE_ADD(NOW(), INTERAL 1 MONTH);
    SELECT DATE_ADD(NOW(), INTERAL -1 DAY);

    #时间截取
    select data_format(now(), '%D')
    select data_format(now(), '%M')
    select data_format(now(), '%Y')

    #时间差
    SELECT DATEDIFF('2022-08-02','2022-08-01')

```
### 转换函数
```sql
    #隐式转换 + 号只会做数字运算，非数字直接无视
    SELECT 1+1
    SELECT 1+'A'+2

```