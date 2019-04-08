### 1.3、delete标签

##### （1）属性介绍

属性同insert

```sql
<delete id="deleteByPrimaryKey" parameterType="Object">
        delete      from student where id=#{id}
</delete>
```



