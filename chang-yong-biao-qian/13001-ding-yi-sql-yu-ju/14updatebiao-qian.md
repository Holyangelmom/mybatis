### 1.4、update标签

##### （1）属性介绍

属性同insert

```sql
<update id="update" parameterType="cn.irds.domain.Catalog">
        update IRDS.T_CATALOG
        <set>
	        <if test="code != null">
	        	"CODE"=#{code,jdbcType=VARCHAR},
	        </if>
	        <if test="name != null">
	        	"NAME"=#{name,jdbcType=VARCHAR},
	        </if>
        </set>
        where ID = #{id,jdbcType=INTEGER}
    </update>
```



