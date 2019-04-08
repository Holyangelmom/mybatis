### 2.1、resultMap标签

##### （1）基本作用：

* 建立SQL查询结果字段与实体属性的映射关系信息
* 查询的结果集转换为java对象。
* 将结果集中的列与java对象中的属性对应起来并将值填充进去

##### （2）实例

```sql
<resultMap id="resultMap" type="com.student.model.Student">
        <id property="id" column="id" />
        <result column="NAME" property="name" />
        <result column="HOBBY" property="hobby" />
        <result column="MAJOR" property="major" />
        <result column="BIRTHDAY" property="birthday" />
        <result column="AGE" property="age" />
</resultMap>
```

```sql
<!--查询时resultMap引用该resultMap -->
<select id="selectByPrimaryKey" resultMap="resultMap" parameterType="Object">
    select id,name,hobby,major,birthday,age from student where id=#{id}
</select>
```

##### （3）属性介绍

```sql
<resultMap id="resultMap" type="com.student.model.Student">
```

id：该resultMap的标志

type：返回值的类名，此例中返回Studnet类

