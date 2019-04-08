### 3.1、if标签

##### （1）意义

if标签通常用于WHERE语句、UPDATE语句、INSERT语句中，通过判断参数值来决定是否使用某个查询条件、判断是否更新某一个字段、判断是否插入某个字段的值。

##### （2）实例

```sql
<if test="name != null and name != ''">
         and NAME = #{name}
</if>
```



