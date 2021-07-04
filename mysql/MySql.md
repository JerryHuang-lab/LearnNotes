---
typora-root-url: pic
---

# MySQL数据库

## 一、MySQL数据库

### 1.数据库版本

2010 年  MySQL 5.5 发布， InnoDB 成为默认的存储引擎  。之后的版本5.6 可以当成 6.x， 5.7 可以当 成 7.x。  2016年出现了MySQL 8.0版本

### 2. MySQL数据库结构

![](D:\github-work\LearnNotes\mysql\pic\mysql数据库架构.png)

**MySQL服务端组成**

连接池：

缓存：

语法解析器：

执行优化器：

存储引擎：

文件系统：binlog

**MySQL的架构分层**

![mysql分层](/mysql分层.png)

### 3. 执行sql语句过程

![sql语句的执行过程](D:\笔记\typora\mysql\pic\sql语句的执行过程.png)

------

## 二、存储引擎Innodb

### 1. 物理存储结构

​	     ![innodb的物理结构](/innodb的物理结构.png)

**内存部分**

- Buffer Pool
- Change Buffer
- Log Buffer
- Adaptive Hash Index

**磁盘部分**

-   Innodb Data Dictionary
-   Doublewrite Buffer
-   Change Buffer
-   undo Logs

### 2. 逻辑存储结构



### 3. 在innodb的层面上看sql语句的执行

![Innodb执行sql语句](/Innodb执行sql语句.png)

### 4. 索引

​	**innodb索引结构：B+树、全文索引**

​        

​        **innodb索引类型：主键索引、辅助索引**

​	

​	**索引下推**

​	

### 5. 事务

**事务特性（ACID）**

- 原子性
- 一致性
- 隔离性
- 持久化

**事务并发产生的问题**

- 脏读
- 不可重复读
- 幻读

**事务隔离级别**

- 读未提交
- 读已提交
- 可重复读
- 串行化

**Innodb如何解决事务并发问题（MVCC+锁）**

​	默认隔离级别：读已提交（Read Commited RC隔离级别）

- 解决脏读
- 解决不可重复读
- 解决幻读

**为什么Innodb的事务隔离级别默认RC**

​		

------

## 三、数据库优化

### 1. 连接池优化

### 2. 架构优化

### 3. 慢SQL分析

### 4. explain解析

### 5. 针对order by 和 offset的分析

------

## 四、面试题



​	