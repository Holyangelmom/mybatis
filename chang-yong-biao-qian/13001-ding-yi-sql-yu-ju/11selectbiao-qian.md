### 1.1、select标签

##### （1）属性介绍

* id：唯一的标识符.
* parameterType：传给此语句的参数的全路径名或别名 例:com.test.poso.User或user
* resultType：语句返回值类型或别名。注意，如果是集合，那么这里填写的是集合的泛型，而不是集合本身（resultType 与resultMap 不能并用）

```sql
<select id="selectByPrimaryKey" resultMap="BaseResultMap" parameterType="Object">
        select * from student where id=#{id}
</select>
```



