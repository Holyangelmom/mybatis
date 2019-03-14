# 模糊查询字符串拼接

### 1、使用concat方法

where name like concat\(concat\('%',\#{name}\),'%'\)

### 2、动态sql标签的&lt;bind&gt;标签

```
    <select id="query" resultType="Map">
        <bind name="bindName" value="'%'+name+'%'"></bind>
        select *
        from post
        where 1=1
        <if test="name != null">
        name like #{bindName}
        </if>
     </select>
```

### 3、在java方法中拼接字符串

（略）

### 4、使用“\|\|”

前提需要mybatis的upper\(\)或lower\(\)方法

&lt;&gt;

&lt;/&gt;



where name like '%' \|\| upper\(\#{name}\) \|\| '%'

