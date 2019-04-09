### 4.3、trim标签

##### （1）意义

trim标记是一个格式化的标记，主要用于拼接sql的条件语句（前缀、后缀的添加或忽略），可以完成set或者是where标记的功能。

##### （2）属性介绍

* prefix：增加prefix前缀内容
* suffix：增加suffix后缀内容
* prefixOverrides：忽略前缀的内容
* suffixOverrides：忽略后缀的内容

（3）实例

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
```



