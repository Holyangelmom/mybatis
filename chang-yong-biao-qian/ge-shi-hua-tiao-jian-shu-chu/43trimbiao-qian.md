### 4.3、trim标签

##### （1）意义

trim标记是一个格式化的标记，主要用于拼接sql的条件语句（前缀、后缀的添加或忽略），可以完成set或者是where标记的功能。

##### （2）属性介绍

* prefix：增加prefix前缀内容
* suffix：增加suffix后缀内容
* prefixOverrides：忽略前缀的内容
* suffixOverrides：忽略后缀的内容

##### （3）实例

update语句

```sql
<update id="updateByPrimaryKey" parameterType="Object">
        update student set 
  <trim  suffixOverrides="," > 
    <if test="name != null  ">
        NAME=#{name},
    </if>
    <if test="hobby != null  ">
        HOBBY=#{hobby},
    </if>
  </trim> where id=#{id}
</update>


如果name和hobby的值都不为空的话，会执行如下语句
update student set NAME='XX',HOBBY='XX' where id='XX'
```

select语句

```sql
<select id="selectByNameOrHobby" resultMap="BaseResultMap">
    select * from student 
    <trim prefix="WHERE" prefixOverrides="AND | OR">
        <if test="name != null and name.length()>0"> AND name=#{name}
        </if>
        <if test="hobby != null and hobby.length()>0"> AND hobby=#{hobby}
        </if>
    </trim>
</select>


如果name和hobby的值都不为空的话，会执行如下语句
select * from user WHERE /*and*/ name = ‘xx’ and hobby= ‘xx’
```



