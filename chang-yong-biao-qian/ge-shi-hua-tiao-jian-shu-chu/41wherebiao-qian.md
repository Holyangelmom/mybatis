### 4.1、where标签

##### （1）意义

当if标签较多时，这样的组合可能会导致错误。 如下：

```sql
<select id="getStudentListWhere" parameterType="Object" resultMap="BaseResultMap">     
    SELECT * from STUDENT      
        WHERE      
        <if test="name!=null and name!='' ">     
            NAME LIKE CONCAT(CONCAT('%', #{name}),'%')      
        </if>     
        <if test="hobby!= null and hobby!= '' ">     
            AND hobby = #{hobby}      
        </if>     
</select> 
```



