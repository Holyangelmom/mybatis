### 1.2、insert标签

##### （1）属性介绍

* id：唯一的标识符
* parameterType：传给此语句的参数的全路径名或别名 例:com.test.poso.User

```sql
<insert id="insert" parameterType="Object">
        insert into student    <trim     prefix="("    suffix=")"    suffixOverrides="," >    
    <if test="name != null  "> NAME,  </if>    
    </trim>    <trim     prefix="values("    suffix=")"    suffixOverrides="," >
    <if test="name != null  ">  #{name},  </if>    
    </trim>
</insert>
```



