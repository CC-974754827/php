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
改
查
```

ci
```
application -> controllers -> 首字母大写.php
```
