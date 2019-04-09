### 6.1、sql标签

##### （1）意义

当多种类型的查询语句的查询字段或者查询条件相同时，可以将其定义为常量，方便调用。为求sql结构清晰也可将sql语句分解。



##### （2）实例

```sql
<!-- 查询字段 -->
<sql id="Base_Column_List">
	ID,MAJOR,BIRTHDAY,AGE,NAME,HOBBY
</sql>
```

```sql
<!-- 查询条件 -->
<sql id="Example_Where_Clause">
	where 1=1
	<trim suffixOverrides=","> 
		<if test="id != null and id !=''">
			and id = #{id}
		</if>
		<if test="major != null and major != ''">
			and MAJOR = #{major}
		</if>
		<if test="birthday != null ">
			and BIRTHDAY = #{birthday}
		</if>
		<if test="age != null ">
			and AGE = #{age}
		</if>
		<if test="name != null and name != ''">
			and NAME = #{name}
		</if>
		<if test="hobby != null and hobby != ''">
			and HOBBY = #{hobby}
		</if>            
		<if test="sorting != null">
			order by #{sorting}
		</if>
		<if test="sort!= null  and sort != '' ">
			order by ${sort}   ${order}
		</if>

	</trim>
</sql>
```



