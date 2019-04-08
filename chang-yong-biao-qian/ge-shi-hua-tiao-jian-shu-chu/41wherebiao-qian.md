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

当name值为null时，查询语句会出现 “WHERE AND” 的情况，解决该情况除了将"WHERE"改为“WHERE 1=1”之外，还可以利用where标签。这个“where”标签会知道如果它包含的标签中有返回值的话，它就插入一个‘where’。此外，如果标签返回的内容是以AND 或OR 开头的，则它会剔除掉。

##### （2）实例

```sql
<select id="getStudentListWhere" parameterType="Object" resultMap="BaseResultMap">     
    SELECT * from STUDENT      
       <where>   
         <if test="name!=null and name!='' ">     
            NAME LIKE CONCAT(CONCAT('%', #{name}),'%')      
         </if>     
         <if test="hobby!= null and hobby!= '' ">     
            AND hobby = #{hobby}      
         </if>  
       </where>        
</select>
```



