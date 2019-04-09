### 4.2、set 标签

##### （1）意义

当update语句中没有使用if标签时，如果有一个参数为null，都会导致错误。如：

```sql
<update id="updateStudent" parameterType="Object">     
    UPDATE STUDENT   
    SET NAME = #{name},   
           MAJOR = #{major},
           HOBBY = #{hobby}
     WHERE ID = #{id};      
</update>
```

当在update语句中使用if标签时，如果最后的if没有执行，则或导致逗号多余错误。使用set标签可以将动态的配置set关键字，和剔除追加到条件末尾的任何不相关的逗号。如：

```sql
<update id="updateStudent" parameterType="Object">     
    UPDATE STUDENT SET    
        <if test="name!=null and name!='' ">     
            NAME = #{name},      
        </if>     
        <if test="hobby!=null and hobby!='' ">     
            MAJOR = #{major},      
        </if> 
        <if test="hobby!=null and hobby!='' ">     
            HOBBY = #{hobby}    
        </if>          
    WHERE ID = #{id};      
</update>
```

使用set+if标签修改后，如果某项为null则不进行更新，而是保持数据库原值。

##### （2）实例

```sql
<update id="updateStudent" parameterType="Object">     
    UPDATE STUDENT      
    <set>     
        <if test="name!=null and name!='' ">     
            NAME = #{name},      
        </if>     
        <if test="hobby!=null and hobby!='' ">     
            MAJOR = #{major},      
        </if> 
        <if test="hobby!=null and hobby!='' ">     
            HOBBY = #{hobby}    
        </if>     
    </set>     
    WHERE ID = #{id};      
</update>
```



