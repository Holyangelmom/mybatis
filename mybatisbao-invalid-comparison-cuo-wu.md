# mybatis报invalid comparison错误

mybatis 传入mapper xml的hashmap的key若命名为values，则报invalid comparison: java.util.HashMap$Values and java.lang.String错误，**因为key名与hashmap内部类Values重名，所以hashmap中的key需要另起名字。**

