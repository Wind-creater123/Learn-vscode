# ***数据库***

## 理论部分

### 数据库概念

1. **数据库**：数据存储的仓库,有组织,规范的存储数据
2. 数据库解决问题
    - 数据的长久储存
    - 数据规范化储存管理从而高效查找数据
    - 数据备份储存,储存重要数据

### sql基本语法

1. ==通用:  分号;结尾,--或#单行注释,/*多行注释*/==
2. **分类**
   - DDL定义数据库对象(数据库,表)
   - DML数据操作,增删改
   - DQL数据查询
   - DCL增加数据库用户,改变权限
3. **DDL**
    1. 数据库操作
      - show databases;查询所有
      - select database();查询当前数据库
      - create database [库名];创建数据库
      - drop database [库名];删除数据库
      - use [库名];使用,切换数据库
    1. 表操作
      - show tables;
      - ==desc [表名];查询表结构==
      - show create table [表名]查询指定表的建表语句
      - <mark>create table [表名](数据名 类型 comment '注释',...)comment '注释';</mark>
    1. 在当前数据库创建
      - alter table [表名] add 数据名 类型 comment '注释';增
      - alter table [表名] modify 数据名 新数据类型;修改数据类型
      - alter table [表名] change 数据名 新数据名 类型;修改数据名
      - alter table [表名] drop 数据名;删除
      - alter table 表名 rename to 新表名

4. **DML**
    - insert into [表名] (数据名) values (值)
    - update [表名] set 数据名=值1,...[where条件];
    - delete from [表名] [where条件]

5. **DQL**
    - ==select 数据名,... from 表名;通配符*查询所有字段==
    - select 数据名[as 别名],... from 表名;
    - select distinct 数据列表 from 表名;去除重复记录

---

## 实践部分

1. **安装mysql**
   1. Ubuntu打开终端
   2. sudo apt update
   3. sudo apt install mysql-server
    ![下载](../markdown/picture/1.png)
   4. sudo mysql_secure_installation
   5. y 设置密码 y y y y
    ![下载](../markdown/picture/2.png)
   6. 检查systemctl status mysql.service
    ![下载](../markdown/picture/4.png)
   7. sudo mysql -u root -p出现mysql>则成功
    ![下载](../markdown/picture/3.png)
2. **表**
    1. 数据库
![数据库](../markdown/picture/5.png)
    2. 表
![表](../markdown/picture/6.png)
    3. 插入
![插入](../markdown/picture/7.png)
    4. 查询
![查询](../markdown/picture/8.png)

3. **navicat**
    1. **添加新用户**

       - sql查看密码策略show
       variables like  'validate_password%';
       - create user 'your_username'@'你的主机ip' identified '密码';==密码符合策略==
       - grant all privileges on *.* 'your_username'@'密码' with grant option;
       - flush privileges;刷新
    2. **或修改root权限**
        - update mysql.user set host='%' where user='root';
        - 刷新
    3. sudo nano /etc/mysql/mysql.conf.d/mysqld.cnf**修改mysql配置**bind-address=0.0.0.0后重启

![navicat查询](../markdown/picture/9.png)

## 加分项

1. 关系型数据库:建立在关系模型基础上,由多张二维表相互连接组成
2. 常见数据库类型(统称Nosql)
   - 文档数据库
   - 图数据库
   - 列族数据库
   - ==键值数据库(Redis)==
3. 差别
   - 结构不同二维表,文档,图...
   - 语言,关系型用sql,Nosql型没统一语言
   - 表结构严格定义,nosql类型每个结构可以不同
   - 运用场景不同
