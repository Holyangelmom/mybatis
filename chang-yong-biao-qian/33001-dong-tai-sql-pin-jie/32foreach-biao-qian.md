### 3.2、foreach 标签

##### （1）意义

foreach标签主要用于构建in条件，可在sql中对集合进行迭代。也常用到批量删除、添加等操作中。

##### （2）属性介绍

collection：collection属性的值有三个分别是list、array、map三种，分别对应的参数类型为：List、数组、map集合。

item：表示在迭代过程中每一个元素的别名

index：表示在迭代过程中每次迭代到的位置（下标）

open：前缀

close：后缀

separator：分隔符，表示迭代时每个元素之间以什么分隔

##### （3）实例

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

##### 



