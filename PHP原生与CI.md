原生代码 
```
确保开启
1、
xampp--Apache MySQL
Navicate Sublime

2、
原生PHP连接MYSQL（3306）
 打开数据库连接 mysqli_connect
 选择数据库
 操作表
 
【php支持MYSQL/MYSQLI】
【MYSQL语言tsql】
 
database -> table ->列名（类型、大小、主外键）
    一个主键(自增长,not null非空)、多个外键
    （table1、table2  主外键关联）
    
（1）类型：int char varchar text date timestamp blob
    title varchar(8)[内容多少长度多少，最多8]  
          char(8)[固定8个，不管内容多少]
          【知道长度的时候，用char】
    int：null+1 != 1
    
（2）约束：主键约束 外键约束 非空约束not null                         默认值约束default
```

数据库操作
```
增
  insert into 表名(列名,列名...) values(值,值...)
删
  delete from 表名
  delete from 表名 where 条件
改
  update 表名 set 列名=值,列名=值 where 条件
查
  select * from 表名
  select * from 表名 where 条件(可用逻辑运算符)
//返回结果集(空结果集/多行、一行)
//result()返回多行
//row()返回一行

```

ci
```
application -> controllers -> 首字母大写.php
```
CI配置
```
(1).htaccess放到根目录下
(2)config/autoload.php url/database/session
   config/config.php--evcryption_key
(3)config/databaser.php
```
```
user(uid,uname,pass,flag,header)
blog(bid,title,content,ntime,hits,uid)
```
切内容
```
    iconv_substr(内容,从第几个开始,切几个)......;
```
切割
```
//uri->segment
//segment(1)  -> 控制器名c
//segment(2)  -> 方法名f
$this->uri->segment(第几段);
```
接数据
```
get   $this->input->get();
post  $this->input->post();
delete
input
```
