# Redis——NoSQL概述

## ——为什么用NoSQL

### 1、单机MySQL的年代

![image](https://user-images.githubusercontent.com/106053649/181044896-4d18193e-bcb3-4032-9fd8-86e5ea6a0276.png)

- DAL表示数据访问层



### 2、Memcached（缓存）+ MySQL + 垂直拆分（读写分离）

![image](https://user-images.githubusercontent.com/106053649/181044938-adb94d23-6dee-4dec-b2d2-358ec9f6fcb3.png)



### 3、分库分表 + 水平拆分（MySQL集群）

- ==数据库的本质（读，写）==
- 通过缓存能够很好地缓解数据库读的压力
- 早些年MySQL的MYISAM存储引擎是行锁，高并发下出现严重的锁问题
- 转战Innodb：行锁
- 慢慢地通过分库分表解决写的压力

![image](https://user-images.githubusercontent.com/106053649/181045049-df978201-f3cf-470a-9ed8-17f231856f84.png)

- 其中，M和S分别表示MySQL的主、从节点



### 4、如今的年代（关系型数据库不够用）

- 数据量很大，变化很快
- 定位，音乐热榜，博客等数据不太好存在 MySQL中

- #### 为什么要用NoSQL

- 用户的个人信息，社交网络，地理位置，用户自己产生的数据，用户日志等爆发增长

- 关系型数据库不好处理上述数据，NoSQL可以很好地处理以上的情况



## ——什么是NoSQL

- NoSQL = Not Only SQL
- 泛指非关系型数据库，传统的关系型数据库很难对付web2.0时代

- 关系型数据库：表格，行，列
- 而很多数据类型如个人信息，社交网络，地理位置等不需要一个固定的格式
- NoSQL万用的存储方式:map<string, Obj>



### 1、NoSQL特点

- 方便扩展（数据之间没有扩展，很好扩展）->解耦（面向接口编程）
- 大数据量高性能（NoSQL的缓存记录级，是一种细粒度的缓存，性能比较高）
- 数据类型是多样的（不需要事先设计数据库，随取随用）
- 传统关系型数据库（RDBMS）和NoSQL区别

```
传统的 RDBMS
- 结构化组织（行列）
- SQL
- 数据和关系都存在单独的表中 row col
- 数据定义语言
- 严格的一致性
- 基础的事务
- ...
```

```
NoSQL
- 不仅仅是数据
- 没有固定的查询语言
- 键值对存储，列存储，文档存储，图形数据库（社交关系）
- 最终一致性
- CAP定理 和 BASE理论  （异地多活）
- 高性能、高可用、高可扩展（随时水平拆分，机器不够了，扩展机器）
- ...
```



### 2、NoSQL分类

#### KV键值对

- Redis
- ...

#### 文档型数据库

- MongoDB

#### 列存储数据库

- Hbase
- 分布式文件系统

#### 图关系数据库

- 不是图形，放的是关系，如朋友圈社交网络，广告推荐等
- Neo4j，infoGrid
