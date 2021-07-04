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

文件系统：binlog，作主从复制使用

**MySQL的架构分层**

![mysql分层](/mysql分层.png)

### 3. 执行sql语句过程

![sql语句的执行过程](D:\笔记\typora\mysql\pic\sql语句的执行过程.png)

------

## 二、存储引擎Innodb

### 1. 物理存储结构

​	     ![innodb的物理结构](/innodb的物理结构.png)

**内存部分**

- Buffer Pool：数据页，索引页。sql语句执行时，先和Buffer Pool进行交互。若Buffer Pool可以从磁盘加载，进行修改。索引是在内存中进行查找的
- Change Buffer：支持对没有唯一索引的数据行进行写操作缓存，重点是不需要从磁盘中加载数据对数据进行唯一校验。适用于写多读少、表中大部分没有唯一校验的场景、不会在写数据后立 刻读取 。可以修改Change Buffer的大小。
- Log Buffer：这里是redo log的缓存区，数据来源于Buffer pool。当对Buffer pool进行修改的时候，会插入一份到Log Buffer中。redo log作用：对数据库进行宕机的恢复（crash-safe ）。数据库采用的是先写日志再更新磁盘数据（WAL 技 术 ），日志是顺序IO而磁盘数据更新是随记IO需要找到插入数据位置。log buffer刷盘策略： 每执行一个事务将该事务刷到redo log中，且同时写入磁盘；每秒执行数据写入redo log中并刷到磁盘；事务写入redo log，每秒刷到磁盘
- Adaptive Hash Index：用于处理查找的热点数据，做key-value存储。

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

### 1. 连接配置优化

### 2. 架构优化

### 3. 分库分表

### 4. 主从复制

### 5. 慢SQL分析

### 6. explain解析

### 7. 针对order by 和 offset的分析

------

## 四、面试题



​	