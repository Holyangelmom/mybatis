### 3.3、choose标签

##### （1）意义

有时候我们并不想应用所有的条件，只想从多个选项中选择一个。MyBatis提供了choose 标签，按顺序判断when中的条件是否成立。如果有一个成立，则choose结束。当choose中所有when的条件均不满足时，则执行 otherwise中的sql。

##### （2）实例

```sql
<select id="getStudentListChoose" parameterType="Student" resultMap="BaseResultMap">     
    SELECT * from STUDENT WHERE 1=1    
    <where>     
        <choose>     
            <when test="Name!=null and student!='' ">     
                   AND name LIKE CONCAT(CONCAT('%', #{student}),'%')      
            </when>     
            <when test="hobby!= null and hobby!= '' ">     
                    AND hobby = #{hobby}      
            </when>                   
            <otherwise>     
                    AND AGE = 15  
            </otherwise>     
        </choose>     
    </where>     
</select> 
```



