### 2.1、resultMap标签

基本作用：

* 建立SQL查询结果字段与实体属性的映射关系信息
* 查询的结果集转换为java对象。
* 将结果集中的列与java对象中的属性对应起来并将值填充进去

```sql
<resultMap id="BaseResultMap" type="com.online.charge.platform.student.model.Student">
        <id property="id" column="id" />
        <result column="NAME" property="name" />
        <result column="HOBBY" property="hobby" />
        <result column="MAJOR" property="major" />
        <result column="BIRTHDAY" property="birthday" />
        <result column="AGE" property="age" />

</resultMap>
```

```
<!--查询时resultMap引用该resultMap -->
<select id="selectByPrimaryKey" resultMap="BaseResultMap" parameterType="Object">
    select id,name,hobby,major,birthday,age from student where id=#{id}
</select>
```



