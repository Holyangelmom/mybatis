### 6.2、include标签

##### （1）意义

用于引用&lt;sql&gt;标签定义的常量

##### （2）实例

```sql
<!-- 查询所有，不分页 -->
<select id="selectAll" resultMap="BaseResultMap">
    SELECT
    <include refid="Base_Column_List" />
    FROM
    student
    <include refid="Example_Where_Clause" />
</select>
```

```sql
<!-- 分页查询 -->
<select id="select" resultMap="BaseResultMap">
    select * from (
        select tt.*,rownum as rowno from 
            (
                SELECT
                <include refid="Base_Column_List" /> 
                FROM
                student
                <include refid="Example_Where_Clause" />
                 ) tt 
                 <where>
                        <if test="pageNum != null and rows != null">
                            and  rownum  <![CDATA[<=]]>#{page}*#{rows}
                        </if>
                </where>
         ) table_alias
    where table_alias.rowno>#{pageNum}
</select>
```

```sql
<!-- 根据条件删除 -->
<delete id="deleteByEntity" parameterType="java.util.Map">
    delete from   student
    <include refid="Example_Where_Clause" />
</delete>
```



