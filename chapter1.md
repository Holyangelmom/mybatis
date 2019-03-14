# \#{}和${}的区别

两者都是取值操作符，但有许多不同点。

### （参考文档）

[https://www.cnblogs.com/baizhanshi/p/5778692.html](https://www.cnblogs.com/baizhanshi/p/5778692.html)

### 1、传值

（1）\#将传入的数据都当成字符串，自动对传入的数据加上双引号，例如：order by "id"

（2）$不处理传入的数据，一般用于传入表名、字段名等数据库对象，例如：order by id

### 2、防止sql注入

（1）\#方式能够很大程度防止sql注入

（2）$方式无法防止Sql注入



