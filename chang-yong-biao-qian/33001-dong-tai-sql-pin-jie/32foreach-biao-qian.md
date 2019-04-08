### 3.2、foreach 标签

##### （1）意义

foreach标签主要用于构建in条件，可在sql中对集合进行迭代。也常用到批量删除、添加等操作中。

（2）实例

```sql
<delete id="deleteFactors">
		delete from oadb.t_query_info
		where 1 = 1
		<if test="eleIds != null">
        	and ele_id in
        	<foreach collection="eleIds" index="index" item="item" open="(" separator="," close=")">
        		#{item, jdbcType=INTEGER}
        	</foreach>
        </if>
</delete>
```



