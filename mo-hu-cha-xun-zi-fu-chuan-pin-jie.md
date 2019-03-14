# 模糊查询字符串拼接

### 1、使用concat方法

name like concat\(concat\('%',\#{name}\),'%'\)

### 2、动态sql标签的&lt;bind&gt;标签

	&lt;select id="query" resultType="Map"&gt;

		&lt;bind name="bindName" value="'%'+name+'%'"&gt;&lt;/bind&gt;

		select \*

		from post

		where 1=1

		&lt;if test="name != null"&gt;

		name like \#{bindName}

		&lt;/if&gt;

 	&lt;/select&gt;

