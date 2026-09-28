# 数据到底是怎么存放的!

## 运行

1. getById
![3](./3.png)
2. post
![4](./4.png)
3. 分页查询
![6](./6.png)
4. mysql
![7](./7.png)

## 代码理解

1. 建立连接
@autowired实现依赖注入,依据参数创建方法注入参数,spring自动创建bean类
2. getById,post,分类查询
controller层接收请求,转到service层进行处理,最后到mapper层根据请求调用sql语句获取数据
3. @Param注解给对应参数命名后,即可在sql语句中调用对应参数(#{}来引用参数)
4. 在resource的mapper.xml文件中定义方法对应sql语句

## 表索引

索引通过存储指向数据行的指针，可以快速定位和访问表中的特定数据,大大提高 MySQL 的检索速度,这里使用name作索引,因为name比较唯一,不会重复(大...大概吧),当然如果有身份证的话,身份证号码显然更胜任
![8](./8.png)
**创建索引**

1. 建表时创建

```mysql
CREATE TABLE table_name (
  column1 data_type,
  column2 data_type,
  ...,
  INDEX index_name (column1 [ASC|DESC], column2 [ASC|DESC], ...)
);
```

(ASC|DESC为升降序)

2. 直接创建

```mysql
CREATE TABLE table_name (
  column1 data_type,
  column2 data_type,
  ...,
  INDEX index_name (column1 [ASC|DESC], column2 [ASC|DESC], ...)
);
```

3. 图形化工具(navicat)
