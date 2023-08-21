<!-- @import "[TOC]" {cmd="toc" depthFrom=1 depthTo=6 orderedList=false} -->

# MySQL 入门到高级：基础篇 下篇——尚硅谷 2021 年

<!-- code_chunk_output -->

- [MySQL 入门到高级：基础篇 下篇——尚硅谷 2021 年](#mysql-入门到高级基础篇-下篇尚硅谷-2021-年)
- [第 10 章 创建和管理表](#第-10-章-创建和管理表)
  - [1. 基础知识](#1-基础知识)
    - [1.1 一条数据存储的过程](#11-一条数据存储的过程)
    - [1.2 标识符命名规则](#12-标识符命名规则)
    - [1.3 MySQL 中的数据类型](#13-mysql-中的数据类型)
  - [2. 创建和管理数据库](#2-创建和管理数据库)
    - [2.1 创建数据库](#21-创建数据库)
    - [2.2 使用数据库](#22-使用数据库)
    - [2.3 修改数据库](#23-修改数据库)
    - [2.4 删除数据库](#24-删除数据库)
  - [3. 创建表](#3-创建表)
    - [3.1 创建方式 1](#31-创建方式-1)
    - [3.2 创建方式 2](#32-创建方式-2)
    - [3.3 查看数据表结构](#33-查看数据表结构)
  - [4. 修改表](#4-修改表)
    - [4.1 追加一个列](#41-追加一个列)
    - [4.2 修改一个列](#42-修改一个列)
    - [4.3 重命名一个列](#43-重命名一个列)
    - [4.4 删除一个列](#44-删除一个列)
  - [5. 重命名表](#5-重命名表)
  - [6. 删除表](#6-删除表)
  - [7. 清空表](#7-清空表)
  - [8. 内容拓展](#8-内容拓展)
    - [8.1 拓展 1：阿里巴巴《Java 开发手册》之 MySQL 字段命名](#81-拓展-1阿里巴巴java-开发手册之-mysql-字段命名)
    - [8.2 拓展 2：如何理解清空表、删除表等操作需谨慎？](#82-拓展-2如何理解清空表-删除表等操作需谨慎)
    - [8.3 拓展 3：MySQL8 新特性—DDL 的原子化](#83-拓展-3mysql8-新特性ddl-的原子化)
- [第 11 章 数据处理之增删改](#第-11-章-数据处理之增删改)
  - [1. 插入数据](#1-插入数据)
    - [1.1 实际问题](#11-实际问题)
    - [1.2 方式 1：VALUES 的方式添加](#12-方式-1values-的方式添加)
    - [1.3 方式 2：将查询结果插入到表中](#13-方式-2将查询结果插入到表中)
  - [2. 更新数据](#2-更新数据)
  - [3. 删除数据](#3-删除数据)
  - [4. MySQL8 新特性：计算列](#4-mysql8-新特性计算列)
  - [5. 综合案例](#5-综合案例)
- [第 12 章 MySQL 数据类型精讲](#第-12-章-mysql-数据类型精讲)
  - [1. MySQL 中的数据类型](#1-mysql-中的数据类型)
  - [2. 整数类型](#2-整数类型)
    - [2.1 类型介绍](#21-类型介绍)
    - [2.2 可选属性](#22-可选属性)
      - [2.2.1 M](#221-m)
      - [2.2.2 UNSIGNED](#222-unsigned)
      - [2.2.3 ZEROFILL](#223-zerofill)
    - [2.3 适用场景](#23-适用场景)
    - [2.4 如何选择？](#24-如何选择)
  - [3. 浮点类型](#3-浮点类型)
    - [3.1 类型介绍](#31-类型介绍)
    - [3.2 数据精度说明](#32-数据精度说明)
    - [3.3 精度误差说明](#33-精度误差说明)
  - [4. 定点数类型](#4-定点数类型)
    - [4.1 类型介绍](#41-类型介绍)
    - [4.2 开发中经验](#42-开发中经验)
  - [5. 位类型：BIT](#5-位类型bit)
  - [6. 日期与时间类型](#6-日期与时间类型)
    - [6.1 YEAR 类型](#61-year-类型)
    - [6.2 DATE 类型](#62-date-类型)
    - [6.3 TIME 类型](#63-time-类型)
    - [6.4 DATETIME 类型](#64-datetime-类型)
    - [6.5 TIMESTAMP 类型](#65-timestamp-类型)
    - [6.6 开发中经验](#66-开发中经验)
  - [7. 文本字符串类型](#7-文本字符串类型)
    - [7.1 CHAR 与 VARCHAR 类型](#71-char-与-varchar-类型)
    - [7.2 TEXT 类型](#72-text-类型)
  - [8. ENUM 类型](#8-enum-类型)
  - [9. SET 类型](#9-set-类型)
  - [10. 二进制字符串类型](#10-二进制字符串类型)
    - [BINARY 与 VARBINARY 类型](#binary-与-varbinary-类型)
    - [BLOB 类型](#blob-类型)
  - [11. JSON 类型](#11-json-类型)
  - [12. 空间类型](#12-空间类型)
  - [13. 小结及选择建议](#13-小结及选择建议)
- [第 13 章 约束](#第-13-章-约束)
  - [1. 约束(constraint)概述](#1-约束constraint概述)
    - [1.1 为什么需要约束](#11-为什么需要约束)
    - [1.2 什么是约束](#12-什么是约束)
    - [1.3 约束的分类](#13-约束的分类)
  - [2. 非空约束](#2-非空约束)
    - [2.1 作用](#21-作用)
    - [2.2 关键字](#22-关键字)
    - [2.3 特点](#23-特点)
    - [2.4 添加非空约束](#24-添加非空约束)
    - [2.5 删除非空约束](#25-删除非空约束)
  - [3. 唯一性约束](#3-唯一性约束)
    - [3.1 作用](#31-作用)
    - [3.2 关键字](#32-关键字)
    - [3.3 特点](#33-特点)
    - [3.4 添加唯一约束](#34-添加唯一约束)
    - [3.5 关于复合唯一约束](#35-关于复合唯一约束)
    - [3.5 删除唯一约束](#35-删除唯一约束)
  - [4. PRIMARY KEY 约束](#4-primary-key-约束)
    - [4.1 作用](#41-作用)
    - [4.2 关键字](#42-关键字)
    - [4.3 特点](#43-特点)
    - [4.4 添加主键约束](#44-添加主键约束)
    - [4.5 关于复合主键](#45-关于复合主键)
    - [4.6 删除主键约束](#46-删除主键约束)
  - [5. 自增列：AUTO_INCREMENT](#5-自增列auto_increment)
    - [5.1 作用](#51-作用)
    - [5.2 关键字](#52-关键字)
    - [5.3 特点和要求](#53-特点和要求)
    - [5.4 如何指定自增约束](#54-如何指定自增约束)
    - [5.5 如何删除自增约束](#55-如何删除自增约束)
    - [5.6 MySQL 8.0 新特性—自增变量的持久化](#56-mysql-80-新特性自增变量的持久化)
  - [6. FOREIGN KEY 约束](#6-foreign-key-约束)
    - [6.1 作用](#61-作用)
    - [6.2 关键字](#62-关键字)
    - [6.3 主表和从表/父表和子表](#63-主表和从表父表和子表)
    - [6.4 特点](#64-特点)
    - [6.5 添加外键约束](#65-添加外键约束)
    - [6.6 演示问题](#66-演示问题)
    - [6.7 约束等级](#67-约束等级)
    - [6.8 删除外键约束](#68-删除外键约束)
    - [6.9 开发场景](#69-开发场景)
    - [6.10 阿里开发规范](#610-阿里开发规范)
  - [7. CHECK 约束](#7-check-约束)
    - [7.1 作用](#71-作用)
    - [7.2 关键字](#72-关键字)
    - [7.3 说明：MySQL 5.7 不支持](#73-说明mysql-57-不支持)
  - [8. DEFAULT 约束](#8-default-约束)
    - [8.1 作用](#81-作用)
    - [8.2 关键字](#82-关键字)
    - [8.3 如何给字段加默认值](#83-如何给字段加默认值)
    - [8.4 如何删除默认值约束](#84-如何删除默认值约束)
  - [9. 面试](#9-面试)
- [第 14 章 视图](#第-14-章-视图)
  - [1. 常见的数据库对象](#1-常见的数据库对象)
  - [2. 视图概述](#2-视图概述)
    - [2.1 为什么使用视图？](#21-为什么使用视图)
    - [2.2 视图的理解](#22-视图的理解)
  - [3. 创建视图](#3-创建视图)
    - [3.1 创建单表视图](#31-创建单表视图)
    - [3.2 创建多表联合视图](#32-创建多表联合视图)
    - [3.3 基于视图创建视图](#33-基于视图创建视图)
  - [4. 查看视图](#4-查看视图)
  - [5. 更新视图的数据](#5-更新视图的数据)
    - [5.1 一般情况](#51-一般情况)
    - [5.2 不可更新的视图](#52-不可更新的视图)
  - [6. 修改、删除视图](#6-修改-删除视图)
    - [6.1 修改视图](#61-修改视图)
    - [6.2 删除视图](#62-删除视图)
  - [7. 总结](#7-总结)
    - [7.1 视图优点](#71-视图优点)
    - [7.2 视图不足](#72-视图不足)
- [第 15 章 存储过程与函数](#第-15-章-存储过程与函数)
  - [1. 存储过程概述](#1-存储过程概述)
    - [1.1 理解](#11-理解)
    - [1.2 分类](#12-分类)
  - [2. 创建存储过程](#2-创建存储过程)
    - [2.1 语法分析](#21-语法分析)
    - [2.2 代码举例](#22-代码举例)
  - [3. 调用存储过程](#3-调用存储过程)
    - [3.1 调用格式](#31-调用格式)
    - [3.2 代码举例](#32-代码举例)
    - [3.3 如何调试](#33-如何调试)
  - [4. 存储函数的使用](#4-存储函数的使用)
    - [4.1 语法分析](#41-语法分析)
    - [4.2 调用存储函数](#42-调用存储函数)
    - [4.3 代码举例](#43-代码举例)
    - [4.4 对比存储函数和存储过程](#44-对比存储函数和存储过程)
  - [5. 存储过程和函数的查看、修改、删除](#5-存储过程和函数的查看-修改-删除)
    - [5.1 查看](#51-查看)
    - [5.2 修改](#52-修改)
    - [5.3 删除](#53-删除)
  - [6. 关于存储过程使用的争议](#6-关于存储过程使用的争议)
    - [6.1 优点](#61-优点)
    - [6.2 缺点](#62-缺点)
- [第 16 章 变量、流程控制与游标](#第-16-章-变量-流程控制与游标)
  - [1. 变量](#1-变量)
    - [1.1 系统变量](#11-系统变量)
      - [1.1.1 系统变量分类](#111-系统变量分类)
      - [1.1.2 查看系统变量](#112-查看系统变量)
    - [1.2 用户变量](#12-用户变量)
      - [1.2.1 用户变量分类](#121-用户变量分类)
      - [1.2.2 会话用户变量](#122-会话用户变量)
      - [1.2.3 局部变量](#123-局部变量)
      - [1.2.4 对比会话用户变量与局部变量](#124-对比会话用户变量与局部变量)
  - [2. 定义条件与处理程序](#2-定义条件与处理程序)
    - [2.1 案例分析](#21-案例分析)
    - [2.2 定义条件](#22-定义条件)
    - [2.3 定义处理程序](#23-定义处理程序)
    - [2.4 案例解决](#24-案例解决)
  - [3. 流程控制](#3-流程控制)
    - [3.1 分支结构之 IF](#31-分支结构之-if)
    - [3.2 分支结构之 CASE](#32-分支结构之-case)
    - [3.3 循环结构之 LOOP](#33-循环结构之-loop)
    - [3.4 循环结构之 WHILE](#34-循环结构之-while)
    - [3.5 循环结构之 REPEAT](#35-循环结构之-repeat)
    - [3.6 跳转语句之 LEAVE 语句](#36-跳转语句之-leave-语句)
    - [3.7 跳转语句之 ITERATE 语句](#37-跳转语句之-iterate-语句)
  - [4. 游标](#4-游标)
    - [4.1 什么是游标（或光标）](#41-什么是游标或光标)
    - [4.2 使用游标步骤](#42-使用游标步骤)
    - [4.3 举例](#43-举例)
    - [4.5 小结](#45-小结)
  - [5. 补充：MySQL 8.0 的新特性—全局变量的持久化](#5-补充mysql-80-的新特性全局变量的持久化)
- [第 17 章 触发器](#第-17-章-触发器)
  - [1. 触发器概述](#1-触发器概述)
  - [2. 触发器的创建](#2-触发器的创建)
    - [2.1 创建触发器语法](#21-创建触发器语法)
    - [2.2 代码举例](#22-代码举例-1)
  - [3. 查看、删除触发器](#3-查看-删除触发器)
    - [3.1 查看触发器](#31-查看触发器)
    - [3.2 删除触发器](#32-删除触发器)
  - [4. 触发器的优缺点](#4-触发器的优缺点)
    - [4.1 优点](#41-优点)
    - [4.2 缺点](#42-缺点)
    - [4.3 注意点](#43-注意点)
- [第 18 章 MySQL8 其它新特性](#第-18-章-mysql8-其它新特性)
  - [1. MySQL8 新特性概述](#1-mysql8-新特性概述)
    - [1.1 MySQL8.0 新增特性](#11-mysql80-新增特性)
    - [1.2 MySQL8.0 移除的旧特性](#12-mysql80-移除的旧特性)
  - [2. 新特性 1：窗口函数](#2-新特性-1窗口函数)
    - [2.1 使用窗口函数前后对比](#21-使用窗口函数前后对比)
    - [2.2 窗口函数分类](#22-窗口函数分类)
    - [2.3 语法结构](#23-语法结构)
    - [2.4 分类讲解](#24-分类讲解)
      - [2.4.1 序号函数](#241-序号函数)
      - [2.4.2 分布函数](#242-分布函数)
      - [2.4.3 前后函数](#243-前后函数)
      - [2.4.4 首尾函数](#244-首尾函数)
      - [2.4.5 其他函数](#245-其他函数)
    - [2.5 小 结](#25-小-结)
  - [3. 新特性 2：公用表表达式](#3-新特性-2公用表表达式)
    - [3.1 普通公用表表达式](#31-普通公用表表达式)
    - [3.2 递归公用表表达式](#32-递归公用表表达式)
    - [3.3 小 结](#33-小-结)
- [第 19 章 写在最后](#第-19-章-写在最后)
  - [1. 分享 1](#1-分享-1)
  - [2. 分享 2](#2-分享-2)

<!-- /code_chunk_output -->

# 第 10 章 创建和管理表

## 1. 基础知识

### 1.1 一条数据存储的过程

`存储数据是处理数据的第一步`。只有正确地把数据存储起来，我们才能进行有效的处理和分析。否则，只能是一团乱麻，无从下手。

那么，怎样才能把用户各种经营相关的、纷繁复杂的数据，有序、高效地存储起来呢？ 在 MySQL 中，一个完整的数据存储过程总共有 4 步，分别是创建数据库、确认字段、创建数据表、插入数据。

![一条数据存储的过程](https://img-blog.csdnimg.cn/eddf4d3eaa314994a7b9b9fd265fd1a9.png)

我们要先创建一个数据库，而不是直接创建数据表呢？

因为从系统架构的层次上看，MySQL 数据库系统从大到小依次是`数据库服务器`、`数据库`、`数据表`、数据表的`行与列`。

MySQL 数据库服务器之前已经安装。所以，我们就从创建数据库开始。

### 1.2 标识符命名规则

- 数据库名、表名不得超过 30 个字符，变量名限制为 29 个。

- 必须只能包含 A–Z, a–z, 0–9, \_共 63 个字符。

- 数据库名、表名、字段名等对象名中间不要包含空格。

- 同一个 MySQL 软件中，数据库不能同名；同一个库中，表不能重名；同一个表中，字段不能重名。

- 必须保证你的字段没有和保留字、数据库系统或常用方法冲突。如果坚持使用，请在 SQL 语句中使用`（着重号）引起来。

- 保持字段名和类型的一致性：在命名字段并为其指定数据类型的时候一定要保证一致性，假如数据类型在一个表里是整数，那在另一个表里可就别变成字符型了。

### 1.3 MySQL 中的数据类型

| 类型             | 类型举例                                                                                                             |
| ---------------- | -------------------------------------------------------------------------------------------------------------------- |
| 整数类型         | TINYINT、SMALLINT、MEDIUMINT、**INT(或 INTEGER)**、BIGINT                                                            |
| 浮点类型         | FLOAT、DOUBLE                                                                                                        |
| 定点数类型       | **DECIMAL**                                                                                                          |
| 位类型           | BIT                                                                                                                  |
| 日期时间类型     | YEAR、TIME、**DATE**、DATETIME、TIMESTAMP                                                                            |
| 文本字符串类型   | CHAR、**VARCHAR**、TINYTEXT、TEXT、MEDIUMTEXT、LONGTEXT                                                              |
| 枚举类型         | ENUM                                                                                                                 |
| 集合类型         | SET                                                                                                                  |
| 二进制字符串类型 | BINARY、VARBINARY、TINYBLOB、BLOB、MEDIUMBLOB、LONGBLOB                                                              |
| JSON 类型        | JSON 对象、JSON 数组                                                                                                 |
| 空间数据类型     | 单值：GEOMETRY、POINT、LINESTRING、POLYGON；<br/>集合：MULTIPOINT、MULTILINESTRING、MULTIPOLYGON、GEOMETRYCOLLECTION |

其中，常用的几类类型介绍如下：

| 数据类型      | 描述                                                                                 |
| ------------- | ------------------------------------------------------------------------------------ |
| INT           | 从-2^31 到 2^31-1 的整型数据。存储大小为 4 个字节。                                  |
| CHAR(size)    | 定长字符数据。若未指定，默认为 1 个字符，最大长度 255。                              |
| VARCHAR(size) | 可变长字符数据，根据字符串实际长度保存，**必须指定长度**。                           |
| FLOAT(M,D)    | 单精度，占用 4 个字节，M=整数位+小数位，D=小数位。 D<=M<=255,0<=D<=30，默认 M+D<=6。 |
| DOUBLE(M,D)   | 双精度，占用 8 个字节，D<=M<=255,0<=D<=30，默认 M+D<=15。                            |
| DECIMAL(M,D)  | 高精度小数，占用 M+2 个字节，D<=M<=65，0<=D<=30，最大取值范围与 DOUBLE 相同。        |
| DATE          | 日期型数据，格式'YYYY-MM-DD'。                                                       |
| BLOB          | 二进制形式的长文本数据，最大可达 4G。                                                |
| TEXT          | 长文本数据，最大可达 4G。                                                            |

## 2. 创建和管理数据库

### 2.1 创建数据库

- 方式 1：创建数据库

  > CREATE DATABASE 数据库名;

- 方式 2：创建数据库并指定字符集

  > CREATE DATABASE 数据库名 CHARACTER SET 字符集;

- 方式 3：判断数据库是否已经存在，不存在则创建数据库（`推荐`）

  > CREATE DATABASE IF NOT EXISTS 数据库名;

  如果 MySQL 中已经存在相关的数据库，则忽略创建语句，不再创建数据库。

> 注意：DATABASE 不能改名。一些可视化工具可以改名，它是建新库，把所有表复制到新库，再删旧库完成的。

### 2.2 使用数据库

- 查看当前所有的数据库

  ```sql
  # 有一个 S，代表多个数据库
  SHOW DATABASES;
  ```

- 查看当前正在使用的数据库

  ```sql
  # 使用的一个 mysql 中的全局函数
  SELECT DATABASE();
  ```

- 查看指定库下所有的表

  > SHOW TABLES FROM 数据库名;

- 查看数据库的创建信息

  > SHOW CREATE DATABASE 数据库名;
  > 或者：
  > SHOW CREATE DATABASE 数据库名\G

- 使用/切换数据库

  > USE 数据库名;

> 注意：要操作表格和数据之前必须先说明是对哪个数据库进行操作，否则就要对所有对象加上“数据库名.”。

### 2.3 修改数据库

- 更改数据库字符集

  > \# 比如：gbk、utf8 等
  > ALTER DATABASE 数据库名 CHARACTER SET 字符集;

### 2.4 删除数据库

- 方式 1：删除指定的数据库

  > DROP DATABASE 数据库名;

- 方式 2：删除指定的数据库（`推荐`）

  > DROP DATABASE IF EXISTS 数据库名;

## 3. 创建表

### 3.1 创建方式 1

- **必须具备：**

  - CREATE TABLE 权限。

  - 存储空间。

- **语法格式：**

  > CREATE TABLE [IF NOT EXISTS] 表名(
  > 字段 1, 数据类型 [约束条件] [默认值],
  > 字段 2, 数据类型 [约束条件] [默认值],
  > 字段 3, 数据类型 [约束条件] [默认值],
  > ……
  > [表约束条件]
  > );

  > 加上了 IF NOT EXISTS 关键字，则表示：如果当前数据库中不存在要创建的数据表，则创建数据表；如果当前数据库中已经存在要创建的数据表，则忽略建表语句，不再创建数据表。

- **必须指定：**

  - 表名。

  - 列名(或字段名)，数据类型，**长度**。

- **可选指定：**

  - 约束条件。

  - 默认值。

- 创建表举例 1：

  ```sql
  # 创建表
  CREATE TABLE emp
  (
    # int 类型
    emp_id INT,

    # 最多保存 20 个中英文字符
    emp_name VARCHAR(20),

    # 总位数不超过 15 位
    salary DOUBLE,

    # 日期类型
    birthday DATE
  );
  ```

  ```sql
  DESC emp;
  ```

  ![创建方式 1](https://img-blog.csdnimg.cn/d8210c7b43e248b99c241850538a3004.png)

  MySQL 在执行建表语句时，将 id 字段的类型设置为 int(11)，这里的 11 实际上是 int 类型指定的显示宽度，默认的显示宽度为 11。也可以在创建数据表的时候指定数据的显示宽度。

- 创建表举例 2：

  ```sql
  CREATE TABLE dept
  (
    # int 类型，自增
    deptno INT(2) AUTO_INCREMENT,
    dname VARCHAR(14),
    loc VARCHAR(13),

    # 主键
    PRIMARY KEY (deptno)
  );
  ```

  ```sql
  DESCRIBE dept;
  ```

  ![创建方式 1](https://img-blog.csdnimg.cn/c6aeafc43bb14498b8bf73ad254d4721.png)

> 在 MySQL 8.x 版本中，不再推荐为 INT 类型指定显示长度，并在未来的版本中可能去掉这样的语法。

### 3.2 创建方式 2

- 使用 AS subquery 选项，**将创建表和插入数据结合起来**。

  ![创建方式 2](https://img-blog.csdnimg.cn/f156a89f44e04d159a16f29ea72089bb.png)

- 指定的列和子查询中的列要一一对应。

- 通过列名和默认值定义列。

```sql
CREATE TABLE emp1 AS SELECT * FROM employees;

# 创建的 emp2 是空表
CREATE TABLE emp2 AS SELECT * FROM employees WHERE 1=2;
```

```sql
CREATE TABLE dept
AS
SELECT  employee_id, last_name, salary*12 ANNSAL, hire_date
FROM    employees
WHERE   department_id = 80;

```

```sql
DESCRIBE dept;
```

![创建方式 2](https://img-blog.csdnimg.cn/d3352bfdd75746ea90ba9aae59eba91f.png)

### 3.3 查看数据表结构

在 MySQL 中创建好数据表之后，可以查看数据表的结构。MySQL 支持使用`DESCRIBE/DESC`语句查看数据表结构，也支持使用`SHOW CREATE TABLE`语句查看数据表结构。

语法格式如下：

> SHOW CREATE TABLE 表名\G

使用 SHOW CREATE TABLE 语句不仅可以查看表创建时的详细语句，还可以查看存储引擎和字符编码。

## 4. 修改表

修改表指的是修改数据库中已经存在的数据表的结构。

**使用 ALTER TABLE 语句可以实现：**

- 向已有的表中添加列。

- 修改现有表中的列。

- 删除现有表中的列。

- 重命名现有表中的列。

### 4.1 追加一个列

语法格式如下：

> ALTER TABLE 表名 ADD 【COLUMN】 字段名 字段类型 【FIRST|AFTER 字段名】;

举例：

```sql
ALTER TABLE dept
ADD job_id varchar(15);
```

![追加一个列](https://img-blog.csdnimg.cn/ac4b915b3d9543e28c662968650477a9.png)

### 4.2 修改一个列

- 可以修改列的数据类型，长度、默认值和位置。

- 修改字段数据类型、长度、默认值、位置的语法格式如下：

  > ALTER TABLE 表名 MODIFY 【COLUMN】 字段名 1 字段类型 【DEFAULT 默认值】【FIRST|AFTER 字段名 2】;

- 举例：

  ```sql
  ALTER TABLE	dept
  MODIFY last_name VARCHAR(30);
  ```

  ```sql
  ALTER TABLE	dept
  MODIFY salary double(9,2) default 1000;
  ```

- 对默认值的修改只影响今后对表的修改。

- 此外，还可以通过此种方式修改列的约束。这里暂先不讲。

### 4.3 重命名一个列

使用 CHANGE old_column new_column dataType 子句重命名列。语法格式如下：

> ALTER TABLE 表名 CHANGE 【column】 列名 新列名 新数据类型;

举例：

```sql
ALTER TABLE  dept
CHANGE department_name dept_name varchar(15);
```

### 4.4 删除一个列

删除表中某个字段的语法格式如下：

> ALTER TABLE 表名 DROP 【COLUMN】字段名

举例：

```sql
ALTER TABLE  dept
DROP COLUMN  job_id;
```

## 5. 重命名表

- 方式一：使用 RENAME

  ```sql
  RENAME TABLE emp
  TO myemp;
  ```

- 方式二：

  ```sql
  # [TO] 可以省略
  ALTER table dept
  RENAME [TO] detail_dept;
  ```

- 必须是对象的拥有者。

## 6. 删除表

- 在 MySQL 中，当一张数据表`没有与其他任何数据表形成关联关系`时，可以将当前数据表直接删除。

- 数据和结构都被删除。

- 所有正在运行的相关事务被提交。

- 所有相关索引被删除。

- 语法格式：

  > DROP TABLE [IF EXISTS] 数据表 1 [, 数据表 2, ... , 数据表 n];

  `IF EXISTS`的含义为：如果当前数据库中存在相应的数据表，则删除数据表；如果当前数据库中不存在相应的数据表，则忽略删除语句，不再执行删除数据表的操作。

- 举例：

  ```sql
  DROP TABLE dept;
  ```

- DROP TABLE 语句不能回滚。

## 7. 清空表

- TRUNCATE TABLE 语句：

  - 删除表中所有的数据。

  - 释放表的存储空间。

- 举例：

  ```sql
  TRUNCATE TABLE detail_dept;
  ```

- TRUNCATE 语句**不能回滚**，而使用 DELETE 语句删除数据，可以回滚。

- 对比：

  ```sql
  SET autocommit = FALSE;

  DELETE FROM emp2;
  #TRUNCATE TABLE emp2;

  SELECT * FROM emp2;

  ROLLBACK;

  SELECT * FROM emp2;
  ```

> 阿里开发规范：
>
> 【参考】TRUNCATE TABLE 比 DELETE 速度快，且使用的系统和事务日志资源少，但 TRUNCATE 无事务且不触发 TRIGGER，有可能造成事故，故不建议在开发代码中使用此语句。
>
> 说明：TRUNCATE TABLE 在功能上与不带 WHERE 子句的 DELETE 语句相同。

## 8. 内容拓展

### 8.1 拓展 1：阿里巴巴《Java 开发手册》之 MySQL 字段命名

- 【`强制`】表名、字段名必须使用小写字母或数字，禁止出现数字开头，禁止两个下划线中间只出现数字。数据库字段名的修改代价很大，因为无法进行预发布，所以字段名称需要慎重考虑。

  - 正例：aliyun_admin，rdc_config，level3_name

  - 反例：AliyunAdmin，rdcConfig，level_3_name

- 【`强制`】禁用保留字，如 desc、range、match、delayed 等，请参考 MySQL 官方保留字。

- 【`强制`】表必备三字段：id, gmt_create, gmt_modified。

  - 说明：其中 id 必为主键，类型为 BIGINT UNSIGNED、单表时自增、步长为 1。gmt_create, gmt_modified 的类型均为 DATETIME 类型，前者现在时表示主动式创建，后者过去分词表示被动式更新。

- 【`推荐`】表的命名最好是遵循 “业务名称\_表的作用”。

  - 正例：alipay_task 、 force_project、 trade_config

- 【`推荐`】库名与应用名称尽量一致。

- 【`参考`】合适的字符存储长度，不但节约数据库表空间、节约索引存储，更重要的是提升检索速度。

  - 正例：无符号值可以避免误存负数，且扩大了表示范围。

![拓展 1：阿里巴巴《Java 开发手册》之 MySQL 字段命名](https://img-blog.csdnimg.cn/089df6d5df4647a1b01ad3981d3a2eb8.png)

### 8.2 拓展 2：如何理解清空表、删除表等操作需谨慎？

`表删除`操作将把表的定义和表中的数据一起删除，并且 MySQL 在执行删除操作时，不会有任何的确认信息提示，因此执行删除操时应当慎重。在删除表前，最好对表中的数据进行`备份`，这样当操作失误时可以对数据进行恢复，以免造成无法挽回的后果。

同样的，在使用 `ALTER TABLE` 进行表的基本修改操作时，在执行操作过程之前，也应该确保对数据进行完整的`备份`，因为数据库的改变是`无法撤销`的，如果添加了一个不需要的字段，可以将其删除；相同的，如果删除了一个需要的列，该列下面的所有数据都将会丢失。

### 8.3 拓展 3：MySQL8 新特性—DDL 的原子化

在 MySQL 8.0 版本中，InnoDB 表的 DDL 支持事务完整性，即`DDL操作要么成功要么回滚`。DDL 操作回滚日志写入到 data dictionary 数据字典表 mysql.innodb_ddl_log（该表是隐藏的表，通过 show tables 无法看到）中，用于回滚操作。通过设置参数，可将 DDL 操作日志打印输出到 MySQL 错误日志中。

分别在 MySQL 5.7 版本和 MySQL 8.0 版本中创建数据库和数据表，结果如下：

```sql
CREATE DATABASE mytest;

USE mytest;

CREATE TABLE book1
(
book_id INT ,
book_name VARCHAR(255)
);

SHOW TABLES;
```

（1）在 MySQL 5.7 版本中，测试步骤如下：
删除数据表 book1 和数据表 book2，结果如下：

```sh
mysql> DROP TABLE book1,book2;
ERROR 1051 (42S02): Unknown table 'mytest.book2'
```

再次查询数据库中的数据表名称，结果如下：

```sh
mysql> SHOW TABLES;
Empty set (0.00 sec)
```

从结果可以看出，虽然删除操作时报错了，但是仍然删除了数据表 book1。

（2）在 MySQL 8.0 版本中，测试步骤如下：
删除数据表 book1 和数据表 book2，结果如下：

```sh
mysql> DROP TABLE book1,book2;
ERROR 1051 (42S02): Unknown table 'mytest.book2'
```

再次查询数据库中的数据表名称，结果如下：

```sh
mysql> show tables;
+-----------------+
| Tables_in_mytest |
+------------------+
| book1            |
+------------------+
1 row in set (0.00 sec)
```

从结果可以看出，数据表 book1 并没有被删除。

# 第 11 章 数据处理之增删改

## 1. 插入数据

### 1.1 实际问题

![实际问题](https://img-blog.csdnimg.cn/81a5d19fb2bf4c75a96c857100d3bc82.png)

解决方式：使用 INSERT 语句向表中插入数据。

### 1.2 方式 1：VALUES 的方式添加

使用这种语法一次只能向表中插入**一条**数据。

**情况 1：为表的所有字段按默认顺序插入数据**

> INSERT INTO 表名
> VALUES (value1,value2,....);

值列表中需要为表的每一个字段指定值，并且值的顺序必须和数据表中字段定义时的顺序相同。

举例：

```sql
INSERT INTO departments
VALUES (70, 'Pub', 100, 1700);
```

```sql
INSERT INTO	departments
VALUES		(100, 'Finance', NULL, NULL);
```

**情况 2：为表的指定字段插入数据**

> INSERT INTO 表名(column1 [, column2, ... , columnn])
> VALUES (value1 [,value2, ... , valuen]);

为表的指定字段插入数据，就是在 INSERT 语句中只向部分字段中插入值，而其他字段的值为表定义时的默认值。

在 INSERT 子句中随意列出列名，但是一旦列出，VALUES 中要插入的 value1,....valuen 需要与 column1,...columnn 列一一对应。如果类型不同，将无法插入，并且 MySQL 会产生错误。

举例：

```sql
INSERT INTO departments(department_id, department_name)
VALUES (80, 'IT');
```

**情况 3：同时插入多条记录**

INSERT 语句可以同时向数据表中插入多条记录，插入时指定多个值列表，每个值列表之间用逗号分隔开，基本语法格式如下：

> INSERT INTO table_name
> VALUES
> (value1 [,value2, ... , valuen]),
> (value1 [,value2, ... , valuen]),
> ……
> (value1 [,value2, ... , valuen]);

或者

> INSERT INTO table_name(column1 [, column2, ... , columnn])
> VALUES
> (value1 [,value2, ... , valuen]),
> (value1 [,value2, ... , valuen]),
> ……
> (value1 [,value2, ... , valuen]);

举例：

```sql
mysql> INSERT INTO emp(emp_id,emp_name)
    -> VALUES (1001,'shkstart'),
    -> (1002,'myxh'),
    -> (1003,'Tom');
Query OK, 3 rows affected (0.00 sec)
Records: 3  Duplicates: 0  Warnings: 0
```

使用 INSERT 同时插入多条记录时，MySQL 会返回一些在执行单行插入时没有的额外信息，这些信息的含义如下：

- Records：表明插入的记录条数。

- Duplicates：表明插入时被忽略的记录，原因可能是这些记录包含了重复的主键值。

- Warnings：表明有问题的数据值，例如发生数据类型转换。

> 一个同时插入多行记录的 INSERT 语句等同于多个单行插入的 INSERT 语句，但是多行的 INSERT 语句在处理过程中`效率更高`。因为 MySQL 执行单条 INSERT 语句插入多行数据比使用多条 INSERT 语句快，所以在插入多条记录时最好选择使用单条 INSERT 语句的方式插入。

**小结：**

- `VALUES`也可以写成`VALUE`，但是 VALUES 是标准写法。

- 字符和日期型数据应包含在单引号中。

### 1.3 方式 2：将查询结果插入到表中

INSERT 还可以将 SELECT 语句查询的结果插入到表中，此时不需要把每一条记录的值一个一个输入，只需要使用一条 INSERT 语句和一条 SELECT 语句组成的组合语句即可快速地从一个或多个表中向一个表中插入多行。

基本语法格式如下：

> INSERT INTO 目标表名
> (tar_column1 [, tar_column2, ... , tar_columnn])
> SELECT
> (src_column1 [, src_column2, ... , src_columnn])
> FROM 源表名
> [WHERE condition]

- 在 INSERT 语句中加入子查询。

- **不必书写** **VALUES** **子句。**

- 子查询中的值列表应与 INSERT 子句中的列名对应。

举例：

```sql
INSERT INTO emp2
SELECT *
FROM employees
WHERE department_id = 90;
```

```sql
INSERT INTO sales_reps(id, name, salary, commission_pct)
SELECT employee_id, last_name, salary, commission_pct
FROM   employees
WHERE  job_id LIKE '%REP%';
```

## 2. 更新数据

![更新数据](https://img-blog.csdnimg.cn/3794df399f1a414682fc562b251e3f51.png)

- 使用 UPDATE 语句更新数据。语法如下：

  > UPDATE table_name
  > SET column1=value1, column2=value2, ... , column=valuen
  > [WHERE condition]

- 可以一次更新**多条**数据。

- 如果需要回滚数据，需要保证在 DML 前，进行设置：**SET AUTOCOMMIT = FALSE;**。

- 使用 **WHERE** 子句指定需要更新的数据。

  ```sql
  UPDATE employees
  SET    department_id = 70
  WHERE  employee_id = 113;
  ```

- 如果省略 WHERE 子句，则表中的所有数据都将被更新。

  ```sql
  UPDATE   copy_emp
  SET      department_id = 110;
  ```

- **更新中的数据完整性错误**。

  ```sql
  UPDATE employees
  SET    department_id = 55
  WHERE  department_id = 110;
  ```

  ![更新数据](https://img-blog.csdnimg.cn/a313bff68d5f456c9e1fa7f04c99f923.png)

  > 说明：不存在 55 号部门

## 3. 删除数据

![删除数据](https://img-blog.csdnimg.cn/384dbd78e0c44822b7226e9ac54f6f22.png)

- 使用 DELETE 语句从表中删除数据。

  ![删除数据](https://img-blog.csdnimg.cn/855d690c51ce4f8c9ec0a73e85a5e1b7.png)

  > DELETE FROM table_name [WHERE <condition>];

  table_name 指定要执行删除操作的表；“[WHERE <condition>]”为可选参数，指定删除条件，如果没有 WHERE 子句，DELETE 语句将删除表中的所有记录。

- 使用 WHERE 子句删除指定的记录。

  ```sql
  DELETE FROM departments
  WHERE  department_name = 'Finance';
  ```

- 如果省略 WHERE 子句，则表中的全部数据将被删除。

  ```sql
  DELETE FROM  copy_emp;
  ```

- **删除中的数据完整性错误**。

  ```sql
  DELETE FROM departments
  WHERE       department_id = 60;
  ```

  ![删除数据](https://img-blog.csdnimg.cn/f20265856206405b91229f3bb8d0604e.png)

  > 说明：
  >
  > You cannot delete a row that contains a primary key that is used as a foreign key in another table.
  > 不能删除包含在另一个表中用作外键的主键的行。

## 4. MySQL8 新特性：计算列

什么叫计算列呢？简单来说就是某一列的值是通过别的列计算得来的。例如，a 列值为 1、b 列值为 2，c 列不需要手动插入，定义 a+b 的结果为 c 的值，那么 c 就是计算列，是通过别的列计算得来的。

在 MySQL 8.0 中，CREATE TABLE 和 ALTER TABLE 中都支持增加计算列。下面以 CREATE TABLE 为例进行讲解。

举例：定义数据表 tb1，然后定义字段 id、字段 a、字段 b 和字段 c，其中字段 c 为计算列，用于计算 a+b 的值。
首先创建测试表 tb1，语句如下：

```sql
CREATE TABLE tb1
(
  id INT,
  a INT,
  b INT,
  c INT GENERATED ALWAYS AS (a + b) VIRTUAL
);
```

插入演示数据，语句如下：

```sql
INSERT INTO tb1(a,b) VALUES (100,200);
```

查询数据表 tb1 中的数据，结果如下：

```sh
mysql> SELECT * FROM tb1;
+------+------+------+------+
| id   | a    | b    | c    |
+------+------+------+------+
| NULL |  100 |  200 |  300 |
+------+------+------+------+
1 row in set (0.00 sec)
```

更新数据中的数据，语句如下：

```sh
mysql> UPDATE tb1 SET a = 500;
Query OK, 0 rows affected (0.00 sec)
Rows matched: 1  Changed: 0  Warnings: 0
```

## 5. 综合案例

1、创建数据库 test01_library。

```sql
CREATE DATABASE IF NOT EXISTS test01_library CHARACTER SET 'utf8';

# 指定使用哪个数据库。
USE test01_library;
```

2、创建表 books，表结构如下：

| 字段名  | 字段说明 | 数据类型     |
| ------- | -------- | ------------ |
| id      | 书编号   | INT          |
| name    | 书名     | VARCHAR(50)  |
| authors | 作者     | VARCHAR(100) |
| price   | 价格     | FLOAT        |
| pubdate | 出版日期 | YEAR         |
| note    | 说明     | VARCHAR(100) |
| num     | 库存     | INT          |

```sql
CREATE TABLE books
(
  id INT,
  name VARCHAR(50),
  `authors` VARCHAR(100) ,
  price FLOAT,
  pubdate YEAR ,
  note VARCHAR(100),
  num INT
);
```

3、向 books 表中插入记录。
① 不指定字段名称，插入第一条记录。
② 指定所有字段名称，插入第二记录。
③ 同时插入多条记录（剩下的所有记录）。

| id  | name          | authors         | price | pubdate | note     | num |
| --- | ------------- | --------------- | ----- | ------- | -------- | --- |
| 1   | Tal of AAA    | Dickes          | 23    | 1995    | novel    | 11  |
| 2   | EmmaT         | Jane lura       | 35    | 1993    | joke     | 22  |
| 3   | Story of Jane | Jane Tim        | 40    | 2001    | novel    | 0   |
| 4   | Lovey Day     | George Byron    | 20    | 2005    | novel    | 30  |
| 5   | Old land      | Honore Blade    | 30    | 2010    | law      | 0   |
| 6   | The Battle    | Upton Sara      | 30    | 1999    | medicine | 40  |
| 7   | Rose Hood     | Richard haggard | 28    | 2008    | cartoon  | 28  |

```sql
# ① 不指定字段名称，插入第一条记录。
INSERT INTO books
VALUES(1,'Tal of AAA','Dickes',23,1995,'novel',11);

# ② 指定所有字段名称，插入第二记录。

INSERT INTO books (id,name,`authors`,price,pubdate,note,num)
VALUES(2,'EmmaT','Jane lura',35,1993,'Joke',22);

# ③ 同时插入多条记录（剩下的所有记录）。
INSERT INTO books (id,name,`authors`,price,pubdate,note,num) VALUES
(3,'Story of Jane','Jane Tim',40,2001,'novel',0),
(4,'Lovey Day','George Byron',20,2005,'novel',30),
(5,'Old land','Honore Blade',30,2010,'Law',0),
(6,'The Battle','Upton Sara',30,1999,'medicine',40),
(7,'Rose Hood','Richard haggard',28,2008,'cartoon',28);
```

4、将小说类型(novel)的书的价格都增加 5。

```sql
UPDATE books SET price=price+5 WHERE note = 'novel';
```

5、将名称为 EmmaT 的书的价格改为 40，并将说明改为 drama。

```sql
UPDATE books SET price=40,note='drama' WHERE name='EmmaT';
```

6、删除库存为 0 的记录。

```sql
DELETE FROM books WHERE num=0;
```

7、统计书名中包含 a 字母的书。

```sql
SELECT \* FROM books WHERE name LIKE '%a%';
```

8、统计书名中包含 a 字母的书的数量和库存总量。

```sql
SELECT COUNT(\*),SUM(num) FROM books WHERE name LIKE '%a%';
```

9、找出“novel”类型的书，按照价格降序排列。

```sql
SELECT \* FROM books WHERE note = 'novel' ORDER BY price DESC;
```

10、查询图书信息，按照库存量降序排列，如果库存量相同的按照 note 升序排列。

```sql
SELECT \* FROM books ORDER BY num DESC,note ASC;
```

11、按照 note 分类统计书的数量。

```sql
SELECT note,COUNT(\*) FROM books GROUP BY note;
```

12、按照 note 分类统计书的库存量，显示库存量超过 30 本的。

```sql
SELECT note,SUM(num) FROM books GROUP BY note HAVING SUM(num)>30;
```

13、查询所有图书，每页显示 5 本，显示第二页。

```sql
SELECT \* FROM books LIMIT 5,5;
```

14、按照 note 分类统计书的库存量，显示库存量最多的。

```sql
SELECT note,SUM(num) sum_num FROM books GROUP BY note ORDER BY sum_num DESC LIMIT 0,1;
```

15、查询书名达到 10 个字符的书，不包括里面的空格。

```sql
SELECT \* FROM books WHERE CHAR_LENGTH(REPLACE(name,' ',''))>=10;
```

16、查询书名和类型，其中 note 值为 novel 显示小说，law 显示法律，medicine 显示医药，cartoon 显示卡通，joke 显示笑话。

```sql
SELECT name AS "书名" ,note, CASE note
WHEN 'novel' THEN '小说'
WHEN 'law' THEN '法律'
WHEN 'medicine' THEN '医药'
WHEN 'cartoon' THEN '卡通'
WHEN 'joke' THEN '笑话'
END AS "类型"
FROM books;
```

17、查询书名、库存，其中 num 值超过 30 本的，显示滞销，大于 0 并低于 10 的，显示畅销，为 0 的显示需要无货。

```sql
SELECT name,num,CASE
WHEN num>30 THEN '滞销'
WHEN num>0 AND num<10 THEN '畅销'
WHEN num=0 THEN '无货'
ELSE '正常'
END AS "库存状态"
FROM books;
```

18、统计每一种 note 的库存量，并合计总量。

```sql
SELECT IFNULL(note,'合计总库存量') AS note,SUM(num) FROM books GROUP BY note WITH ROLLUP;
```

19、统计每一种 note 的数量，并合计总量。

```sql
SELECT IFNULL(note,'合计总数') AS note,COUNT(\*) FROM books GROUP BY note WITH ROLLUP;
```

20、统计库存量前三名的图书。

```sql
SELECT \* FROM books ORDER BY num DESC LIMIT 0,3;
```

21、找出最早出版的一本书。

```sql
SELECT \* FROM books ORDER BY pubdate ASC LIMIT 0,1;
```

22、找出 novel 中价格最高的一本书。

```sql
SELECT \* FROM books WHERE note = 'novel' ORDER BY price DESC LIMIT 0,1;
```

23、找出书名中字数最多的一本书，不含空格。

```sql
SELECT \* FROM books ORDER BY CHAR_LENGTH(REPLACE(name,' ','')) DESC LIMIT 0,1;
```

# 第 12 章 MySQL 数据类型精讲

## 1. MySQL 中的数据类型

| 类型             | 类型举例                                                                                                                     |
| ---------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| 整数类型         | TINYINT、SMALLINT、MEDIUMINT、INT(或 INTEGER)、BIGINT                                                                        |
| 浮点类型         | FLOAT、DOUBLE                                                                                                                |
| 定点数类型       | DECIMAL                                                                                                                      |
| 位类型           | BIT                                                                                                                          |
| 日期时间类型     | YEAR、TIME、DATE、DATETIME、TIMESTAMP                                                                                        |
| 文本字符串类型   | CHAR、VARCHAR、TINYTEXT、TEXT、MEDIUMTEXT、LONGTEXT                                                                          |
| 枚举类型         | ENUM                                                                                                                         |
| 集合类型         | SET                                                                                                                          |
| 二进制字符串类型 | BINARY、VARBINARY、TINYBLOB、BLOB、MEDIUMBLOB、LONGBLOB                                                                      |
| JSON 类型        | JSON 对象、JSON 数组                                                                                                         |
| 空间数据类型     | 单值类型：GEOMETRY、POINT、LINESTRING、POLYGON；<br/>集合类型：MULTIPOINT、MULTILINESTRING、MULTIPOLYGON、GEOMETRYCOLLECTION |

常见数据类型的属性，如下：

| MySQL 关键字       | 含义                       |
| ------------------ | -------------------------- |
| NULL               | 数据列可包含 NULL 值。     |
| NOT NULL           | 数据列不允许包含 NULL 值。 |
| DEFAULT            | 默认值。                   |
| PRIMARY KEY        | 主键。                     |
| AUTO_INCREMENT     | 自动递增，适用于整数类型。 |
| UNSIGNED           | 无符号。                   |
| CHARACTER SET name | 指定一个字符集。           |

## 2. 整数类型

### 2.1 类型介绍

整数类型一共有 5 种，包括 TINYINT、SMALLINT、MEDIUMINT、INT（INTEGER）和 BIGINT。

它们的区别如下表所示：

| **整数类型** | **字节** | 有符号数取值范围                         | 无符号数取值范围       |
| ------------ | -------- | ---------------------------------------- | ---------------------- |
| TINYINT      | 1        | -128~127                                 | 0~255                  |
| SMALLINT     | 2        | -32768~32767                             | 0~65535                |
| MEDIUMINT    | 3        | -8388608~8388607                         | 0~16777215             |
| INT、INTEGER | 4        | -2147483648~2147483647                   | 0~4294967295           |
| BIGINT       | 8        | -9223372036854775808~9223372036854775807 | 0~18446744073709551615 |

### 2.2 可选属性

**整数类型的可选属性有三个：**

#### 2.2.1 M

`M`: 表示显示宽度，M 的取值范围是(0, 255)。例如，int(5)：当数据宽度小于 5 位的时候在数字前面需要用字符填满宽度。该项功能需要配合“`ZEROFILL`”使用，表示用“0”填满宽度，否则指定显示宽度无效。

如果设置了显示宽度，那么插入的数据宽度超过显示宽度限制，会不会截断或插入失败？

答案：不会对插入的数据有任何影响，还是按照类型的实际宽度进行保存，即`显示宽度与类型可以存储的值范围无关`。**从 MySQL 8.0.17 开始，整数数据类型不推荐使用显示宽度属性。**

整型数据类型可以在定义表结构时指定所需要的显示宽度，如果不指定，则系统为每一种类型指定默认的宽度值。

举例：

```sql
CREATE TABLE test_int1 ( x TINYINT,　y SMALLINT,　z MEDIUMINT,　m INT,　n BIGINT );
```

查看表结构 （MySQL5.7 中显式如下，MySQL8 中不再显式范围）。

```sh
mysql> desc test_int1;
+-------+--------------+------+-----+---------+-------+
| Field | Type         | Null | Key | Default | Extra |
+-------+--------------+------+-----+---------+-------+
|   x   | tinyint(4)   | YES  |     | NULL    |       |
| 　y   | smallint(6)  | YES  |     | NULL    |       |
| 　z   | mediumint(9) | YES  |     | NULL    |       |
| 　m   | int(11)      | YES  |     | NULL    |       |
| 　n   | bigint(20)   | YES  |     | NULL    |       |
+-------+--------------+------+-----+---------+-------+
5 rows in set (0.00 sec)
```

TINYINT 有符号数和无符号数的取值范围分别为-128~127 和 0~255，由于负号占了一个数字位，因此 TINYINT 默认的显示宽度为 4。同理，其他整数类型的默认显示宽度与其有符号数的最小值的宽度相同。

举例：

```sql
CREATE TABLE test_int2
(
  f1 INT,
  f2 INT(5),
  f3 INT(5) ZEROFILL
)

DESC test_int2;

INSERT INTO test_int2(f1,f2,f3)
VALUES(1,123,123);

INSERT INTO test_int2(f1,f2)
VALUES(123456,123456);

INSERT INTO test_int2(f1,f2,f3)
VALUES(123456,123456,123456);
```

```sh
mysql> SELECT * FROM test_int2;
+--------+--------+--------+
| f1     | f2     | f3     |
+--------+--------+--------+
|      1 |    123 |  00123 |
| 123456 | 123456 |   NULL |
| 123456 | 123456 | 123456 |
+--------+--------+--------+
3 rows in set (0.00 sec)
```

#### 2.2.2 UNSIGNED

`UNSIGNED`: 无符号类型（非负），所有的整数类型都有一个可选的属性 UNSIGNED（无符号属性），无符号整数类型的最小取值为 0。所以，如果需要在 MySQL 数据库中保存非负整数值时，可以将整数类型设置为无符号类型。

int 类型默认显示宽度为 int(11)，无符号 int 类型默认显示宽度为 int(10)。

```sql
CREATE TABLE test_int3
(
  f1 INT UNSIGNED
);
```

```sh
mysql> desc test_int3;
+-------+------------------+------+-----+---------+-------+
| Field | Type             | Null | Key | Default | Extra |
+-------+------------------+------+-----+---------+-------+
| f1    | int(10) unsigned | YES  |     | NULL    |       |
+-------+------------------+------+-----+---------+-------+
1 row in set (0.00 sec)
```

#### 2.2.3 ZEROFILL

`ZEROFILL`: 0 填充,（如果某列是 ZEROFILL，那么 MySQL 会自动为当前列添加 UNSIGNED 属性），如果指定了 ZEROFILL 只是表示不够 M 位时，用 0 在左边填充，如果超过 M 位，只要不超过数据存储范围即可。

原来，在 int(M) 中，M 的值跟 int(M) 所占多少存储空间并无任何关系。 int(3)、int(4)、int(8) 在磁盘上都是占用 4 bytes 的存储空间。也就是说，**int(M)，必须和 UNSIGNED ZEROFILL 一起使用才有意义。** 如果整数值超过 M 位，就按照实际位数存储。只是无须再用字符 0 进行填充。

### 2.3 适用场景

`TINYINT`：一般用于枚举数据，比如系统设定取值范围很小且固定的场景。

`SMALLINT`：可以用于较小范围的统计数据，比如统计工厂的固定资产库存数量等。

`MEDIUMINT`：用于较大整数的计算，比如车站每日的客流量等。

`INT、INTEGER`：取值范围足够大，一般情况下不用考虑超限问题，用得最多。比如商品编号。

`BIGINT`：只有当你处理特别巨大的整数时才会用到。比如双十一的交易量、大型门户网站点击量、证券公司衍生产品持仓等。

### 2.4 如何选择？

在评估用哪种整数类型的时候，你需要考虑`存储空间`和`可靠性`的平衡问题：一方 面，用占用字节数少的整数类型可以节省存储空间；另一方面，要是为了节省存储空间， 使用的整数类型取值范围太小，一旦遇到超出取值范围的情况，就可能引起`系统错误`，影响可靠性。

举个例子，商品编号采用的数据类型是 INT。原因就在于，客户门店中流通的商品种类较多，而且，每天都有旧商品下架，新商品上架，这样不断迭代，日积月累。

如果使用 SMALLINT 类型，虽然占用字节数比 INT 类型的整数少，但是却不能保证数据不会超出范围 65535。相反，使用 INT，就能确保有足够大的取值范围，不用担心数据超出范围影响可靠性的问题。

你要注意的是，在实际工作中，**系统故障产生的成本远远超过增加几个字段存储空间所产生的成本**。因此，我建议你首先确保数据不会超过取值范围，在这个前提之下，再去考虑如何节省存储空间。

## 3. 浮点类型

### 3.1 类型介绍

浮点数和定点数类型的特点是可以`处理小数`，你可以把整数看成小数的一个特例。因此，浮点数和定点数的使用场景，比整数大多了。 MySQL 支持的浮点数类型，分别是 FLOAT、DOUBLE、REAL。

- FLOAT 表示单精度浮点数；

- DOUBLE 表示双精度浮点数；

![类型介绍](https://img-blog.csdnimg.cn/622dc11ed0e242688fa25c540c546807.png)

- REAL 默认就是 DOUBLE。如果你把 SQL 模式设定为启用“`REAL_AS_FLOAT`”，那 么，MySQL 就认为 REAL 是 FLOAT。如果要启用“REAL_AS_FLOAT”，可以通过以下 SQL 语句实现：

  ```sql
  SET sql_mode = “REAL_AS_FLOAT”;
  ```

**问题 1：** FLOAT 和 DOUBLE 这两种数据类型的区别是啥呢？

FLOAT 占用字节数少，取值范围小；DOUBLE 占用字节数多，取值范围也大。

**问题 2：** 为什么浮点数类型的无符号数取值范围，只相当于有符号数取值范围的一半，也就是只相当于有符号数取值范围大于等于零的部分呢？

MySQL 存储浮点数的格式为：`符号(S)`、`尾数(M)`和 `阶码(E)`。因此，无论有没有符号，MySQL 的浮点数都会存储表示符号的部分。因此， 所谓的无符号数取值范围，其实就是有符号数取值范围大于等于零的部分。

### 3.2 数据精度说明

对于浮点类型，在 MySQL 中单精度值使用`4`个字节，双精度值使用`8`个字节。

- MySQL 允许使用`非标准语法`（其他数据库未必支持，因此如果涉及到数据迁移，则最好不要这么用）：`FLOAT(M,D)`或`DOUBLE(M,D)`。这里，M 称为`精度`，D 称为`标度`。(M,D)中 M=整数位+小数位，D=小数位。 D<=M<=255，0<=D<=30。

  例如，定义为 FLOAT(5,2)的一个列可以显示为-999.99-999.99。如果超过这个范围会报错。

- FLOAT 和 DOUBLE 类型在不指定(M,D)时，默认会按照实际的精度（由实际的硬件和操作系统决定）来显示。

- 说明：浮点类型，也可以加`UNSIGNED`，但是不会改变数据范围，例如：FLOAT(3,2) UNSIGNED 仍然只能表示 0-9.99 的范围。

- 不管是否显式设置了精度(M,D)，这里 MySQL 的处理方案如下：

  - 如果存储时，整数部分超出了范围，MySQL 就会报错，不允许存这样的值。

  - 如果存储时，小数点部分若超出范围，就分以下情况：

    - 若四舍五入后，整数部分没有超出范围，则只警告，但能成功操作并四舍五入删除多余的小数位后保存。例如在 FLOAT(5,2)列内插入 999.009，近似结果是 999.01。

    - 若四舍五入后，整数部分超出范围，则 MySQL 报错，并拒绝处理。如 FLOAT(5,2)列内插入 999.995 和-999.995 都会报错。

- **从 MySQL 8.0.17 开始，FLOAT(M,D) 和 DOUBLE(M,D)用法在官方文档中已经明确不推荐使用**，将来可能被移除。另外，关于浮点型 FLOAT 和 DOUBLE 的 UNSIGNED 也不推荐使用了，将来也可能被移除。

- 举例

  ```sql
  CREATE TABLE test_double1
  (
    f1 FLOAT,
    f2 FLOAT(5,2),
    f3 DOUBLE,
    f4 DOUBLE(5,2)
  );

  DESC test_double1;

  INSERT INTO test_double1
  VALUES(123.456,123.456,123.4567,123.45);

  # Out of range value for column 'f2' at row 1
  INSERT INTO test_double1
  VALUES(123.456,1234.456,123.4567,123.45);

  SELECT * FROM test_double1;
  ```

### 3.3 精度误差说明

浮点数类型有个缺陷，就是不精准。下面我来重点解释一下为什么 MySQL 的浮点数不够精准。比如，我们设计一个表，有 f1 这个字段，插入值分别为 0.47,0.44,0.19，我们期待的运行结果是：0.47 + 0.44 + 0.19 = 1.1。而使用 sum 之后查询：

```sql
CREATE TABLE test_double2
(
  f1 DOUBLE
);

INSERT INTO test_double2
VALUES(0.47),(0.44),(0.19);
```

```sh
mysql> SELECT SUM(f1)
    -> FROM test_double2;
+--------------------+
| SUM(f1)            |
+--------------------+
| 1.0999999999999999 |
+--------------------+
1 row in set (0.00 sec)
```

```sh
mysql> SELECT SUM(f1) = 1.1,1.1 = 1.1
    -> FROM test_double2;
+---------------+-----------+
| SUM(f1) = 1.1 | 1.1 = 1.1 |
+---------------+-----------+
|             0 |         1 |
+---------------+-----------+
1 row in set (0.00 sec)
```

查询结果是 1.0999999999999999。看到了吗？虽然误差很小，但确实有误差。 你也可以尝试把数据类型改成 FLOAT，然后运行求和查询，得到的是， 1.0999999940395355。显然，误差更大了。

那么，为什么会存在这样的误差呢？问题还是出在 MySQL 对浮点类型数据的存储方式上。

MySQL 用 4 个字节存储 FLOAT 类型数据，用 8 个字节来存储 DOUBLE 类型数据。无论哪个，都是采用二进制的方式来进行存储的。比如 9.625，用二进制来表达，就是 1001.101，或者表达成 1.001101×2^3。如果尾数不是 0 或 5（比如 9.624），你就无法用一个二进制数来精确表达。进而，就只好在取值允许的范围内进行四舍五入。

在编程中，如果用到浮点数，要特别注意误差问题，**因为浮点数是不准确的，所以我们要避免使用“=”来判断两个数是否相等。** 同时，在一些对精确度要求较高的项目中，千万不要使用浮点数，不然会导致结果错误，甚至是造成不可挽回的损失。那么，MySQL 有没有精准的数据类型呢？当然有，这就是定点数类型：`DECIMAL`。

## 4. 定点数类型

### 4.1 类型介绍

- MySQL 中的定点数类型只有 DECIMAL 一种类型。

  | 数据类型                 | 字节数   | 含义                     |
  | ------------------------ | -------- | ------------------------ |
  | DECIMAL(M,D),DEC,NUMERIC | M+2 字节 | 有效范围由 M 和 D 决定。 |

  使用 DECIMAL(M,D) 的方式表示高精度小数。其中，M 被称为精度，D 被称为标度。0<=M<=65，0<=D<=30，D<M。例如，定义 DECIMAL（5,2）的类型，表示该列取值范围是-999.99~999.99。

- **DECIMAL(M,D)的最大取值范围与 DOUBLE 类型一样**，但是有效的数据范围是由 M 和 D 决定的。DECIMAL 的存储空间并不是固定的，由精度值 M 决定，总共占用的存储空间为 M+2 个字节。也就是说，在一些对精度要求不高的场景下，比起占用同样字节长度的定点数，浮点数表达的数值范围可以更大一些。

- 定点数在 MySQL 内部是以`字符串`的形式进行存储，这就决定了它一定是精准的。

- 当 DECIMAL 类型不指定精度和标度时，其默认为 DECIMAL(10,0)。当数据的精度超出了定点数类型的精度范围时，则 MySQL 同样会进行四舍五入处理。

- **浮点数 vs 定点数**

  - 浮点数相对于定点数的优点是在长度一定的情况下，浮点类型取值范围大，但是不精准，适用于需要取值范围大，又可以容忍微小误差的科学计算场景（比如计算化学、分子建模、流体动力学等）
  - 定点数类型取值范围相对小，但是精准，没有误差，适合于对精度要求极高的场景 （比如涉及金额计算的场景）

- 举例

  ```sql
  CREATE TABLE test_decimal1
  (
    f1 DECIMAL,
    f2 DECIMAL(5,2)
  );

  DESC test_decimal1;

  INSERT INTO test_decimal1(f1,f2)
  VALUES(123.123,123.456);

  # Out of range value for column 'f2' at row 1
  INSERT INTO test_decimal1(f2)
  VALUES(1234.34);
  ```

  ```sh
  mysql> SELECT * FROM test_decimal1;
  +------+--------+
  | f1   | f2     |
  +------+--------+
  |  123 | 123.46 |
  +------+--------+
  1 row in set (0.00 sec)
  ```

- 举例

  我们运行下面的语句，把 test_double2 表中字段“f1”的数据类型修改为 DECIMAL(5,2)：

  ```sql
  ALTER TABLE test_double2
  MODIFY f1 DECIMAL(5,2);
  ```

  然后，我们再一次运行求和语句：

  ```sh
  mysql> SELECT SUM(f1)
      -> FROM test_double2;
  +---------+
  | SUM(f1) |
  +---------+
  |    1.10 |
  +---------+
  1 row in set (0.00 sec)
  ```

  ```sh
  mysql> SELECT SUM(f1) = 1.1
      -> FROM test_double2;
  +---------------+
  | SUM(f1) = 1.1 |
  +---------------+
  |             1 |
  +---------------+
  1 row in set (0.00 sec)
  ```

### 4.2 开发中经验

> “由于 DECIMAL 数据类型的精准性，在我们的项目中，除了极少数（比如商品编号）用到整数类型外，其他的数值都用的是 DECIMAL，原因就是这个项目所处的零售行业，要求精准，一分钱也不能差。 ” ——来自某项目经理

## 5. 位类型：BIT

BIT 类型中存储的是二进制值，类似 010110。

| 二进制字符串类型 | 长度 | 长度范围     | 占用空间             |
| ---------------- | ---- | ------------ | -------------------- |
| BIT(M)           | M    | 1 <= M <= 64 | 约为(M + 7)/8 个字节 |

BIT 类型，如果没有指定(M)，默认是 1 位。这个 1 位，表示只能存 1 位的二进制值。这里(M)是表示二进制的位数，位数最小值为 1，最大值为 64。

```sql
CREATE TABLE test_bit1
(
  f1 BIT,
  f2 BIT(5),
  f3 BIT(64)
);

INSERT INTO test_bit1(f1)
VALUES(1);

#Data too long for column 'f1' at row 1
INSERT INTO test_bit1(f1)
VALUES(2);

INSERT INTO test_bit1(f2)
VALUES(23);
```

注意：在向 BIT 类型的字段中插入数据时，一定要确保插入的数据在 BIT 类型支持的范围内。

使用 SELECT 命令查询位字段时，可以用`BIN()`或`HEX()`函数进行读取。

```sh
mysql> SELECT * FROM test_bit1;
+------------+------------+------------+
| f1         | f2         | f3         |
+------------+------------+------------+
| 0x01       | NULL       | NULL       |
| NULL       | 0x17       | NULL       |
+------------+------------+------------+
2 rows in set (0.00 sec)
```

```sh
mysql> SELECT BIN(f2),HEX(f2)
    -> FROM test_bit1;
+---------+---------+
| BIN(f2) | HEX(f2) |
+---------+---------+
| NULL    | NULL    |
| 10111   | 17      |
+---------+---------+
2 rows in set (0.00 sec)
```

```sh
mysql> SELECT f2 + 0
    -> FROM test_bit1;
+--------+
| f2 + 0 |
+--------+
|   NULL |
|     23 |
+--------+
2 rows in set (0.00 sec)
```

可以看到，使用 b+0 查询数据时，可以直接查询出存储的十进制数据的值。

## 6. 日期与时间类型

日期与时间是重要的信息，在我们的系统中，几乎所有的数据表都用得到。原因是客户需要知道数据的时间标签，从而进行数据查询、统计和处理。

MySQL 有多种表示日期和时间的数据类型，不同的版本可能有所差异，MySQL8.0 版本支持的日期和时间类型主要有：YEAR 类型、TIME 类型、DATE 类型、DATETIME 类型和 TIMESTAMP 类型。

- `YEAR`类型通常用来表示年。

- `DATE`类型通常用来表示年、月、日。

- `TIME`类型通常用来表示时、分、秒。

- `DATETIME`类型通常用来表示年、月、日、时、分、秒。

- `TIMESTAMP`类型通常用来表示带时区的年、月、日、时、分、秒。

| 类型      | 名称     | 字节 | 日期格式            | 最小值                  | 最大值                 |
| --------- | -------- | ---- | ------------------- | ----------------------- | ---------------------- |
| YEAR      | 年       | 1    | YYYY 或 YY          | 1901                    | 2155                   |
| TIME      | 时间     | 3    | HH:MM:SS            | -838:59:59              | 838:59:59              |
| DATE      | 日期     | 3    | YYYY-MM-DD          | 1000-01-01              | 9999-12-03             |
| DATETIME  | 日期时间 | 8    | YYYY-MM-DD HH:MM:SS | 1000-01-01 00:00:00     | 9999-12-31 23:59:59    |
| TIMESTAMP | 日期时间 | 4    | YYYY-MM-DD HH:MM:SS | 1970-01-01 00:00:00 UTC | 2038-01-19 03:14:07UTC |

可以看到，不同数据类型表示的时间内容不同、取值范围不同，而且占用的字节数也不一样，你要根据实际需要灵活选取。

为什么时间类型 TIME 的取值范围不是 -23:59:59 ～ 23:59:59 呢？原因是 MySQL 设计的 TIME 类型，不光表示一天之内的时间，而且可以用来表示一个时间间隔，这个时间间隔可以超过 24 小时。

### 6.1 YEAR 类型

YEAR 类型用来表示年份，在所有的日期时间类型中所占用的存储空间最小，只需要`1个字节`的存储空间。

在 MySQL 中，YEAR 有以下几种存储格式：

- 以 4 位字符串或数字格式表示 YEAR 类型，其格式为 YYYY，最小值为 1901，最大值为 2155。

- 以 2 位字符串格式表示 YEAR 类型，最小值为 00，最大值为 99。

  - 当取值为 01 到 69 时，表示 2001 到 2069；

  - 当取值为 70 到 99 时，表示 1970 到 1999；

  - 当取值整数的 0 或 00 添加的话，那么是 0000 年；

  - 当取值是日期/字符串的'0'添加的话，是 2000 年。

**从 MySQL5.5.27 开始，2 位格式的 YEAR 已经不推荐使用**。YEAR 默认格式就是“YYYY”，没必要写成 YEAR(4)，从 MySQL 8.0.19 开始，不推荐使用指定显示宽度的 YEAR(4)数据类型。

```sql
CREATE TABLE test_year
(
  f1 YEAR,
  f2 YEAR(4)
);
```

```sh
mysql> DESC test_year;
+-------+---------+------+-----+---------+-------+
| Field | Type    | Null | Key | Default | Extra |
+-------+---------+------+-----+---------+-------+
| f1    | year(4) | YES  |     | NULL    |       |
| f2    | year(4) | YES  |     | NULL    |       |
+-------+---------+------+-----+---------+-------+
2 rows in set (0.00 sec)
```

```sql
INSERT INTO test_year
VALUES('2020','2021');
```

```sh
mysql> SELECT * FROM test_year;
+------+------+
| f1   | f2   |
+------+------+
| 2020 | 2021 |
+------+------+
1 rows in set (0.00 sec)
```

````sql
INSERT INTO test_year
VALUES('45','71');

INSERT INTO test_year
VALUES(0,'0');

```sh
mysql> SELECT * FROM test_year;
+------+------+
| f1   | f2   |
+------+------+
| 2020 | 2021 |
| 2045 | 1971 |
| 0000 | 2000 |
+------+------+
3 rows in set (0.00 sec)
````

### 6.2 DATE 类型

DATE 类型表示日期，没有时间部分，格式为`YYYY-MM-DD`，其中，YYYY 表示年份，MM 表示月份，DD 表示日期。需要`3个字节`的存储空间。在向 DATE 类型的字段插入数据时，同样需要满足一定的格式条件。

- 以`YYYY-MM-DD`格式或者`YYYYMMDD`格式表示的字符串日期，其最小取值为 1000-01-01，最大取值为 9999-12-03。YYYYMMDD 格式会被转化为 YYYY-MM-DD 格式。

- 以`YY-MM-DD`格式或者`YYMMDD`格式表示的字符串日期，此格式中，年份为两位数值或字符串满足 YEAR 类型的格式条件为：当年份取值为 00 到 69 时，会被转化为 2000 到 2069；当年份取值为 70 到 99 时，会被转化为 1970 到 1999。

- 使用`CURRENT_DATE()`或者`NOW()`函数，会插入当前系统的日期。

**举例：**

创建数据表，表中只包含一个 DATE 类型的字段 f1。

```sql
CREATE TABLE test_date1
(
  f1 DATE
);
Query OK, 0 rows affected (0.13 sec)
```

插入数据：

```sql
INSERT INTO test_date1
VALUES ('2020-10-01'), ('20201001'),(20201001);

INSERT INTO test_date1
VALUES ('00-01-01'), ('000101'), ('69-10-01'), ('691001'), ('70-01-01'), ('700101'), ('99-01-01'), ('990101');

INSERT INTO test_date1
VALUES (000301), (690301), (700301), (990301);

INSERT INTO test_date1
VALUES (CURRENT_DATE()), (NOW());

SELECT *
FROM test_date1;
```

### 6.3 TIME 类型

TIME 类型用来表示时间，不包含日期部分。在 MySQL 中，需要`3个字节`的存储空间来存储 TIME 类型的数据，可以使用“HH:MM:SS”格式来表示 TIME 类型，其中，HH 表示小时，MM 表示分钟，SS 表示秒。

在 MySQL 中，向 TIME 类型的字段插入数据时，也可以使用几种不同的格式。
（1）可以使用带有冒号的字符串，比如'`D HH:MM:SS'`、'`HH:MM:SS`'、'`HH:MM`'、'`D HH:MM`'、'`D HH`'或'`SS`'格式，都能被正确地插入 TIME 类型的字段中。其中 D 表示天，其最小值为 0，最大值为 34。如果使用带有 D 格式的字符串插入 TIME 类型的字段时，D 会被转化为小时，计算格式为 D\*24+HH。当使用带有冒号并且不带 D 的字符串表示时间时，表示当天的时间，比如 12:10 表示 12:10:00，而不是 00:12:10。
（2）可以使用不带有冒号的字符串或者数字，格式为'`HHMMSS`'或者`HHMMSS`。如果插入一个不合法的字符串或者数字，MySQL 在存储数据时，会将其自动转化为 00:00:00 进行存储。比如 1210，MySQL 会将最右边的两位解析成秒，表示 00:12:10，而不是 12:10:00。
（3）使用`CURRENT_TIME()`或者`NOW()`，会插入当前系统的时间。

**举例：**

创建数据表，表中包含一个 TIME 类型的字段 f1。

```sql
CREATE TABLE test_time1
(
  f1 TIME
);
Query OK, 0 rows affected (0.02 sec)
```

```sql
INSERT INTO test_time1
VALUES('2 12:30:29'), ('12:35:29'), ('12:40'), ('2 12:40'),('1 05'), ('45');

INSERT INTO test_time1
VALUES ('123520'), (124011),(1210);

INSERT INTO test_time1
VALUES (NOW()), (CURRENT_TIME());

SELECT * FROM test_time1;
```

### 6.4 DATETIME 类型

DATETIME 类型在所有的日期时间类型中占用的存储空间最大，总共需要`8`个字节的存储空间。在格式上为 DATE 类型和 TIME 类型的组合，可以表示为`YYYY-MM-DD HH:MM:SS`，其中 YYYY 表示年份，MM 表示月份，DD 表示日期，HH 表示小时，MM 表示分钟，SS 表示秒。

在向 DATETIME 类型的字段插入数据时，同样需要满足一定的格式条件。

- 以`YYYY-MM-DD HH:MM:SS`格式或者`YYYYMMDDHHMMSS`格式的字符串插入 DATETIME 类型的字段时，最小值为 1000-01-01 00:00:00，最大值为 9999-12-03 23:59:59。

  - 以 YYYYMMDDHHMMSS 格式的数字插入 DATETIME 类型的字段时，会被转化为 YYYY-MM-DD HH:MM:SS 格式。

- 以`YY-MM-DD HH:MM:SS`格式或者`YYMMDDHHMMSS`格式的字符串插入 DATETIME 类型的字段时，两位数的年份规则符合 YEAR 类型的规则，00 到 69 表示 2000 到 2069；70 到 99 表示 1970 到 1999。

- 使用函数`CURRENT_TIMESTAMP()`和`NOW()`，可以向 DATETIME 类型的字段插入系统的当前日期和时间。

**举例：**

创建数据表，表中包含一个 DATETIME 类型的字段 dt。

```sql
CREATE TABLE test_datetime1
(
  dt DATETIME
);
Query OK, 0 rows affected (0.02 sec)
```

插入数据：

```sql
INSERT INTO test_datetime1
VALUES ('2021-01-01 06:50:30'), ('20210101065030');

INSERT INTO test_datetime1
VALUES ('99-01-01 00:00:00'), ('990101000000'), ('20-01-01 00:00:00'), ('200101000000');

INSERT INTO test_datetime1
VALUES (20200101000000), (200101000000), (19990101000000), (990101000000);

INSERT INTO test_datetime1
VALUES (CURRENT_TIMESTAMP()), (NOW());
```

### 6.5 TIMESTAMP 类型

TIMESTAMP 类型也可以表示日期时间，其显示格式与 DATETIME 类型相同，都是`YYYY-MM-DD HH:MM:SS`，需要 4 个字节的存储空间。但是 TIMESTAMP 存储的时间范围比 DATETIME 要小很多，只能存储“1970-01-01 00:00:01 UTC”到“2038-01-19 03:14:07 UTC”之间的时间。其中，UTC 表示世界统一时间，也叫作世界标准时间。

- **存储数据的时候需要对当前时间所在的时区进行转换，查询数据的时候再将时间转换回当前的时区。因此，使用 TIMESTAMP 存储的同一个时间值，在不同的时区查询时会显示不同的时间。**

向 TIMESTAMP 类型的字段插入数据时，当插入的数据格式满足 YY-MM-DD HH:MM:SS 和 YYMMDDHHMMSS 时，两位数值的年份同样符合 YEAR 类型的规则条件，只不过表示的时间范围要小很多。

如果向 TIMESTAMP 类型的字段插入的时间超出了 TIMESTAMP 类型的范围，则 MySQL 会抛出错误信息。

**举例：**

创建数据表，表中包含一个 TIMESTAMP 类型的字段 ts。

```sql
CREATE TABLE test_timestamp1
(
  ts TIMESTAMP
);
```

插入数据：

```sql
INSERT INTO test_timestamp1
VALUES ('1999-01-01 03:04:50'), ('19990101030405'), ('99-01-01 03:04:05'), ('990101030405');

INSERT INTO test_timestamp1
VALUES ('2020@01@01@00@00@00'), ('20@01@01@00@00@00');

INSERT INTO test_timestamp1
VALUES (CURRENT_TIMESTAMP()), (NOW());

#Incorrect datetime value
INSERT INTO test_timestamp1
VALUES ('2038-01-20 03:14:07');
```

**TIMESTAMP 和 DATETIME 的区别：**

- TIMESTAMP 存储空间比较小，表示的日期时间范围也比较小。

- 底层存储方式不同，TIMESTAMP 底层存储的是毫秒值，距离 1970-1-1 0:0:0 0 毫秒的毫秒值。

- 两个日期比较大小或日期计算时，TIMESTAMP 更方便、更快。

- TIMESTAMP 和时区有关。TIMESTAMP 会根据用户的时区不同，显示不同的结果。而 DATETIME 则只能反映出插入时当地的时区，其他时区的人查看数据必然会有误差的。

  ```sql
  CREATE TABLE temp_time
  (
    d1 DATETIME,
    d2 TIMESTAMP
  );
  ```

  ```sql
  INSERT INTO temp_time VALUES('2021-9-2 14:45:52','2021-9-2 14:45:52');

  INSERT INTO temp_time VALUES(NOW(),NOW());
  ```

  ```sh
  mysql> SELECT * FROM temp_time;
  +---------------------+---------------------+
  | d1                  | d2                  |
  +---------------------+---------------------+
  | 2021-09-02 14:45:52 | 2021-09-02 14:45:52 |
  | 2021-11-03 17:38:17 | 2021-11-03 17:38:17 |
  +---------------------+---------------------+
  2 rows in set (0.00 sec)
  ```

  ```sql
  # 修改当前的时区
  SET time_zone = '+9:00';
  ```

  ```sh
  mysql> SELECT * FROM temp_time;
  +---------------------+---------------------+
  | d1                  | d2                  |
  +---------------------+---------------------+
  | 2021-09-02 14:45:52 | 2021-09-02 15:45:52 |
  | 2021-11-03 17:38:17 | 2021-11-03 18:38:17 |
  +---------------------+---------------------+
  2 rows in set (0.00 sec)
  ```

### 6.6 开发中经验

用得最多的日期时间类型，就是 `DATETIME`。虽然 MySQL 也支持 YEAR（年）、 TIME（时间）、DATE（日期），以及 TIMESTAMP 类型，但是在实际项目中，尽量用 DATETIME 类型。因为这个数据类型包括了完整的日期和时间信息，取值范围也最大，使用起来比较方便。毕竟，如果日期时间信息分散在好几个字段，很不容易记，而且查询的时候，SQL 语句也会更加复杂。

此外，一般存注册时间、商品发布时间等，不建议使用 DATETIME 存储，而是使用`时间戳`，因为 DATETIME 虽然直观，但不便于计算。

```sh
mysql> SELECT UNIX_TIMESTAMP();
+------------------+
| UNIX_TIMESTAMP() |
+------------------+
|       1635932762 |
+------------------+
1 row in set (0.00 sec)
```

## 7. 文本字符串类型

在实际的项目中，我们还经常遇到一种数据，就是字符串数据。

MySQL 中，文本字符串总体上分为`CHAR`、`VARCHAR`、`TINYTEXT`、`TEXT`、`MEDIUMTEXT`、`LONGTEXT`、`ENUM`、`SET`等类型。

![文本字符串类型](https://img-blog.csdnimg.cn/a9b933af39b1490ab0609e2850102de7.png)

### 7.1 CHAR 与 VARCHAR 类型

CHAR 和 VARCHAR 类型都可以存储比较短的字符串。

| 字符串(文本)类型 | 特点     | 长度 | 长度范围        | 占用的存储空间        |
| ---------------- | -------- | ---- | --------------- | --------------------- |
| CHAR(M)          | 固定长度 | M    | 0 <= M <= 255   | M 个字节              |
| VARCHAR(M)       | 可变长度 | M    | 0 <= M <= 65535 | (实际长度 + 1) 个字节 |

**CHAR 类型：**

- CHAR(M) 类型一般需要预先定义字符串长度。如果不指定(M)，则表示长度默认是 1 个字符。

- 如果保存时，数据的实际长度比 CHAR 类型声明的长度小，则会在`右侧填充`空格以达到指定的长度。当 MySQL 检索 CHAR 类型的数据时，CHAR 类型的字段会去除尾部的空格。

- 定义 CHAR 类型字段时，声明的字段长度即为 CHAR 类型字段所占的存储空间的字节数。

  ```sql
  CREATE TABLE test_char1
  (
    c1 CHAR,
    c2 CHAR(5)
  );

  DESC test_char1;
  ```

  ```sql
  INSERT INTO test_char1
  VALUES('a','Tom');

  SELECT c1,CONCAT(c2,'***') FROM test_char1;
  ```

  ```sql
  INSERT INTO test_char1(c2)
  VALUES('a');

  SELECT CHAR_LENGTH(c2)
  FROM test_char1;
  ```

**VARCHAR 类型：**

- VARCHAR(M) 定义时，`必须指定`长度 M，否则报错。

- MySQL4.0 版本以下，varchar(20)：指的是 20 字节，如果存放 UTF8 汉字时，只能存 6 个（每个汉字 3 字节） ；MySQL5.0 版本以上，varchar(20)：指的是 20 字符。

- 检索 VARCHAR 类型的字段数据时，会保留数据尾部的空格。VARCHAR 类型的字段所占用的存储空间为字符串实际长度加 1 个字节。

  ```sql
  CREATE TABLE test_varchar1
  (
    # 错误
    NAME VARCHAR
  );
  ```

  ```sql
  # Column length too big for column 'NAME' (max = 21845);
  CREATE TABLE test_varchar2
  (
    # 错误
    NAME VARCHAR(65535)
  );
  ```

  ```sql
  CREATE TABLE test_varchar3
  (
    NAME VARCHAR(5)
  );

  INSERT INTO test_varchar3
  VALUES('MYXH'),('末影小黑xh');

  #Data too long for column 'NAME' at row 1
  INSERT INTO test_varchar3
  VALUES('末影小黑xh');
  ```

**哪些情况使用 CHAR 或 VARCHAR 更好**

| 类型       | 特点     | 空间上       | 时间上 | 适用场景             |
| ---------- | -------- | ------------ | ------ | -------------------- |
| CHAR(M)    | 固定长度 | 浪费存储空间 | 效率高 | 存储不大，速度要求高 |
| VARCHAR(M) | 可变长度 | 节省存储空间 | 效率低 | 非 CHAR 的情况       |

情况 1：存储很短的信息。比如门牌号码 101，201……这样很短的信息应该用 char，因为 varchar 还要占个 byte 用于存储信息长度，本来打算节约存储的，结果得不偿失。

情况 2：固定长度的。比如使用 uuid 作为主键，那用 char 应该更合适。因为他固定长度，varchar 动态根据长度的特性就消失了，而且还要占个长度信息。

情况 3：十分频繁改变的 column。因为 varchar 每次存储都要有额外的计算，得到长度等工作，如果一个非常频繁改变的，那就要有很多的精力用于计算，而这些对于 char 来说是不需要的。

情况 4：具体存储引擎中的情况：

- `MyISAM` 数据存储引擎和数据列：MyISAM 数据表，最好使用固定长度(CHAR)的数据列代替可变长度(VARCHAR)的数据列。这样使得整个表静态化，从而使`数据检索更快`，用空间换时间。

- `MEMORY` 存储引擎和数据列：MEMORY 数据表目前都使用固定长度的数据行存储，因此无论使用 CHAR 或 VARCHAR 列都没有关系，两者都是作为 CHAR 类型处理的。

- `InnoDB`存储引擎，建议使用 VARCHAR 类型。因为对于 InnoDB 数据表，内部的行存储格式并没有区分固定长度和可变长度列（所有数据行都使用指向数据列值的头指针），而且**主要影响性能的因素是数据行使用的存储总量**，由于 char 平均占用的空间多于 varchar，所以除了简短并且固定长度的，其他考虑 varchar。这样节省空间，对磁盘 I/O 和数据存储总量比较好。

### 7.2 TEXT 类型

在 MySQL 中，TEXT 用来保存文本类型的字符串，总共包含 4 种类型，分别为 TINYTEXT、TEXT、MEDIUMTEXT 和 LONGTEXT 类型。

在向 TEXT 类型的字段保存和查询数据时，系统自动按照实际长度存储，不需要预先定义长度。这一点和 VARCHAR 类型相同。

每种 TEXT 类型保存的数据长度和所占用的存储空间不同，如下：

| 文本字符串类型 | 特点               | 长度 | 长度范围                          | 占用的存储空间 |
| -------------- | ------------------ | ---- | --------------------------------- | -------------- |
| TINYTEXT       | 小文本、可变长度   | L    | 0 <= L <= 255                     | L + 2 个字节   |
| TEXT           | 文本、可变长度     | L    | 0 <= L <= 65535                   | L + 2 个字节   |
| MEDIUMTEXT     | 中等文本、可变长度 | L    | 0 <= L <= 16777215                | L + 3 个字节   |
| LONGTEXT       | 大文本、可变长度   | L    | 0 <= L<= 4294967295（相当于 4GB） | L + 4 个字节   |

**由于实际存储的长度不确定，MySQL 不允许 TEXT 类型的字段做主键**。遇到这种情况，你只能采用 CHAR(M)，或者 VARCHAR(M)。

**举例：**

创建数据表：

```sql
CREATE TABLE test_text
(
  tx TEXT
);
```

```sql
INSERT INTO test_text
VALUES('myxh   ');

SELECT CHAR_LENGTH(tx)
FROM test_text; #10
```

说明在保存和查询数据时，并没有删除 TEXT 类型的数据尾部的空格。

**开发中经验：**

TEXT 文本类型，可以存比较大的文本段，搜索速度稍慢，因此如果不是特别大的内容，建议使用 CHAR，VARCHAR 来代替。还有 TEXT 类型不用加默认值，加了也没用。而且 text 和 blob 类型的数据删除后容易导致“空洞”，使得文件碎片比较多，所以频繁使用的表不建议包含 TEXT 类型字段，建议单独分出去，单独用一个表。

## 8. ENUM 类型

ENUM 类型也叫作枚举类型，ENUM 类型的取值范围需要在定义字段时进行指定。设置字段值时，ENUM 类型只允许从成员中选取单个值，不能一次选取多个值。

其所需要的存储空间由定义 ENUM 类型时指定的成员个数决定。

| 文本字符串类型 | 长度 | 长度范围        | 占用的存储空间 |
| -------------- | ---- | --------------- | -------------- |
| ENUM           | L    | 1 <= L <= 65535 | 1 或 2 个字节  |

- 当 ENUM 类型包含 1 ～ 255 个成员时，需要 1 个字节的存储空间；

- 当 ENUM 类型包含 256 ～ 65535 个成员时，需要 2 个字节的存储空间。
- ENUM 类型的成员个数的上限为 65535 个。

举例：

创建表如下：

```sql
CREATE TABLE test_enum
(
  season ENUM('春','夏','秋','冬','unknow')
);
```

添加数据：

```sql
INSERT INTO test_enum
VALUES('春'),('秋');

# 忽略大小写
INSERT INTO test_enum
VALUES('UNKNOW');

# 允许按照角标的方式获取指定索引位置的枚举值
INSERT INTO test_enum
VALUES('1'),(3);

# Data truncated for column 'season' at row 1
INSERT INTO test_enum
VALUES('ab');

# 当 ENUM 类型的字段没有声明为 NOT NULL 时，插入 NULL 也是有效的
INSERT INTO test_enum
VALUES(NULL);
```

## 9. SET 类型

SET 表示一个字符串对象，可以包含 0 个或多个成员，但成员个数的上限为`64`。设置字段值时，可以取取值范围内的 0 个或多个值。

当 SET 类型包含的成员个数不同时，其所占用的存储空间也是不同的，具体如下：

| 成员个数范围（L 表示实际成员个数） | 占用的存储空间 |
| ---------------------------------- | -------------- |
| 1 <= L <= 8                        | 1 个字节       |
| 9 <= L <= 16                       | 2 个字节       |
| 17 <= L <= 24                      | 3 个字节       |
| 25 <= L <= 32                      | 4 个字节       |
| 33 <= L <= 64                      | 8 个字节       |

SET 类型在存储数据时成员个数越多，其占用的存储空间越大。注意：SET 类型在选取成员时，可以一次选择多个成员，这一点与 ENUM 类型不同。

举例：

创建表：

```sql
CREATE TABLE test_set
(
  s SET ('A', 'B', 'C')
);
```

向表中插入数据：

```sql
INSERT INTO test_set (s) VALUES ('A'), ('A,B');

# 插入重复的 SET 类型成员时，MySQL 会自动删除重复的成员
INSERT INTO test_set (s) VALUES ('A,B,C,A');

#向 SET 类型的字段插入 SET 成员中不存在的值时，MySQL 会抛出错误。
INSERT INTO test_set (s) VALUES ('A,B,C,D');

SELECT *
FROM test_set;
```

举例：

```sql
CREATE TABLE temp_mul
(
  gender ENUM('男','女'),
  hobby SET('吃饭','睡觉','打豆豆','写代码')
);
```

```sql
#成功
INSERT INTO temp_mul VALUES('男','睡觉,打豆豆');

# Data truncated for column 'gender' at row 1
#失败
INSERT INTO temp_mul VALUES('男,女','睡觉,写代码');

# Data truncated for column 'gender' at row 1
# 失败
INSERT INTO temp_mul VALUES('妖','睡觉,写代码');

# 成功
INSERT INTO temp_mul VALUES('男','睡觉,写代码,吃饭');
```

## 10. 二进制字符串类型

MySQL 中的二进制字符串类型主要存储一些二进制数据，比如可以存储图片、音频和视频等二进制数据。

MySQL 中支持的二进制字符串类型主要包括 BINARY、VARBINARY、TINYBLOB、BLOB、MEDIUMBLOB 和 LONGBLOB 类型。

#### BINARY 与 VARBINARY 类型

BINARY 和 VARBINARY 类似于 CHAR 和 VARCHAR，只是它们存储的是二进制字符串。

BINARY (M)为固定长度的二进制字符串，M 表示最多能存储的字节数，取值范围是 0~255 个字符。如果未指定(M)，表示只能存储`1个字节`。例如 BINARY (8)，表示最多能存储 8 个字节，如果字段值不足(M)个字节，将在右边填充'\0'以补齐指定长度。

VARBINARY (M)为可变长度的二进制字符串，M 表示最多能存储的字节数，总字节数不能超过行的字节长度限制 65535，另外还要考虑额外字节开销，VARBINARY 类型的数据除了存储数据本身外，还需要 1 或 2 个字节来存储数据的字节数。VARBINARY 类型`必须指定(M)`，否则报错。

| 二进制字符串类型 | 特点     | 值的长度             | 占用空间   |
| ---------------- | -------- | -------------------- | ---------- |
| BINARY(M)        | 固定长度 | M （0 <= M <= 255）  | M 个字节   |
| VARBINARY(M)     | 可变长度 | M（0 <= M <= 65535） | M+1 个字节 |

举例：

创建表：

```sql
CREATE TABLE test_binary1
(
  f1 BINARY,
  f2 BINARY(3),

  # f3 VARBINARY,
  f4 VARBINARY(10)
);
```

添加数据：

```sql
INSERT INTO test_binary1(f1,f2)
VALUES('a','a');

INSERT INTO test_binary1(f1,f2)

# 失败
VALUES('b','b');
```

```sql
INSERT INTO test_binary1(f2,f4)
VALUES('ab','ab');
```

```sh
mysql> SELECT LENGTH(f2),LENGTH(f4)
    -> FROM test_binary1;
+------------+------------+
| LENGTH(f2) | LENGTH(f4) |
+------------+------------+
|          3 |       NULL |
|          3 |          2 |
+------------+------------+
2 rows in set (0.00 sec)
```

#### BLOB 类型

BLOB 是一个`二进制大对象`，可以容纳可变数量的数据。

MySQL 中的 BLOB 类型包括 TINYBLOB、BLOB、MEDIUMBLOB 和 LONGBLOB 4 种类型，它们可容纳值的最大长度不同。可以存储一个二进制的大对象，比如`图片`、`音频`和`视频`等。

需要注意的是，在实际工作中，往往不会在 MySQL 数据库中使用 BLOB 类型存储大对象数据，通常会将图片、音频和视频文件存储到`服务器的磁盘上`，并将图片、音频和视频的访问路径存储到 MySQL 中。

| 二进制字符串类型 | 值的长度 | 长度范围                           | 占用空间     |
| ---------------- | -------- | ---------------------------------- | ------------ |
| TINYBLOB         | L        | 0 <= L <= 255                      | L + 1 个字节 |
| BLOB             | L        | 0 <= L <= 65535（相当于 64KB）     | L + 2 个字节 |
| MEDIUMBLOB       | L        | 0 <= L <= 16777215 （相当于 16MB） | L + 3 个字节 |
| LONGBLOB         | L        | 0 <= L <= 4294967295（相当于 4GB） | L + 4 个字节 |

举例：

```sql
CREATE TABLE test_blob1
(
  id INT,
  img MEDIUMBLOB
);
```

**TEXT 和 BLOB 的使用注意事项：**

在使用 text 和 blob 字段类型时要注意以下几点，以便更好的发挥数据库的性能。

① BLOB 和 TEXT 值也会引起自己的一些问题，特别是执行了大量的删除或更新操作的时候。删除这种值会在数据表中留下很大的"`空洞`"，以后填入这些"空洞"的记录可能长度不同。为了提高性能，建议定期使用 OPTIMIZE TABLE 功能对这类表进行`碎片整理`。

② 如果需要对大文本字段进行模糊查询，MySQL 提供了`前缀索引`。但是仍然要在不必要的时候避免检索大型的 BLOB 或 TEXT 值。例如，SELECT \* 查询就不是很好的想法，除非你能够确定作为约束条件的 WHERE 子句只会找到所需要的数据行。否则，你可能毫无目的地在网络上传输大量的值。

③ 把 BLOB 或 TEXT 列`分离到单独的表`中。在某些环境中，如果把这些数据列移动到第二张数据表中，可以让你把原数据表中的数据列转换为固定长度的数据行格式，那么它就是有意义的。这会`减少主表中的碎片`，使你得到固定长度数据行的性能优势。它还使你在主数据表上运行 SELECT \* 查询的时候不会通过网络传输大量的 BLOB 或 TEXT 值。

## 11. JSON 类型

JSON（JavaScript Object Notation）是一种轻量级的`数据交换格式`。简洁和清晰的层次结构使得 JSON 成为理想的数据交换语言。它易于人阅读和编写，同时也易于机器解析和生成，并有效地提升网络传输效率。**JSON 可以将 JavaScript 对象中表示的一组数据转换为字符串，然后就可以在网络或者程序之间轻松地传递这个字符串，并在需要的时候将它还原为各编程语言所支持的数据格式。**

在 MySQL 5.7 中，就已经支持 JSON 数据类型。在 MySQL 8.x 版本中，JSON 类型提供了可以进行自动验证的 JSON 文档和优化的存储结构，使得在 MySQL 中存储和读取 JSON 类型的数据更加方便和高效。

创建数据表，表中包含一个 JSON 类型的字段 js 。

```sql
CREATE TABLE test_json
(
  js json
);
```

向表中插入 JSON 数据。

```sql
INSERT INTO test_json (js)
VALUES ('{"name":"songhk", "age":18, "address":{"province":"beijing", "city":"beijing"}}');
```

查询 t19 表中的数据。

```sh
mysql> SELECT *
    -> FROM test_json;
```

![JSON 类型](https://img-blog.csdnimg.cn/74b9c7209d134795b4ac63ce30101e34.png)

当需要检索 JSON 类型的字段中数据的某个具体值时，可以使用“->”和“->>”符号。

```sh
mysql> SELECT js -> '$.name' AS NAME,js -> '$.age' AS age ,js -> '$.address.province' AS province, js -> '$.address.city' AS city
    -> FROM test_json;
+----------+------+-----------+-----------+
| NAME     | age  | province  | city      |
+----------+------+-----------+-----------+
| "songhk" | 18   | "beijing" | "beijing" |
+----------+------+-----------+-----------+
1 row in set (0.00 sec)
```

通过“->”和“->>”符号，从 JSON 字段中正确查询出了指定的 JSON 数据的值。

## 12. 空间类型

MySQL 空间类型扩展支持地理特征的生成、存储和分析。这里的地理特征表示世界上具有位置的任何东西，可以是一个实体，例如一座山；可以是空间，例如一座办公楼；也可以是一个可定义的位置，例如一个十字路口等等。MySQL 中使用`Geometry（几何）`来表示所有地理特征。Geometry 指一个点或点的集合，代表世界上任何具有位置的事物。

MySQL 的空间数据类型（Spatial Data Type）对应于 OpenGIS 类，包括单值类型：GEOMETRY、POINT、LINESTRING、POLYGON 以及集合类型：MULTIPOINT、MULTILINESTRING、MULTIPOLYGON、GEOMETRYCOLLECTION 。

- Geometry 是所有空间集合类型的基类，其他类型如 POINT、LINESTRING、POLYGON 都是 Geometry 的子类。

  - Point，顾名思义就是点，有一个坐标值。例如 POINT(121.213342 31.234532)，POINT(30 10)，坐标值支持 DECIMAL 类型，经度（longitude）在前，维度（latitude）在后，用空格分隔。

  - LineString，线，由一系列点连接而成。如果线从头至尾没有交叉，那就是简单的（simple）；如果起点和终点重叠，那就是封闭的（closed）。例如 LINESTRING(30 10,10 30,40 40)，点与点之间用逗号分隔，一个点中的经纬度用空格分隔，与 POINT 格式一致。

  - Polygon，多边形。可以是一个实心平面形，即没有内部边界，也可以有空洞，类似纽扣。最简单的就是只有一个外边界的情况，例如 POLYGON((0 0,10 0,10 10, 0 10))。

下面展示几种常见的几何图形元素：

![空间类型](https://img-blog.csdnimg.cn/2979ae9151174da5b322bd0b84cb5f00.png)

- MultiPoint、MultiLineString、MultiPolygon、GeometryCollection 这 4 种类型都是集合类，是多个 Point、LineString 或 Polygon 组合而成。

下面展示的是多个同类或异类几何图形元素的组合：

![空间类型](https://img-blog.csdnimg.cn/7f0f1990c213443dbebf7214f98e10fd.png)

## 13. 小结及选择建议

在定义数据类型时，如果确定是`整数`，就用` INT`； 如果是`小数`，一定用定点数类型 `DECIMAL(M,D)`； 如果是日期与时间，就用 `DATETIME`。

这样做的好处是，首先确保你的系统不会因为数据类型定义出错。不过，凡事都是有两面的，可靠性好，并不意味着高效。比如，TEXT 虽然使用方便，但是效率不如 CHAR(M) 和 VARCHAR(M)。

关于字符串的选择，建议参考如下阿里巴巴的《Java 开发手册》规范：

**阿里巴巴《Java 开发手册》之 MySQL 数据库：**

- 任何字段如果为非负数，必须是 UNSIGNED。

- 【`强制`】小数类型为 DECIMAL，禁止使用 FLOAT 和 DOUBLE。

  - 说明：在存储的时候，FLOAT 和 DOUBLE 都存在精度损失的问题，很可能在比较值的时候，得到不正确的结果。如果存储的数据范围超过 DECIMAL 的范围，建议将数据拆成整数和小数并分开存储。

- 【`强制`】如果存储的字符串长度几乎相等，使用 CHAR 定长字符串类型。

- 【`强制`】VARCHAR 是可变长字符串，不预先分配存储空间，长度不要超过 5000。如果存储长度大于此值，定义字段类型为 TEXT，独立出来一张表，用主键来对应，避免影响其它字段索引效率。

# 第 13 章 约束

## 1. 约束(constraint)概述

### 1.1 为什么需要约束

数据完整性（Data Integrity）是指数据的精确性（Accuracy）和可靠性（Reliability）。它是防止数据库中存在不符合语义规定的数据和防止因错误信息的输入输出造成无效操作或错误信息而提出的。

为了保证数据的完整性，SQL 规范以约束的方式对**表数据进行额外的条件限制**。从以下四个方面考虑：

- `实体完整性（Entity Integrity）`：例如，同一个表中，不能存在两条完全相同无法区分的记录。

- `域完整性（Domain Integrity）`：例如：年龄范围 0-120，性别范围“男/女”。

- `引用完整性（Referential Integrity）`：例如：员工所在部门，在部门表中要能找到这个部门。

- `用户自定义完整性（User-defined Integrity）`：例如：用户名唯一、密码不能为空等，本部门经理的工资不得高于本部门职工的平均工资的 5 倍。

### 1.2 什么是约束

约束是表级的强制规定。

可以在**创建表时规定约束（通过 CREATE TABLE 语句）**，或者在**表创建之后通过 ALTER TABLE 语句规定约束**。

### 1.3 约束的分类

- **根据约束数据列的限制，** 约束可分为：

  - **单列约束**：每个约束只约束一列。

  - **多列约束**：每个约束可约束多列数据。

- **根据约束的作用范围**，约束可分为：

  - **列级约束**：只能作用在一个列上，跟在列的定义后面。

  - **表级约束**：可以作用在多个列上，不与列一起，而是单独定义。

以下是将内容转换为 Markdown 表格格式的示例：

|          | 位置         | 支持的约束类型               | 是否可以起约束名     |
| -------- | ------------ | ---------------------------- | -------------------- |
| 列级约束 | 列的后面     | 语法都支持，但外键没有效果。 | 不可以               |
| 表级约束 | 所有列的下面 | 默认和非空不支持，其他支持。 | 可以（主键没有效果） |

- **根据约束起的作用**，约束可分为：

  - **NOT NULL** **非空约束，规定某个字段不能为空**。

  - **UNIQUE** **唯一约束**，**规定某个字段在整个表中是唯一的**。

  - **PRIMARY KEY 主键(非空且唯一)约束**。

  - **FOREIGN KEY** **外键约束**。

  - **CHECK** **检查约束**。

  - **DEFAULT** **默认值约束**。

> 注意： MySQL 不支持 check 约束，但可以使用 check 约束，而没有任何效果

- 查看某个表已有的约束。

  ```sql
  # information_schema 数据库名（系统库）
  # table_constraints 表名称（专门存储各个表的约束）
  SELECT * FROM information_schema.table_constraints
  WHERE table_name = '表名称';
  ```

## 2. 非空约束

### 2.1 作用

限定某个字段/某列的值不允许为空。

![作用](https://img-blog.csdnimg.cn/8d3e835b226b4a189ee5056934df987a.png)

### 2.2 关键字

NOT NULL

### 2.3 特点

- 默认，所有的类型的值都可以是 NULL，包括 INT、FLOAT 等数据类型。

- 非空约束只能出现在表对象的列上，只能某个列单独限定非空，不能组合非空。

- 一个表可以有很多列都分别限定了非空。

- 空字符串''不等于 NULL，0 也不等于 NULL。

### 2.4 添加非空约束

（1）建表时

> CREATE TABLE 表名称
> (
> &nbsp; 字段名 数据类型,
> &nbsp; 字段名 数据类型 NOT NULL,
> &nbsp; 字段名 数据类型 NOT NULL
> );

举例：

```sql
CREATE TABLE emp
(
  id INT(10) NOT NULL,
  NAME VARCHAR(20) NOT NULL,
  sex CHAR NULL
);
```

```sql
CREATE TABLE student
(
  sid int,
  sname varchar(20) not null,
  tel char(11) ,
  cardid char(18) not null
);
```

```sh
# 成功
insert into student values(1,'张三','13710011002','110222198912032545');

# 身份证号为空
insert into student values(2,'李四','13710011002',null);
ERROR 1048 (23000): Column 'cardid' cannot be null

# 成功，tel 允许为空
insert into student values(2,'李四',null,'110222198912032546');

# 失败
insert into student values(3,null,null,'110222198912032547');
ERROR 1048 (23000): Column 'sname' cannot be null
```

（2）建表后

> alter table 表名称 modify 字段名 数据类型 not null;

举例：

```sql
ALTER TABLE emp
MODIFY sex VARCHAR(30) NOT NULL;
```

```sql
alter table student modify sname varchar(20) not null;
```

### 2.5 删除非空约束

> \# 去掉 not null，相当于修改某个非注解字段，该字段允许为空
> alter table 表名称 modify 字段名 数据类型 NULL;

或

> \# 去掉 not null，相当于修改某个非注解字段，该字段允许为空
> alter table 表名称 modify 字段名 数据类型;

举例：

```sql
ALTER TABLE emp
MODIFY sex VARCHAR(30) NULL;
```

```sql
ALTER TABLE emp
MODIFY NAME VARCHAR(15) DEFAULT 'abc' NULL;
```

## 3. 唯一性约束

### 3.1 作用

用来限制某个字段/某列的值不能重复。

![作用](https://img-blog.csdnimg.cn/f85d70bcc4a94c85a15d8646b4de6819.png)

### 3.2 关键字

UNIQUE

### 3.3 特点

- 同一个表可以有多个唯一约束。

- 唯一约束可以是某一个列的值唯一，也可以多个列组合的值唯一。

- 唯一性约束允许列值为空。

- 在创建唯一约束的时候，如果不给唯一约束命名，就默认和列名相同。

- **MySQL 会给唯一约束的列上默认创建一个唯一索引。**

### 3.4 添加唯一约束

（1）建表时

> create table 表名称
> (
> &nbsp; 字段名 数据类型,
> &nbsp; 字段名 数据类型 unique,
> &nbsp; 字段名 数据类型 unique key,
> &nbsp; 字段名 数据类型
> );
>
> create table 表名称
> (
> &nbsp; 字段名 数据类型,
> &nbsp; 字段名 数据类型,
> &nbsp; 字段名 数据类型,
> &nbsp; [constraint 约束名] unique key(字段名)
> );

举例：

```sql
create table student
(
  sid int,
  sname varchar(20),
  tel char(11) unique,
  cardid char(18) unique key
);
```

```sql
CREATE TABLE t_course
(
  cid INT UNIQUE,
  cname VARCHAR(100) UNIQUE,
  description VARCHAR(200)
);
```

```sql
CREATE TABLE USER
(
  id INT NOT NULL,
  NAME VARCHAR(25),
  PASSWORD VARCHAR(16),

  # 使用表级约束语法
  CONSTRAINT uk_name_pwd UNIQUE(NAME,PASSWORD)
);
```

> 表示用户名和密码组合不能重复

```sql
insert into student values(1,'张三','13710011002','101223199012015623');
insert into student values(2,'李四','13710011003','101223199012015624');
```

```sh
mysql> select * from student;
+-----+-------+-------------+--------------------+
| sid | sname | tel         | cardid             |
+-----+-------+-------------+--------------------+
|   1 | 张三  | 13710011002 | 101223199012015623 |
|   2 | 李四  | 13710011003 | 101223199012015624 |
+-----+-------+-------------+--------------------+
2 rows in set (0.00 sec)
```

```sh
# 身份证号重复
insert into student values(3,'王五','13710011004','101223199012015624');
ERROR 1062 (23000): Duplicate entry '101223199012015624' for key 'cardid'

insert into student values(3,'王五','13710011003','101223199012015625');
ERROR 1062 (23000): Duplicate entry '13710011003' for key 'tel'
```

（2）建表后指定唯一键约束

> \# 字段列表中如果是一个字段，表示该列的值唯一。如果是两个或更多个字段，那么复合唯一，即多个字段的组合是唯一的
> \# 方式 1：
> alter table 表名称 add unique key(字段列表);
>
> \# 方式 2：
> alter table 表名称 modify 字段名 字段类型 unique;

举例：

```sql
ALTER TABLE USER
ADD UNIQUE(NAME,PASSWORD);
```

```sql
ALTER TABLE USER
ADD CONSTRAINT uk_name_pwd UNIQUE(NAME,PASSWORD);
```

```sql
ALTER TABLE USER
MODIFY NAME VARCHAR(20) UNIQUE;
```

举例：

```sql
create table student
(
  sid int primary key,
  sname varchar(20),
  tel char(11) ,
  cardid char(18)
);
```

```sql
alter table student add unique key(tel);
alter table student add unique key(cardid);
```

### 3.5 关于复合唯一约束

> \# 字段列表中写的是多个字段名，多个字段名用逗号分隔，表示那么是复合唯一，即多个字段的组合是唯一的。
> create table 表名称
> (
> &nbsp; 字段名 数据类型,
> &nbsp; 字段名 数据类型,
> &nbsp; 字段名 数据类型,
> &nbsp; unique key(字段列表)
> );

```sql
# 学生表
create table student
(
  # 学号
  sid int,

  # 姓名
  sname varchar(20),

  # 电话
  tel char(11) unique key,

  # 身份证号
  cardid char(18) unique key
);

# 课程表
create table course
(
  # 课程编号
  cid int,

  # 课程名称
  cname varchar(20)
);

# 选课表
create table student_course
(
  id int,
  sid int,
  cid int,
  score int,

  # 复合唯一
  unique key(sid,cid)
);
```

```sql
# 成功
insert into student values(1,'张三','13710011002','101223199012015623');

# 成功
insert into student values(2,'李四','13710011003','101223199012015624');

# 成功
insert into course values(1001,'Java'),(1002,'MySQL');
```

```sh
mysql> select * from student;
+-----+-------+-------------+--------------------+
| sid | sname | tel         | cardid             |
+-----+-------+-------------+--------------------+
|   1 | 张三  | 13710011002 | 101223199012015623 |
|   2 | 李四  | 13710011003 | 101223199012015624 |
+-----+-------+-------------+--------------------+
2 rows in set (0.00 sec)

mysql> select * from course;
+------+-------+
| cid  | cname |
+------+-------+
| 1001 | Java  |
| 1002 | MySQL |
+------+-------+
2 rows in set (0.00 sec)
```

```sql
insert into student_course values
(1, 1, 1001, 89),
(2, 1, 1002, 90),
(3, 2, 1001, 88),

# 成功
(4, 2, 1002, 56);
```

```sh
mysql> select * from student_course;
+----+------+------+-------+
| id | sid  | cid  | score |
+----+------+------+-------+
|  1 |    1 | 1001 |    89 |
|  2 |    1 | 1002 |    90 |
|  3 |    2 | 1001 |    88 |
|  4 |    2 | 1002 |    56 |
+----+------+------+-------+
4 rows in set (0.00 sec)
```

```sh
# 失败
insert into student_course values (5, 1, 1001, 88);

# ERROR 1062 (23000): Duplicate entry '1-1001' for key 'sid'
# 违反 sid-cid 的复合唯一
```

### 3.5 删除唯一约束

- 添加唯一性约束的列上也会自动创建唯一索引。

- 删除唯一约束只能通过删除唯一索引的方式删除。

- 删除时需要指定唯一索引名，唯一索引名就和唯一约束名一样。

- 如果创建唯一约束时未指定名称，如果是单列，就默认和列名相同；如果是组合列，那么默认和()中排在第一个的列名相同。也可以自定义唯一性约束名。

> \# 查看都有哪些约束
> SELECT \* FROM information_schema.table_constraints WHERE table_name = '表名';

```sql
ALTER TABLE USER
DROP INDEX uk_name_pwd;
```

> 注意：可以通过 `show index from 表名称; `查看表的索引

## 4. PRIMARY KEY 约束

### 4.1 作用

用来唯一标识表中的一行记录。

### 4.2 关键字

primary key

### 4.3 特点

- 主键约束相当于**唯一约束+非空约束的组合**，主键约束列不允许重复，也不允许出现空值。

  ![特点](https://img-blog.csdnimg.cn/c80214ac13774acf872a8d327a827428.png)

- 一个表最多只能有一个主键约束，建立主键约束可以在列级别创建，也可以在表级别上创建。

- 主键约束对应着表中的一列或者多列（复合主键）。

- 如果是多列组合的复合主键约束，那么这些列都不允许为空值，并且组合的值不允许重复。

- **MySQL 的主键名总是 PRIMARY**，就算自己命名了主键约束名也没用。

- 当创建主键约束时，系统默认会在所在的列或列组合上建立对应的**主键索引**（能够根据主键查询的，就根据主键查询，效率更高）。如果删除主键约束了，主键约束对应的索引就自动删除了。

- 需要注意的一点是，不要修改主键字段的值。因为主键是数据记录的唯一标识，如果修改了主键的值，就有可能会破坏数据的完整性。

### 4.4 添加主键约束

（1）建表时指定主键约束

> create table 表名称
> (
> &nbsp; \# 列级模式
> &nbsp; 字段名 数据类型 primary key,
> &nbsp; 字段名 数据类型,
> &nbsp; 字段名 数据类型
> );
>
> create table 表名称
> (
> &nbsp; 字段名 数据类型,
> &nbsp; 字段名 数据类型,
> &nbsp; 字段名 数据类型,
>
> &nbsp; \# 表级模式
> &nbsp; [constraint 约束名] primary key(字段名)
> );

举例：

```sql
create table temp
(
  id int primary key,
  name varchar(20)
);
```

```sh
mysql> desc temp;
+-------+-------------+------+-----+---------+-------+
| Field | Type        | Null | Key | Default | Extra |
+-------+-------------+------+-----+---------+-------+
| id    | int(11)     | NO   | PRI | NULL    |       |
| name  | varchar(20) | YES  |     | NULL    |       |
+-------+-------------+------+-----+---------+-------+
2 rows in set (0.00 sec)
```

```sql
# 成功
insert into temp values(1,'张三');

# 成功
insert into temp values(2,'李四');
```

```sh
mysql> select * from temp;
+----+------+
| id | name |
+----+------+
|  1 | 张三 |
|  2 | 李四 |
+----+------+
2 rows in set (0.00 sec)
```

```sh
# 失败
insert into temp values(1,'张三');
ERROR 1062 (23000): Duplicate（重复） entry（键入，输入） '1' for key 'PRIMARY'

# 失败
insert into temp values(1,'王五');
ERROR 1062 (23000): Duplicate entry '1' for key 'PRIMARY'

# 成功
insert into temp values(3,'张三');
```

```sh
mysql> select * from temp;
+----+------+
| id | name |
+----+------+
|  1 | 张三 |
|  2 | 李四 |
|  3 | 张三 |
+----+------+
3 rows in set (0.00 sec)
```

```sh
# 成功
insert into temp values(4,null);

# 失败
insert into temp values(null,'李琦');
ERROR 1048 (23000): Column 'id' cannot be null
```

```sh
mysql> select * from temp;
+----+------+
| id | name |
+----+------+
|  1 | 张三 |
|  2 | 李四 |
|  3 | 张三 |
|  4 | NULL |
+----+------+
4 rows in set (0.00 sec)
```

```sh
# 演示一个表建立两个主键约束
create table temp
(
  id int primary key,
  name varchar(20) primary key
);
ERROR 1068 (42000): Multiple（多重的） primary key defined（定义）
```

再举例：

- 列级约束

  ```sql
  CREATE TABLE emp4
  (
    id INT PRIMARY KEY AUTO_INCREMENT ,
    NAME VARCHAR(20)
  );
  ```

- 表级约束

  ```sql
  CREATE TABLE emp5
  (
    id INT NOT NULL AUTO_INCREMENT,
    NAME VARCHAR(20),
    pwd VARCHAR(15),
    CONSTRAINT emp5_id_pk PRIMARY KEY(id)
  );
  ```

（2）建表后增加主键约束

> \# 字段列表可以是一个字段，也可以是多个字段，如果是多个字段的话，是复合主键
> ALTER TABLE 表名称 ADD PRIMARY KEY(字段列表);

```sql
ALTER TABLE student ADD PRIMARY KEY (sid);
```

```sql
ALTER TABLE emp5 ADD PRIMARY KEY(NAME,pwd);
```

### 4.5 关于复合主键

> create table 表名称
> (
> &nbsp; 字段名 数据类型,
> &nbsp; 字段名 数据类型,
> &nbsp; 字段名 数据类型,
> &nbsp; primary key(字段名 1,字段名 2) #表示字段 1 和字段 2 的组合是唯一的，也可以有更多个字段
> );

```sql
# 学生表
create table student
(
  # 学号
  sid int primary key,

  # 学生姓名
  sname varchar(20)
);

# 课程表
create table course
(
  # 课程编号
  cid int primary key,

  # 课程名称
  cname varchar(20)
);

# 选课表
create table student_course
(
  sid int,
  cid int,
  score int,

  # 复合主键
  primary key(sid,cid)
);
```

```sql
insert into student values(1,'张三'),(2,'李四');
insert into course values(1001,'Java'),(1002,'MySQL');
```

```sh
mysql> select * from student;
+-----+-------+
| sid | sname |
+-----+-------+
|   1 | 张三  |
|   2 | 李四  |
+-----+-------+
2 rows in set (0.00 sec)

mysql> select * from course;
+------+-------+
| cid  | cname |
+------+-------+
| 1001 | Java  |
| 1002 | MySQL |
+------+-------+
2 rows in set (0.00 sec)
```

```sql
insert into student_course values(1, 1001, 89),(1,1002,90),(2,1001,88),(2,1002,56);
```

```sh
mysql> select * from student_course;
+-----+------+-------+
| sid | cid  | score |
+-----+------+-------+
|   1 | 1001 |    89 |
|   1 | 1002 |    90 |
|   2 | 1001 |    88 |
|   2 | 1002 |    56 |
+-----+------+-------+
4 rows in set (0.00 sec)
```

```sql
insert into student_course values(1, 1001, 100);
ERROR 1062 (23000): Duplicate entry '1-1001' for key 'PRIMARY'
```

```sh
mysql> desc student_course;
+-------+---------+------+-----+---------+-------+
| Field | Type    | Null | Key | Default | Extra |
+-------+---------+------+-----+---------+-------+
| sid   | int(11) | NO   | PRI | NULL    |       |
| cid   | int(11) | NO   | PRI | NULL    |       |
| score | int(11) | YES  |     | NULL    |       |
+-------+---------+------+-----+---------+-------+
3 rows in set (0.00 sec)
```

- 再举例

  ```sql
  CREATE TABLE emp6
  (
    id INT NOT NULL,
    NAME VARCHAR(20),
    pwd VARCHAR(15),
    CONSTRAINT emp7_pk PRIMARY KEY(NAME,pwd)
  );
  ```

### 4.6 删除主键约束

> alter table 表名称 drop primary key;

举例：

```sql
ALTER TABLE student DROP PRIMARY KEY;
```

```sql
ALTER TABLE emp5 DROP PRIMARY KEY;
```

> 说明：删除主键约束，不需要指定主键名，因为一个表只有一个主键，删除主键约束后，非空还存在。

## 5. 自增列：AUTO_INCREMENT

### 5.1 作用

某个字段的值自增。

### 5.2 关键字

auto_increment

### 5.3 特点和要求

（1）一个表最多只能有一个自增长列。

（2）当需要产生唯一标识符或顺序值时，可设置自增长。

（3）自增长列约束的列必须是键列（主键列，唯一键列）。

（4）自增约束的列的数据类型必须是整数类型。

（5）如果自增列指定了 0 和 null，会在当前最大值的基础上自增；如果自增列手动指定了具体值，直接赋值为具体值。

错误演示：

```sql
create table employee
(
  eid int auto_increment,
  ename varchar(20)
);

# ERROR 1075 (42000): Incorrect table definition; there can be only one auto column and it must be defined as a key
```

```sql
create table employee
(
  eid int primary key,
  ename varchar(20) unique key auto_increment
);

# ERROR 1063 (42000): Incorrect column specifier for column 'ename'  因为ename不是整数类型
```

### 5.4 如何指定自增约束

**（1）建表时**

> create table 表名称
> (
> &nbsp; 字段名 数据类型 primary key auto_increment,
> &nbsp; 字段名 数据类型 unique key not null,
> &nbsp; 字段名 数据类型 unique key,
> &nbsp; 字段名 数据类型 not null default 默认值,
> );
>
> create table 表名称
> (
> &nbsp; 字段名 数据类型 default 默认值 ,
> &nbsp; 字段名 数据类型 unique key auto_increment,
> &nbsp; 字段名 数据类型 not null default 默认值,,
> &nbsp; primary key(字段名)
> );

```sql
create table employee
(
  eid int primary key auto_increment,
  ename varchar(20)
);
```

```sh
mysql> desc employee;
+-------+-------------+------+-----+---------+----------------+
| Field | Type        | Null | Key | Default | Extra          |
+-------+-------------+------+-----+---------+----------------+
| eid   | int(11)     | NO   | PRI | NULL    | auto_increment |
| ename | varchar(20) | YES  |     | NULL    |                |
+-------+-------------+------+-----+---------+----------------+
2 rows in set (0.00 sec)
```

**（2）建表后**

> alter table 表名称 modify 字段名 数据类型 auto_increment;

例如：

```sql
create table employee
(
  eid int primary key ,
  ename varchar(20)
);
```

```sql
alter table employee modify eid int auto_increment;
```

```sh
mysql> desc employee;
+-------+-------------+------+-----+---------+----------------+
| Field | Type        | Null | Key | Default | Extra          |
+-------+-------------+------+-----+---------+----------------+
| eid   | int(11)     | NO   | PRI | NULL    | auto_increment |
| ename | varchar(20) | YES  |     | NULL    |                |
+-------+-------------+------+-----+---------+----------------+
2 rows in set (0.00 sec)
```

### 5.5 如何删除自增约束

> \# alter table 表名称 modify 字段名 数据类型 auto_increment;
> \# 给这个字段增加自增约束
> \# 去掉 auto_increment 相当于删除
> alter table 表名称 modify 字段名 数据类型;

```sql
alter table employee modify eid int;
```

```sh
mysql> desc employee;
+-------+-------------+------+-----+---------+-------+
| Field | Type        | Null | Key | Default | Extra |
+-------+-------------+------+-----+---------+-------+
| eid   | int(11)     | NO   | PRI | NULL    |       |
| ename | varchar(20) | YES  |     | NULL    |       |
+-------+-------------+------+-----+---------+-------+
2 rows in set (0.00 sec)
```

### 5.6 MySQL 8.0 新特性—自增变量的持久化

在 MySQL 8.0 之前，自增主键 AUTO_INCREMENT 的值如果大于 max(primary key)+1，在 MySQL 重启后，会重置 AUTO_INCREMENT=max(primary key)+1，这种现象在某些情况下会导致业务主键冲突或者其他难以发现的问题。

下面通过案例来对比不同的版本中自增变量是否持久化。

在 MySQL 5.7 版本中，测试步骤如下：

创建的数据表中包含自增主键的 id 字段，语句如下：

```sql
CREATE TABLE test1
(
  id INT PRIMARY KEY AUTO_INCREMENT
);
```

插入 4 个空值，执行如下：

```sql
INSERT INTO test1
VALUES(0),(0),(0),(0);
```

查询数据表 test1 中的数据，结果如下：

```sh
mysql> SELECT * FROM test1;
+----+
| id |
+----+
|  1 |
|  2 |
|  3 |
|  4 |
+----+
4 rows in set (0.00 sec)
```

删除 id 为 4 的记录，语句如下：

```sql
DELETE FROM test1 WHERE id = 4;
```

再次插入一个空值，语句如下：

```sql
INSERT INTO test1 VALUES(0);
```

查询此时数据表 test1 中的数据，结果如下：

```sh
mysql> SELECT * FROM test1;
+----+
| id |
+----+
|  1 |
|  2 |
|  3 |
|  5 |
+----+
4 rows in set (0.00 sec)
```

从结果可以看出，虽然删除了 id 为 4 的记录，但是再次插入空值时，并没有重用被删除的 4，而是分配了 5。

删除 id 为 5 的记录，结果如下：

```sql
DELETE FROM test1 where id=5;
```

**重启数据库**，重新插入一个空值。

```sql
INSERT INTO test1 values(0);
```

再次查询数据表 test1 中的数据，结果如下：

```sh
mysql> SELECT * FROM test1;
+----+
| id |
+----+
|  1 |
|  2 |
|  3 |
|  4 |
+----+
4 rows in set (0.00 sec)
```

从结果可以看出，新插入的 0 值分配的是 4，按照重启前的操作逻辑，此处应该分配 6。出现上述结果的主要原因是自增主键没有持久化。

在 MySQL 5.7 系统中，对于自增主键的分配规则，是由 InnoDB 数据字典内部一个`计数器`来决定的，而该计数器只在`内存中维护`，并不会持久化到磁盘中。当数据库重启时，该计数器会被初始化。

在 MySQL 8.0 版本中，上述测试步骤最后一步的结果如下：

```sh
mysql> SELECT * FROM test1;
+----+
| id |
+----+
|  1 |
|  2 |
|  3 |
|  6 |
+----+
4 rows in set (0.00 sec)
```

从结果可以看出，自增变量已经持久化了。

MySQL 8.0 将自增主键的计数器持久化到`重做日志`中。每次计数器发生改变，都会将其写入重做日志中。如果数据库重启，InnoDB 会根据重做日志中的信息来初始化计数器的内存值。

## 6. FOREIGN KEY 约束

### 6.1 作用

限定某个表的某个字段的引用完整性。

比如：员工表的员工所在部门的选择，必须在部门表能找到对应的部分。

![作用](https://img-blog.csdnimg.cn/2b6635b66e474fb4b4440007ceef02fb.png)

### 6.2 关键字

FOREIGN KEY

### 6.3 主表和从表/父表和子表

主表（父表）：被引用的表，被参考的表。

从表（子表）：引用别人的表，参考别人的表。

例如：员工表的员工所在部门这个字段的值要参考部门表：部门表是主表，员工表是从表。

例如：学生表、课程表、选课表：选课表的学生和课程要分别参考学生表和课程表，学生表和课程表是主表，选课表是从表。

### 6.4 特点

（1）从表的外键列，必须引用/参考主表的主键或唯一约束的列。
​ 为什么？因为被依赖/被参考的值必须是唯一的

（2）在创建外键约束时，如果不给外键约束命名，**默认名不是列名，而是自动产生一个外键名**（例如 student_ibfk_1;），也可以指定外键约束名。

（3）创建(CREATE)表时就指定外键约束的话，先创建主表，再创建从表。

（4）删表时，先删从表（或先删除外键约束），再删除主表。

（5）当主表的记录被从表参照时，主表的记录将不允许删除，如果要删除数据，需要先删除从表中依赖该记录的数据，然后才可以删除主表的数据。

（6）在“从表”中指定外键约束，并且一个表可以建立多个外键约束。

（7）从表的外键列与主表被参照的列名字可以不相同，但是数据类型必须一样，逻辑意义一致。如果类型不一样，创建子表时，就会出现错误“ERROR 1005 (HY000): Can't create table'database.tablename'(errno: 150)”。
​ 例如：都是表示部门编号，都是 int 类型。

（8）**当创建外键约束时，系统默认会在所在的列上建立对应的普通索引**。但是索引名是外键的约束名。（根据外键查询效率很高）

（9）删除外键约束后，必须`手动`删除对应的索引。

### 6.5 添加外键约束

（1）建表时

> create table 主表名称
> (
> &nbsp; 字段 1 数据类型 primary key,
> &nbsp;字段 2 数据类型
> );
>
> create table 从表名称
> (
> &nbsp; 字段 1 数据类型 primary key,
> &nbsp; 字段 2 数据类型,
> &nbsp; [CONSTRAINT <外键约束名称>] FOREIGN KEY(从表的某个字段)references 主表名(被参考字段)
> );
>
> \#(从表的某个字段)的数据类型必须与主表名(被参考字段)的数据类型一致，逻辑意义也一样
> \#(从表的某个字段)的字段名可以与主表名(被参考字段)的字段名一样，也可以不一样
>
> \# FOREIGN KEY: 在表级指定子表中的列
> \# REFERENCES: 标示在父表中的列

```sql
# 主表
create table dept
(
  # 部门编号
  did int primary key,

  # 部门名称
  dname varchar(50)
);

# 从表
create table emp
(
  # 员工编号
  eid int primary key,

  # 员工姓名
  ename varchar(5),

  # 员工所在的部门
  deptid int,

  # 在从表中指定外键约束
  foreign key (deptid) references dept(did)

  #emp表的deptid和和dept表的did的数据类型一致，意义都是表示部门的编号
);

# 说明：
# ① 主表dept必须先创建成功，然后才能创建emp表，指定外键成功。
# ② 删除表时，先删除从表emp，再删除主表dept。
```

（2）建表后

一般情况下，表与表的关联都是提前设计好了的，因此，会在创建表的时候就把外键约束定义好。不过，如果需要修改表的设计（比如添加新的字段，增加新的关联关系），但没有预先定义外键约束，那么，就要用修改表的方式来补充定义。

格式：

> ALTER TABLE 从表名 ADD [CONSTRAINT 约束名] FOREIGN KEY (从表的字段) >REFERENCES 主表名(被引用字段) [on update xx][on delete xx];

举例：

```sql
ALTER TABLE emp1
ADD [CONSTRAINT emp_dept_id_fk] FOREIGN KEY(dept_id) REFERENCES dept(dept_id);
```

举例：

```sql
create table dept
(
  # 部门编号
  did int primary key,

  # 部门名称
  dname varchar(50)
);

create table emp
(
  # 员工编号
  eid int primary key,

  # 员工姓名
  ename varchar(5),

  # 员工所在的部门
  deptid int
);

# 这两个表创建时，没有指定外键的话，那么创建顺序是随意。
alter table emp add foreign key (deptid) references dept(did);
```

### 6.6 演示问题

（1）失败：不是键列

```sql
create table dept
(
  # 部门编号
  did int ,

  # 部门名称
  dname varchar(50)
);

create table emp
(
  # 员工编号
  eid int primary key,

  # 员工姓名
  ename varchar(5),

  # 员工所在的部门
  deptid int,
  foreign key (deptid) references dept(did)
);

# ERROR 1215 (HY000): Cannot add foreign key constraint
# 原因是 dept 的 did 不是键列
```

（2）失败：数据类型不一致

```sql
create table dept
(
  # 部门编号
  did int primary key,

  # 部门名称
  dname varchar(50)
);

create table emp
(
  # 员工编号
  eid int primary key,

  # 员工姓名
  ename varchar(5),

  # 员工所在的部门
  deptid char,
  foreign key (deptid) references dept(did)
);

# ERROR 1215 (HY000): Cannot add foreign key constraint
# 原因是从表的 deptid 字段和主表的 did 字段的数据类型不一致，并且要它俩的逻辑意义一致
```

（3）成功，两个表字段名一样

```sql
create table dept
(
  # 部门编号
  did int primary key,

  # 部门名称
  dname varchar(50)
);

create table emp
(
  # 员工编号
  eid int primary key,

  # 员工姓名
  ename varchar(5),

  # 员工所在的部门
  did int,
  foreign key (did) references dept(did)

  # emp 表的 deptid 和 dept 表的 did 的数据类型一致，意义都是表示部门的编号
  # 是否重名没问题，因为两个 did 在不同的表中
);
```

（4）添加、删除、修改问题

```sql
create table dept
(
  # 部门编号
  did int primary key,

  # 部门名称
  dname varchar(50)
);

create table emp
(
  #员工编号
  eid int primary key,

  #员工姓名
  ename varchar(5),

  #员工所在的部门
  deptid int,
  foreign key (deptid) references dept(did)

  # emp 表的 deptid 和 dept 表的 did 的数据类型一致，意义都是表示部门的编号
);
```

```sh
insert into dept values(1001,'教学部');
insert into dept values(1003, '财务部');

# 添加从表记录成功，在添加这条记录时，要求部门表有 1001 部门
insert into emp values(1,'张三',1001);

# 添加从表记录失败
insert into emp values(2,'李四',1005);

ERROR 1452 (23000): Cannot add（添加） or update（修改） a child row: a foreign key constraint fails (`myxhdb`.`emp`, CONSTRAINT `emp_ibfk_1` FOREIGN KEY (`deptid`) REFERENCES `dept` (`did`))

# 从表 emp 添加记录失败，因为主表 dept 没有 1005 部门
```

```sh
mysql> select * from dept;
+------+--------+
| did  | dname  |
+------+--------+
| 1001 | 教学部  |
| 1003 | 财务部  |
+------+--------+
2 rows in set (0.00 sec)

mysql> select * from emp;
+-----+-------+--------+
| eid | ename | deptid |
+-----+-------+--------+
|   1 | 张三   |   1001 |
+-----+-------+--------+
1 row in set (0.00 sec)
```

```sh
# 修改从表失败
update emp set deptid = 1002 where eid = 1;

# 部门表 did 字段现在没有 1002 的值，所以员工表中不能修改员工所在部门 deptid 为 1002
ERROR 1452 (23000): Cannot add（添加） or update（修改） a child row（子表的记录）: a foreign key constraint fails（外键约束失败） (`myxhdb`.`emp`, CONSTRAINT `emp_ibfk_1` FOREIGN KEY (`deptid`) REFERENCES `dept` (`did`))

# 修改主表失败
update dept set did = 1002 where did = 1001;

# 部门表 did 的 1001 字段已经被 emp 引用了，所以部门表的 1001 字段就不能修改了。
ERROR 1451 (23000): Cannot delete（删除） or update（修改） a parent row（父表的记录）: a foreign key constraint fails (`myxhdb`.`emp`, CONSTRAINT `emp_ibfk_1` FOREIGN KEY (`deptid`) REFERENCES `dept` (`did`))

# 修改主表成功，因为部门表的 1003 部门没有被 emp 表引用，所以可以修改
update dept set did = 1002 where did = 1003;
```

```sh
# 删除主表失败
delete from dept where did=1001;

# 因为部门表 did 的 1001 字段已经被 emp 引用了，所以部门表的 1001 字段对应的记录就不能被删除
ERROR 1451 (23000): Cannot delete（删除） or update（修改） a parent row（父表记录）: a foreign key constraint fails (`myxhdb`.`emp`, CONSTRAINT `emp_ibfk_1` FOREIGN KEY (`deptid`) REFERENCES `dept` (`did`))
```

总结：约束关系是针对双方的

- 添加了外键约束后，主表的修改和删除数据受约束。

- 添加了外键约束后，从表的添加和修改数据受约束。

- 在从表上建立外键，要求主表必须存在。

- 删除主表时，要求从表从表先删除，或将从表中外键引用该主表的关系先删除。

### 6.7 约束等级

- `Cascade方式`：在父表上 update/delete 记录时，同步 update/delete 掉子表的匹配记录。

- `Set null方式`：在父表上 update/delete 记录时，将子表上匹配记录的列设为 null，但是要注意子表的外键列不能为 not null。

- `No action方式`：如果子表中有匹配的记录，则不允许对父表对应候选键进行 update/delete 操作。

- `Restrict方式`：同 no action， 都是立即检查外键约束。

- `Set default方式`（在可视化工具 SQLyog 中可能显示空白）：父表有变更时，子表将外键列设置成一个默认的值，但 Innodb 不能识别。

如果没有指定等级，就相当于 Restrict 方式。

对于外键约束，最好是采用: `ON UPDATE CASCADE ON DELETE RESTRICT` 的方式。

（1）演示 1：on update cascade on delete set null

```sql
create table dept
(
  # 部门编号
  did int primary key,

  # 部门名称
  dname varchar(50)
);

create table emp
(
  # 员工编号
  eid int primary key,

  # 员工姓名
  ename varchar(5),

  # 员工所在的部门
  deptid int,

  # 把修改操作设置为级联修改等级，把删除操作设置为 set null 等级
  foreign key (deptid) references dept(did)  on update cascade on delete set null
);
```

```sql
insert into dept values(1001,'教学部');
insert into dept values(1002, '财务部');
insert into dept values(1003, '咨询部');

# 在添加这条记录时，要求部门表有 1001 部门
insert into emp values(1,'张三',1001);
insert into emp values(2,'李四',1001);
insert into emp values(3,'王五',1002);
```

```sh
mysql> select * from dept;

mysql> select * from emp;
```

```sh
# 修改主表成功，从表也跟着修改，修改了主表被引用的字段 1002 为 1004，从表的引用字段就跟着修改为 1004 了
mysql> update dept set did = 1004 where did = 1002;
Query OK, 1 row affected (0.00 sec)
Rows matched: 1  Changed: 1  Warnings: 0

# 原来是 1002，修改为 1004
mysql> select * from dept;
+------+--------+
| did  | dname  |
+------+--------+
| 1001 | 教学部 |
| 1003 | 咨询部 |
| 1004 | 财务部 |
+------+--------+
3 rows in set (0.00 sec)

# 原来是 1002，跟着修改为 1004
mysql> select * from emp;
+-----+-------+--------+
| eid | ename | deptid |
+-----+-------+--------+
|   1 | 张三  |   1001 |
|   2 | 李四  |   1001 |
|   3 | 王五  |   1004 |
+-----+-------+--------+
3 rows in set (0.00 sec)
```

```sh
# 删除主表的记录成功，从表对应的字段的值被修改为 null
mysql> delete from dept where did = 1001;
Query OK, 1 row affected (0.01 sec)

# 记录 1001 部门被删除了
mysql> select * from dept;
+------+--------+
| did  | dname  |
+------+--------+
| 1003 | 咨询部  |
| 1004 | 财务部  |
+------+--------+
2 rows in set (0.00 sec)

# 原来引用 1001 部门的员工，deptid 字段变为 null
mysql> select * from emp;
+-----+-------+--------+
| eid | ename | deptid |
+-----+-------+--------+
|   1 | 张三  |   NULL |
|   2 | 李四  |   NULL |
|   3 | 王五  |   1004 |
+-----+-------+--------+
3 rows in set (0.00 sec)
```

（2）演示 2：on update set null on delete cascade

```sql
create table dept
(
  # 部门编号
  did int primary key,

  # 部门名称
  dname varchar(50)
);

create table emp
(
  # 员工编号
  eid int primary key,

  # 员工姓名
  ename varchar(5),

  # 员工所在的部门
  deptid int,

  # 把修改操作设置为 set null 等级，把删除操作设置为级联删除等级
  foreign key (deptid) references dept(did)  on update set null on delete cascade
);
```

```sql
insert into dept values(1001,'教学部');
insert into dept values(1002, '财务部');
insert into dept values(1003, '咨询部');

# 在添加这条记录时，要求部门表有 1001 部门
insert into emp values(1,'张三',1001);
insert into emp values(2,'李四',1001);
insert into emp values(3,'王五',1002);
```

```sh
mysql> select * from dept;
+------+--------+
| did  | dname  |
+------+--------+
| 1001 | 教学部 |
| 1002 | 财务部 |
| 1003 | 咨询部 |
+------+--------+
3 rows in set (0.00 sec)

mysql> select * from emp;
+-----+-------+--------+
| eid | ename | deptid |
+-----+-------+--------+
|   1 | 张三  |   1001 |
|   2 | 李四  |   1001 |
|   3 | 王五  |   1002 |
+-----+-------+--------+
3 rows in set (0.00 sec)
```

```sh
# 修改主表，从表对应的字段设置为 null
mysql> update dept set did = 1004 where did = 1002;
Query OK, 1 row affected (0.00 sec)
Rows matched: 1  Changed: 1  Warnings: 0

# 原来 did 是 1002
mysql> select * from dept;
+------+--------+
| did  | dname  |
+------+--------+
| 1001 | 教学部 |
| 1003 | 咨询部 |
| 1004 | 财务部 |
+------+--------+
3 rows in set (0.00 sec)

# 原来 deptid 是 1002，因为部门表 1002 被修改了，1002 没有对应的了，就设置为 null
mysql> select * from emp;
+-----+-------+--------+
| eid | ename | deptid |
+-----+-------+--------+
|   1 | 张三  |   1001 |
|   2 | 李四  |   1001 |
|   3 | 王五  |   NULL |
+-----+-------+--------+
3 rows in set (0.00 sec)
```

```sh
# 删除主表的记录成功，主表的 1001 行被删除了，从表相应的记录也被删除了
mysql> delete from dept where did=1001;
Query OK, 1 row affected (0.00 sec)

# 部门表中 1001 部门被删除
mysql> select * from dept;
+------+--------+
| did  | dname  |
+------+--------+
| 1003 | 咨询部 |
| 1004 | 财务部 |
+------+--------+
2 rows in set (0.00 sec)

# 原来 1001 部门的员工也被删除了
mysql> select * from emp;
+-----+-------+--------+
| eid | ename | deptid |
+-----+-------+--------+
|   3 | 王五  |   NULL |
+-----+-------+--------+
1 row in set (0.00 sec)
```

（3）演示：on update cascade on delete cascade

```sql
create table dept
(
  # 部门编号
  did int primary key,

  # 部门名称
  dname varchar(50)
);

create table emp
(
  #员工编号
  eid int primary key,

  #员工姓名
  ename varchar(5),

  #员工所在的部门
  deptid int,

  # 把修改操作设置为级联修改等级，把删除操作也设置为级联删除等级
  foreign key (deptid) references dept(did)  on update cascade on delete cascade
);
```

```sql
insert into dept values(1001,'教学部');
insert into dept values(1002, '财务部');
insert into dept values(1003, '咨询部');

# 在添加这条记录时，要求部门表有 1001 部门
insert into emp values(1,'张三',1001);
insert into emp values(2,'李四',1001);
insert into emp values(3,'王五',1002);
```

```sh
mysql> select * from dept;
+------+--------+
| did  | dname  |
+------+--------+
| 1001 | 教学部 |
| 1002 | 财务部 |
| 1003 | 咨询部 |
+------+--------+
3 rows in set (0.00 sec)

mysql> select * from emp;
+-----+-------+--------+
| eid | ename | deptid |
+-----+-------+--------+
|   1 | 张三  |   1001 |
|   2 | 李四  |   1001 |
|   3 | 王五  |   1002 |
+-----+-------+--------+
3 rows in set (0.00 sec)
```

```sh
# 修改主表，从表对应的字段自动修改
mysql> update dept set did = 1004 where did = 1002;
Query OK, 1 row affected (0.00 sec)
Rows matched: 1  Changed: 1  Warnings: 0

# 部门1002修改为1004
mysql> select * from dept;
+------+--------+
| did  | dname  |
+------+--------+
| 1001 | 教学部 |
| 1003 | 咨询部 |
| 1004 | 财务部 |
+------+--------+
3 rows in set (0.00 sec)

# 级联修改
mysql> select * from emp;
+-----+-------+--------+
| eid | ename | deptid |
+-----+-------+--------+
|   1 | 张三  |   1001 |
|   2 | 李四  |   1001 |
|   3 | 王五  |   1004 |
+-----+-------+--------+
3 rows in set (0.00 sec)
```

```sh
# 删除主表的记录成功，主表的 1001 行被删除了，从表相应的记录也被删除了
mysql> delete from dept where did=1001;
Query OK, 1 row affected (0.00 sec)

# 1001 部门被删除了
mysql> select * from dept;
+------+--------+
| did  | dname  |
+------+--------+
| 1003 | 咨询部 |
| 1004 | 财务部 |
+------+--------+
2 rows in set (0.00 sec)

# 1001 部门的员工也被删除了
mysql> select * from emp;
+-----+-------+--------+
| eid | ename | deptid |
+-----+-------+--------+
|   3 | 王五  |   1004 |
+-----+-------+--------+
1 row in set (0.00 sec)
```

### 6.8 删除外键约束

流程如下：

> ① 第一步先查看约束名和删除外键约束
> \# 查看某个表的约束名
> SELECT \* FROM information_schema.table_constraints WHERE table_name = '表名称';
>
> ALTER TABLE 从表名 DROP FOREIGN KEY 外键约束名;
>
> ② 第二步查看索引名和删除索引。（注意，只能手动删除）
> \# 查看某个表的索引名
> SHOW INDEX FROM 表名称;
>
> ALTER TABLE 从表名 DROP INDEX 索引名;

举例：

```sh
mysql> SELECT * FROM information_schema.table_constraints WHERE table_name = 'emp';

mysql> alter table emp drop foreign key emp_ibfk_1;
Query OK, 0 rows affected (0.02 sec)
Records: 0  Duplicates: 0  Warnings: 0
```

```sh
mysql> show index from emp;

mysql> alter table emp drop index deptid;
Query OK, 0 rows affected (0.01 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql>  show index from emp;
```

### 6.9 开发场景

**问题 1：如果两个表之间有关系（一对一、一对多），比如：员工表和部门表（一对多），它们之间是否一定要建外键约束？**

答：不是的。

**问题 2：建和不建外键约束有什么区别？**

答：建外键约束，你的操作（创建表、删除表、添加、修改、删除）会受到限制，从语法层面受到限制。例如：在员工表中不可能添加一个员工信息，它的部门的值在部门表中找不到。

不建外键约束，你的操作（创建表、删除表、添加、修改、删除）不受限制，要保证数据的`引用完整性`，只能依`靠程序员的自觉`，或者是`在Java程序中进行限定`。例如：在员工表中，可以添加一个员工的信息，它的部门指定为一个完全不存在的部门。

**问题 3：那么建和不建外键约束和查询有没有关系？**

答：没有。

> 在 MySQL 里，外键约束是有成本的，需要消耗系统资源。对于大并发的 SQL 操作，有可能会不适合。比如大型网站的中央数据库，可能会`因为外键约束的系统开销而变得非常慢`。所以， MySQL 允许你不使用系统自带的外键约束，在`应用层面`完成检查数据一致性的逻辑。也就是说，即使你不用外键约束，也要想办法通过应用层面的附加逻辑，来实现外键约束的功能，确保数据的一致性。

### 6.10 阿里开发规范

【`强制`】不得使用外键与级联，一切外键概念必须在应用层解决。

说明：（概念解释）学生表中的 student_id 是主键，那么成绩表中的 student_id 则为外键。如果更新学生表中的 student_id，同时触发成绩表中的 student_id 更新，即为级联更新。外键与级联更新适用于`单机低并发`，不适合`分布式`、`高并发集群`；级联更新是强阻塞，存在数据库`更新风暴`的风险；外键影响数据库的`插入速度`。

## 7. CHECK 约束

### 7.1 作用

检查某个字段的值是否符号 xx 要求，一般指的是值的范围。

### 7.2 关键字

CHECK

### 7.3 说明：MySQL 5.7 不支持

MySQL5.7 可以使用 check 约束，但 check 约束对数据验证没有任何作用。添加数据时，没有任何错误或警告。

但是**MySQL 8.0 中可以使用 check 约束了**。

```sql
create table employee
(
  eid int primary key,
  ename varchar(5),
  gender char check ('男' or '女')
);
```

```sql
insert into employee values(1,'张三','男');
```

```sh
mysql> select * from employee;
+-----+-------+--------+
| eid | ename | gender |
+-----+-------+--------+
|   1 | 张三   | 男     |
+-----+-------+--------+
1 row in set (0.00 sec)
```

- 再举例

  ```sql
  CREATE TABLE temp
  (
    id INT AUTO_INCREMENT,
    NAME VARCHAR(20),
    age INT CHECK(age > 20),
    PRIMARY KEY(id)
  );
  ```

- 再举例

  ```sql
  age tinyint check(age >20) 或 sex char(2) check(sex in(‘男’,’女’))
  ```

- 再举例

  ```sql
  CHECK(height>=0 AND height<3)
  ```

## 8. DEFAULT 约束

### 8.1 作用

给某个字段/某列指定默认值，一旦设置默认值，在插入数据时，如果此字段没有显式赋值，则赋值为默认值。

### 8.2 关键字

DEFAULT

### 8.3 如何给字段加默认值

（1）建表时

> create table 表名称
> (
> &nbsp; 字段名 数据类型 primary key,
> &nbsp; 字段名 数据类型 unique key not null,
> &nbsp; 字段名 数据类型 unique key,
> &nbsp; 字段名 数据类型 not null default 默认值,
> );
>
> create table 表名称
> (
> &nbsp; 字段名 数据类型 default 默认值 ,
> &nbsp; 字段名 数据类型 not null default 默认值,
> &nbsp; 字段名 数据类型 not null default 默认值,
> &nbsp; primary key(字段名),
> &nbsp; unique key(字段名)
> );
>
> 说明：默认值约束一般不在唯一键和主键列上加

```sql
create table employee
(
  eid int primary key,
  ename varchar(20) not null,
  gender char default '男',

  # 默认是空字符串
  tel char(11) not null default ''
  );
```

```sh
mysql> desc employee;
+--------+-------------+------+-----+---------+-------+
| Field  | Type        | Null | Key | Default | Extra |
+--------+-------------+------+-----+---------+-------+
| eid    | int(11)     | NO   | PRI | NULL    |       |
| ename  | varchar(20) | NO   |     | NULL    |       |
| gender | char(1)     | YES  |     | 男      |       |
| tel    | char(11)    | NO   |     |         |       |
+--------+-------------+------+-----+---------+-------+
4 rows in set (0.00 sec)
```

```sql
# 成功
insert into employee values(1,'张三','男','13700102535');
```

```sh
mysql> select * from employee;
+-----+-------+--------+-------------+
| eid | ename | gender | tel         |
+-----+-------+--------+-------------+
|   1 | 张三  | 男     | 13700102535 |
+-----+-------+--------+-------------+
1 row in set (0.00 sec)
```

```sql
insert into employee(eid,ename) values(2,'李四'); #成功
```

```sh
mysql> select * from employee;
+-----+-------+--------+-------------+
| eid | ename | gender | tel         |
+-----+-------+--------+-------------+
|   1 | 张三  | 男     | 13700102535 |
|   2 | 李四  | 男     |             |
+-----+-------+--------+-------------+
2 rows in set (0.00 sec)
```

```sh
insert into employee(eid,ename) values(3,'王五');

# ERROR 1062 (23000): Duplicate entry '' for key 'tel'
# 如果 tel 有唯一性约束的话会报错，如果 tel 没有唯一性约束，可以添加成功
```

再举例：

```sql
CREATE TABLE myemp
(
  id INT AUTO_INCREMENT PRIMARY KEY,
  NAME VARCHAR(15),
  salary DOUBLE(10,2) DEFAULT 2000
);
```

（2）建表后

> alter table 表名称 modify 字段名 数据类型 default 默认值;
>
> \# 如果这个字段原来有非空约束，你还保留非空约束，那么在加默认值约束时，还得保留非空约束，否则非空约束就被删除了。
>
> \# 同理，在给某个字段加非空约束也一样，如果这个字段原来有默认值约束，你想保留，也要在 modify 语句中保留默认值约束，否则就删除了。
>
> alter table 表名称 modify 字段名 数据类型 default 默认值 not null;

```sql
create table employee
(
  eid int primary key,
  ename varchar(20),
  gender char,
  tel char(11) not null
);
```

```sh
mysql> desc employee;
+--------+-------------+------+-----+---------+-------+
| Field  | Type        | Null | Key | Default | Extra |
+--------+-------------+------+-----+---------+-------+
| eid    | int(11)     | NO   | PRI | NULL    |       |
| ename  | varchar(20) | YES  |     | NULL    |       |
| gender | char(1)     | YES  |     | NULL    |       |
| tel    | char(11)    | NO   |     | NULL    |       |
+--------+-------------+------+-----+---------+-------+
4 rows in set (0.00 sec)
```

```sql
# 给 gender 字段增加默认值约束
alter table employee modify gender char default '男';

# 给 tel 字段增加默认值约束
alter table employee modify tel char(11) default '';
```

```sh
mysql> desc employee;
+--------+-------------+------+-----+---------+-------+
| Field  | Type        | Null | Key | Default | Extra |
+--------+-------------+------+-----+---------+-------+
| eid    | int(11)     | NO   | PRI | NULL    |       |
| ename  | varchar(20) | YES  |     | NULL    |       |
| gender | char(1)     | YES  |     | 男      |       |
| tel    | char(11)    | YES  |     |         |       |
+--------+-------------+------+-----+---------+-------+
4 rows in set (0.00 sec)
```

```sql
# 给 tel 字段增加默认值约束，并保留非空约束
alter table employee modify tel char(11) default '' not null;
```

```sh
mysql> desc employee;
+--------+-------------+------+-----+---------+-------+
| Field  | Type        | Null | Key | Default | Extra |
+--------+-------------+------+-----+---------+-------+
| eid    | int(11)     | NO   | PRI | NULL    |       |
| ename  | varchar(20) | YES  |     | NULL    |       |
| gender | char(1)     | YES  |     | 男      |       |
| tel    | char(11)    | NO   |     |         |       |
+--------+-------------+------+-----+---------+-------+
4 rows in set (0.00 sec)
```

### 8.4 如何删除默认值约束

> \# 删除默认值约束，也不保留非空约束
> alter table 表名称 modify 字段名 数据类型 ;
>
> \# 删除默认值约束，保留非空约束
> alter table 表名称 modify 字段名 数据类型 not null;

```sql
# 删除 gender 字段默认值约束，如果有非空约束，也一并删除
alter table employee modify gender char;

# 删除 tel 字段默认值约束，保留非空约束
alter table employee modify tel char(11) not null;
```

```sh
mysql> desc employee;
+--------+-------------+------+-----+---------+-------+
| Field  | Type        | Null | Key | Default | Extra |
+--------+-------------+------+-----+---------+-------+
| eid    | int(11)     | NO   | PRI | NULL    |       |
| ename  | varchar(20) | YES  |     | NULL    |       |
| gender | char(1)     | YES  |     | NULL    |       |
| tel    | char(11)    | NO   |     | NULL    |       |
+--------+-------------+------+-----+---------+-------+
4 rows in set (0.00 sec)
```

## 9. 面试

**面试 1、为什么建表时，加 not null default '' 或 default 0**

答：不想让表中出现 null 值。

**面试 2、为什么不想要 null 的值**

答:（1）不好比较。null 是一种特殊值，比较时只能用专门的 is null 和 is not null 来比较。碰到运算符，通常返回 null。

​ （2）效率不高。影响提高索引效果。因此，我们往往在建表时 not null default '' 或 default 0。

**面试 3、带 AUTO_INCREMENT 约束的字段值是从 1 开始的吗？**
在 MySQL 中，默认 AUTO_INCREMENT 的初始值是 1，每新增一条记录，字段值自动加 1。设置自增属性（AUTO_INCREMENT）的时候，还可以指定第一条插入记录的自增字段的值，这样新插入的记录的自增字段值从初始值开始递增，如在表中插入第一条记录，同时指定 id 值为 5，则以后插入的记录的 id 值就会从 6 开始往上增加。添加主键约束时，往往需要设置字段自动增加属性。

**面试 4、并不是每个表都可以任意选择存储引擎？**
外键约束（FOREIGN KEY）不能跨引擎使用。

MySQL 支持多种存储引擎，每一个表都可以指定一个不同的存储引擎，需要注意的是：外键约束是用来保证数据的参照完整性的，如果表之间需要关联外键，却指定了不同的存储引擎，那么这些表之间是不能创建外键约束的。所以说，存储引擎的选择也不完全是随意的。

# 第 14 章 视图

## 1. 常见的数据库对象

| 对象                | 描述                                                                                                   |
| ------------------- | ------------------------------------------------------------------------------------------------------ |
| 表(TABLE)           | 表是存储数据的逻辑单元，以行和列的形式存在，列就是字段，行就是记录。                                   |
| 数据字典            | 就是系统表，存放数据库相关信息的表。系统表的数据通常由数据库系统维护，程序员通常不应该修改，只可查看。 |
| 约束(CONSTRAINT)    | 执行数据校验的规则，用于保证数据完整性的规则。                                                         |
| 视图(VIEW)          | 一个或者多个数据表里的数据的逻辑显示，视图并不存储数据。                                               |
| 索引(INDEX)         | 用于提高查询性能，相当于书的目录。                                                                     |
| 存储过程(PROCEDURE) | 用于完成一次完整的业务处理，没有返回值，但可通过传出参数将多个值传给调用环境。                         |
| 存储函数(FUNCTION)  | 用于完成一次特定的计算，具有一个返回值。                                                               |
| 触发器(TRIGGER)     | 相当于一个事件监听器，当数据库发生特定事件后，触发器被触发，完成相应的处理。                           |

## 2. 视图概述

![视图概述](https://img-blog.csdnimg.cn/b1c94cb71f9445109599774cf8660408.png)

### 2.1 为什么使用视图？

视图一方面可以帮我们使用表的一部分而不是所有的表，另一方面也可以针对不同的用户制定不同的查询视图。比如，针对一个公司的销售人员，我们只想给他看部分数据，而某些特殊的数据，比如采购的价格，则不会提供给他。再比如，人员薪酬是个敏感的字段，那么只给某个级别以上的人员开放，其他人的查询视图中则不提供这个字段。

刚才讲的只是视图的一个使用场景，实际上视图还有很多作用。最后，我们总结视图的优点。

### 2.2 视图的理解

- 视图是一种`虚拟表`，本身是`不具有数据`的，占用很少的内存空间，它是 SQL 中的一个重要概念。

- **视图建立在已有表的基础上**, 视图赖以建立的这些表称为**基表**。

  ![视图的理解](https://img-blog.csdnimg.cn/7f82913de1c14dd4ab0b53e64fbb5209.png)

- 视图的创建和删除只影响视图本身，不影响对应的基表。但是当对视图中的数据进行增加、删除和修改操作时，数据表中的数据会相应地发生变化，反之亦然。

- 向视图提供数据内容的语句为 SELECT 语句, 可以将视图理解为**存储起来的** **SELECT** **语句**

  - 在数据库中，视图不会保存数据，数据真正保存在数据表中。当对视图中的数据进行增加、删除和修改操作时，数据表中的数据会相应地发生变化；反之亦然。

- 视图，是向用户提供基表数据的另一种表现形式。通常情况下，小型项目的数据库可以不使用视图，但是在大型项目中，以及数据表比较复杂的情况下，视图的价值就凸显出来了，它可以帮助我们把经常查询的结果集放到虚拟表中，提升使用效率。理解和使用起来都非常方便。

## 3. 创建视图

- **在** **CREATE VIEW** **语句中嵌入子查询**

  > CREATE [OR REPLACE] > [ALGORITHM = {UNDEFINED | MERGE | TEMPTABLE}]
  > VIEW 视图名称 [(字段列表)]
  > AS 查询语句
  > [WITH [CASCADED|LOCAL] CHECK OPTION]

- 精简版

  > CREATE VIEW 视图名称
  > AS 查询语句

### 3.1 创建单表视图

举例：

```sql
CREATE VIEW empvu80
AS
SELECT  employee_id, last_name, salary
FROM    employees
WHERE   department_id = 80;
```

查询视图：

```sql
SELECT *
FROM   salvu80;
```

![创建单表视图](https://img-blog.csdnimg.cn/6812ac798e3343789d9f852a60b01b65.png)

举例：

```sql
CREATE VIEW emp_year_salary (ename,year_salary)
AS
SELECT ename,salary*12*(1+IFNULL(commission_pct,0))
FROM t_employee;
```

举例：

```sql
CREATE VIEW salvu50
AS
SELECT  employee_id ID_NUMBER, last_name NAME,salary*12 ANN_SALARY
FROM    employees
WHERE   department_id = 50;
```

说明 1：实际上就是我们在 SQL 查询语句的基础上封装了视图 VIEW，这样就会基于 SQL 语句的结果集形成一张虚拟表。

说明 2：在创建视图时，没有在视图名后面指定字段列表，则视图中字段列表默认和 SELECT 语句中的字段列表一致。如果 SELECT 语句中给字段取了别名，那么视图中的字段名和别名相同。

### 3.2 创建多表联合视图

举例：

```sql
CREATE VIEW empview
AS
SELECT employee_id emp_id,last_name NAME,department_name
FROM employees e,departments d
WHERE e.department_id = d.department_id;
```

```sql
CREATE VIEW emp_dept
AS
SELECT ename,dname
FROM t_employee LEFT JOIN t_department
ON t_employee.did = t_department.did;
```

```sql
CREATE VIEW	dept_sum_vu
(name, minsal, maxsal, avgsal)
AS
SELECT d.department_name, MIN(e.salary), MAX(e.salary),AVG(e.salary)
FROM employees e, departments d
WHERE e.department_id = d.department_id
GROUP BY  d.department_name;
```

- **利用视图对数据进行格式化**

  我们经常需要输出某个格式的内容，比如我们想输出员工姓名和对应的部门名，对应格式为 emp_name(department_name)，就可以使用视图来完成数据格式化的操作：

  ```sql
  CREATE VIEW emp_depart
  AS
  SELECT CONCAT(last_name,'(',department_name,')') AS emp_dept
  FROM employees e JOIN departments d
  WHERE e.department_id = d.department_id
  ```

### 3.3 基于视图创建视图

当我们创建好一张视图之后，还可以在它的基础上继续创建视图。

举例：联合“emp_dept”视图和“emp_year_salary”视图查询员工姓名、部门名称、年薪信息创建 “emp_dept_ysalary”视图。

```sql
CREATE VIEW emp_dept_ysalary
AS
SELECT emp_dept.ename,dname,year_salary
FROM emp_dept INNER JOIN emp_year_salary
ON emp_dept.ename = emp_year_salary.ename;
```

## 4. 查看视图

语法 1：查看数据库的表对象、视图对象

```sql
SHOW TABLES;
```

语法 2：查看视图的结构

> DESC / DESCRIBE 视图名称;

语法 3：查看视图的属性信息

> \# 查看视图信息（显示数据表的存储引擎、版本、数据行数和数据大小等）
> SHOW TABLE STATUS LIKE '视图名称'\G

执行结果显示，注释 Comment 为 VIEW，说明该表为视图，其他的信息为 NULL，说明这是一个虚表。

语法 4：查看视图的详细定义信息

> SHOW CREATE VIEW 视图名称;

## 5. 更新视图的数据

### 5.1 一般情况

MySQL 支持使用 INSERT、UPDATE 和 DELETE 语句对视图中的数据进行插入、更新和删除操作。当视图中的数据发生变化时，数据表中的数据也会发生变化，反之亦然。

举例：UPDATE 操作

```sh
mysql> SELECT ename,tel FROM emp_tel WHERE ename = '张三';
+---------+-------------+
| ename   | tel         |
+---------+-------------+
| 张三   | 13789098765 |
+---------+-------------+
1 row in set (0.01 sec)

mysql> UPDATE emp_tel SET tel = '13789091234' WHERE ename = '张三';
Query OK, 1 row affected (0.01 sec)
Rows matched: 1  Changed: 1  Warnings: 0

mysql> SELECT ename,tel FROM emp_tel WHERE ename = '张三';
+---------+-------------+
| ename    | tel         |
+---------+-------------+
|   张三 | 13789091234 |
+---------+-------------+
1 row in set (0.00 sec)

mysql> SELECT ename,tel FROM t_employee WHERE ename = '张三';
+---------+-------------+
| ename   | tel         |
+---------+-------------+
| 张三   | 13789091234 |
+---------+-------------+
1 row in set (0.00 sec)
```

举例：DELETE 操作

```sh
mysql> SELECT ename,tel FROM emp_tel WHERE ename = '张三';
+---------+-------------+
| ename  	| tel           |
+---------+-------------+
| 张三 	| 13789091234 |
+---------+-------------+
1 row in set (0.00 sec)

mysql> DELETE FROM emp_tel  WHERE ename = '张三';
Query OK, 1 row affected (0.01 sec)

mysql> SELECT ename,tel FROM emp_tel WHERE ename = '张三';
Empty set (0.00 sec)

mysql> SELECT ename,tel FROM t_employee WHERE ename = '张三';
Empty set (0.00 sec)
```

### 5.2 不可更新的视图

要使视图可更新，视图中的行和底层基本表中的行之间必须存在`一对一`的关系。另外当视图定义出现如下情况时，视图不支持更新操作：

- 在定义视图的时候指定了“ALGORITHM = TEMPTABLE”，视图将不支持 INSERT 和 DELETE 操作；

- 视图中不包含基表中所有被定义为非空又未指定默认值的列，视图将不支持 INSERT 操作；

- 在定义视图的 SELECT 语句中使用了`JOIN联合查询`，视图将不支持 INSERT 和 DELETE 操作；

- 在定义视图的 SELECT 语句后的字段列表中使用了`数学表达式`或`子查询`，视图将不支持 INSERT，也不支持 UPDATE 使用了数学表达式、子查询的字段值；

- 在定义视图的 SELECT 语句后的字段列表中使用`DISTINCT`、`聚合函数`、`GROUP BY`、`HAVING`、`UNION`等，视图将不支持 INSERT、UPDATE、DELETE；

- 在定义视图的 SELECT 语句中包含了子查询，而子查询中引用了 FROM 后面的表，视图将不支持 INSERT、UPDATE、DELETE；

- 视图定义基于一个`不可更新视图`；

- 常量视图。

举例：

```sh
mysql> CREATE OR REPLACE VIEW emp_dept
    -> (ename,salary,birthday,tel,email,hiredate,dname)
    -> AS SELECT ename,salary,birthday,tel,email,hiredate,dname
    -> FROM t_employee INNER JOIN t_department
    -> ON t_employee.did = t_department.did ;
Query OK, 0 rows affected (0.01 sec)
```

```sh
mysql> INSERT INTO emp_dept(ename,salary,birthday,tel,email,hiredate,dname)
    -> VALUES('张三',15000,'1995-01-08','18201587896',
    -> 'zs@myxh.com','2022-02-14','新部门');

# ERROR 1393 (HY000): Can not modify more than one base table through a join view 'myxh_chapter9.emp_dept'
```

从上面的 SQL 执行结果可以看出，在定义视图的 SELECT 语句中使用了 JOIN 联合查询，视图将不支持更新操作。

> 虽然可以更新视图数据，但总的来说，视图作为`虚拟表`，主要用于`方便查询`，不建议更新视图的数据。**对视图数据的更改，都是通过对实际数据表里数据的操作来完成的。**

## 6. 修改、删除视图

### 6.1 修改视图

方式 1：使用 CREATE **OR REPLACE** VIEW 子句**修改视图**

```sql
CREATE OR REPLACE VIEW empvu80
(id_number, name, sal, department_id)
AS
SELECT  employee_id, first_name || ' ' || last_name, salary, department_id
FROM employees
WHERE department_id = 80;
```

> 说明：CREATE VIEW 子句中各列的别名应和子查询中各列相对应。

方式 2：ALTER VIEW

修改视图的语法是：

> ALTER VIEW 视图名称
> AS
> 查询语句

### 6.2 删除视图

- 删除视图只是删除视图的定义，并不会删除基表的数据。

- 删除视图的语法是：

  > DROP VIEW IF EXISTS 视图名称;

  > DROP VIEW IF EXISTS 视图名称 1,视图名称 2,视图名称 3, ... ;

- 举例：

  ```sql
  DROP VIEW empvu80;
  ```

- 说明：基于视图 a、b 创建了新的视图 c，如果将视图 a 或者视图 b 删除，会导致视图 c 的查询失败。这样的视图 c 需要手动删除或修改，否则影响使用。

## 7. 总结

### 7.1 视图优点

**1. 操作简单**

将经常使用的查询操作定义为视图，可以使开发人员不需要关心视图对应的数据表的结构、表与表之间的关联关系，也不需要关心数据表之间的业务逻辑和查询条件，而只需要简单地操作视图即可，极大简化了开发人员对数据库的操作。

**2. 减少数据冗余**

视图跟实际数据表不一样，它存储的是查询语句。所以，在使用的时候，我们要通过定义视图的查询语句来获取结果集。而视图本身不存储数据，不占用数据存储的资源，减少了数据冗余。

**3. 数据安全**

MySQL 将用户对数据的`访问限制`在某些数据的结果集上，而这些数据的结果集可以使用视图来实现。用户不必直接查询或操作数据表。这也可以理解为视图具有`隔离性`。视图相当于在用户和实际的数据表之间加了一层虚拟表。

![数据安全](https://img-blog.csdnimg.cn/344beda61b184680ba9d52d422c424b8.png)

同时，MySQL 可以根据权限将用户对数据的访问限制在某些视图上，**用户不需要查询数据表，可以直接通过视图获取数据表中的信息**。这在一定程度上保障了数据表中数据的安全性。

**4. 适应灵活多变的需求**

当业务系统的需求发生变化后，如果需要改动数据表的结构，则工作量相对较大，可以使用视图来减少改动的工作量。这种方式在实际工作中使用得比较多。

**5. 能够分解复杂的查询逻辑**

数据库中如果存在复杂的查询逻辑，则可以将问题进行分解，创建多个视图获取数据，再将创建的多个视图结合起来，完成复杂的查询逻辑。

### 7.2 视图不足

如果我们在实际数据表的基础上创建了视图，那么，**如果实际数据表的结构变更了，我们就需要及时对相关的视图进行相应的维护**。特别是嵌套的视图（就是在视图的基础上创建视图），维护会变得比较复杂，`可读性不好`，容易变成系统的潜在隐患。因为创建视图的 SQL 查询可能会对字段重命名，也可能包含复杂的逻辑，这些都会增加维护的成本。

实际项目中，如果视图过多，会导致数据库维护成本的问题。

所以，在创建视图的时候，你要结合实际项目需求，综合考虑视图的优点和不足，这样才能正确使用视图，使系统整体达到最优。

# 第 15 章 存储过程与函数

MySQL 从 5.0 版本开始支持存储过程和函数。存储过程和函数能够将复杂的 SQL 逻辑封装在一起，应用程序无须关注存储过程和函数内部复杂的 SQL 逻辑，而只需要简单地调用存储过程和函数即可。

## 1. 存储过程概述

### 1.1 理解

**含义**：存储过程的英文是 `Stored Procedure`。它的思想很简单，就是一组经过`预先编译`的 SQL 语句的封装。

执行过程：存储过程预先存储在 MySQL 服务器上，需要执行的时候，客户端只需要向服务器端发出调用存储过程的命令，服务器端就可以把预先存储好的这一系列 SQL 语句全部执行。

**好处**：

1、简化操作，提高了 sql 语句的重用性，减少了开发程序员的压力。

2、减少操作过程中的失误，提高效率。

3、减少网络传输量（客户端不需要把所有的 SQL 语句通过网络发给服务器）。

4、减少了 SQL 语句暴露在网上的风险，也提高了数据查询的安全性。

**和视图、函数的对比**：

它和视图有着同样的优点，清晰、安全，还可以减少网络传输量。不过它和视图不同，视图是`虚拟表`，通常不对底层数据表直接操作，而存储过程是程序化的 SQL，可以`直接操作底层数据表`，相比于面向集合的操作方式，能够实现一些更复杂的数据处理。

一旦存储过程被创建出来，使用它就像使用函数一样简单，我们直接通过调用存储过程名即可。相较于函数，存储过程是`没有返回值`的。

### 1.2 分类

存储过程的参数类型可以是 IN、OUT 和 INOUT。根据这点分类如下：

1、没有参数（无参数无返回）。

2、仅仅带 IN 类型（有参数无返回）。

3、仅仅带 OUT 类型（无参数有返回）。

4、既带 IN 又带 OUT（有参数有返回）。

5、带 INOUT（有参数有返回）。

注意：IN、OUT、INOUT 都可以在一个存储过程中带多个。

## 2. 创建存储过程

### 2.1 语法分析

语法：

> CREATE PROCEDURE 存储过程名(IN|OUT|INOUT 参数名 参数类型,...)
> [characteristics ...]
> BEGIN
> &nbsp; 存储过程体
>
> END

类似于 Java 中的方法：

> 修饰符 返回类型 方法名(参数类型 参数名, ...)
> {
> &nbsp; 方法体;
> }

说明：

1、参数前面的符号的意思。

- `IN`：当前参数为输入参数，也就是表示入参；

  存储过程只是读取这个参数的值。如果没有定义参数种类，`默认就是 IN`，表示输入参数。

- `OUT`：当前参数为输出参数，也就是表示出参；

  执行完成之后，调用这个存储过程的客户端或者应用程序就可以读取这个参数返回的值了。

- `INOUT`：当前参数既可以为输入参数，也可以为输出参数。

2、形参类型可以是 MySQL 数据库中的任意类型。

3、`characteristics` 表示创建存储过程时指定的对存储过程的约束条件，其取值信息如下：

> LANGUAGE SQL
> | [NOT] DETERMINISTIC
> | { CONTAINS SQL | NO SQL | READS SQL DATA | MODIFIES SQL DATA }
> | SQL SECURITY { DEFINER | INVOKER }
> | COMMENT 'string'

- `LANGUAGE SQL`：说明存储过程执行体是由 SQL 语句组成的，当前系统支持的语言为 SQL。

- `[NOT] DETERMINISTIC`：指明存储过程执行的结果是否确定。DETERMINISTIC 表示结果是确定的。每次执行存储过程时，相同的输入会得到相同的输出。NOT DETERMINISTIC 表示结果是不确定的，相同的输入可能得到不同的输出。如果没有指定任意一个值，默认为 NOT DETERMINISTIC。

- `{ CONTAINS SQL | NO SQL | READS SQL DATA | MODIFIES SQL DATA }`：指明子程序使用 SQL 语句的限制。

  - CONTAINS SQL 表示当前存储过程的子程序包含 SQL 语句，但是并不包含读写数据的 SQL 语句；

  - NO SQL 表示当前存储过程的子程序中不包含任何 SQL 语句；

  - READS SQL DATA 表示当前存储过程的子程序中包含读数据的 SQL 语句；

  - MODIFIES SQL DATA 表示当前存储过程的子程序中包含写数据的 SQL 语句；

  - 默认情况下，系统会指定为 CONTAINS SQL。

- `SQL SECURITY { DEFINER | INVOKER }`：执行当前存储过程的权限，即指明哪些用户能够执行当前存储过程。

  - `DEFINER`表示只有当前存储过程的创建者或者定义者才能执行当前存储过程；

  - `INVOKER`表示拥有当前存储过程的访问权限的用户能够执行当前存储过程；

  - 如果没有设置相关的值，则 MySQL 默认指定值为 DEFINER；

- `COMMENT 'string'`：注释信息，可以用来描述存储过程。

4、存储过程体中可以有多条 SQL 语句，如果仅仅一条 SQL 语句，则可以省略 BEGIN 和 END。

编写存储过程并不是一件简单的事情，可能存储过程中需要复杂的 SQL 语句。

> 1. BEGIN ... END：BEGIN ... END 中间包含了多个语句，每个语句都以（;）号为结束符。
> 2. DECLARE：DECLARE 用来声明变量，使用的位置在于 BEGIN ... END 语句中间，而且需要在其他语句使用之前进行变量的声明。
> 3. SET：赋值语句，用于对变量进行赋值。
> 4. SELECT ... INTO：把从数据表中查询的结果存放到变量中，也就是为变量赋值。

5、需要设置新的结束标记

> DELIMITER 新的结束标记

因为 MySQL 默认的语句结束符号为分号‘;’。为了避免与存储过程中 SQL 语句结束符相冲突，需要使用 DELIMITER 改变存储过程的结束符。

比如：“DELIMITER //”语句的作用是将 MySQL 的结束符设置为//，并以“END //”结束存储过程。存储过程定义完毕之后再使用“DELIMITER ;”恢复默认结束符。DELIMITER 也可以指定其他符号作为结束符。

当使用 DELIMITER 命令时，应该避免使用反斜杠（‘\’）字符，因为反斜线是 MySQL 的转义字符。

示例：

> DELIMITER $
>
> CREATE PROCEDURE 存储过程名(IN|OUT|INOUT 参数名 参数类型, ...)
> [characteristics ...]
> BEGIN
> &nbsp; sql 语句 1;
> &nbsp; sql 语句 2;
>
> END $

### 2.2 代码举例

举例 1：创建存储过程 select_all_data()，查看 emps 表的所有数据。

```sql
DELIMITER $

CREATE PROCEDURE select_all_data()
BEGIN
  SELECT * FROM emps;

END $

DELIMITER ;
```

举例 2：创建存储过程 avg_employee_salary()，返回所有员工的平均工资。

```sql
DELIMITER //

CREATE PROCEDURE avg_employee_salary ()
BEGIN
  SELECT AVG(salary) AS avg_salary FROM emps;
END //

DELIMITER ;
```

举例 3：创建存储过程 show_max_salary()，用来查看“emps”表的最高薪资值。

```sql
CREATE PROCEDURE show_max_salary()
  LANGUAGE SQL
  NOT DETERMINISTIC
  CONTAINS SQL
  SQL SECURITY DEFINER
  COMMENT '查看最高薪资'
  BEGIN
    SELECT MAX(salary) FROM emps;
  END //

DELIMITER ;
```

举例 4：创建存储过程 show_min_salary()，查看“emps”表的最低薪资值。并将最低薪资通过 OUT 参数“ms”输出。

```sql
DELIMITER //

CREATE PROCEDURE show_min_salary(OUT ms DOUBLE)
  BEGIN
    SELECT MIN(salary) INTO ms FROM emps;
  END //

DELIMITER ;
```

举例 5：创建存储过程 show_someone_salary()，查看“emps”表的某个员工的薪资，并用 IN 参数 empname 输入员工姓名。

```sql
DELIMITER //

CREATE PROCEDURE show_someone_salary(IN empname VARCHAR(20))
  BEGIN
    SELECT salary FROM emps WHERE ename = empname;
  END //

DELIMITER ;
```

举例 6：创建存储过程 show_someone_salary2()，查看“emps”表的某个员工的薪资，并用 IN 参数 empname 输入员工姓名，用 OUT 参数 empsalary 输出员工薪资。

```sql
DELIMITER //

CREATE PROCEDURE show_someone_salary2(IN empname VARCHAR(20),OUT empsalary DOUBLE)
  BEGIN
    SELECT salary INTO empsalary FROM emps WHERE ename = empname;
  END //

DELIMITER ;
```

举例 7：创建存储过程 show_mgr_name()，查询某个员工领导的姓名，并用 INOUT 参数“empname”输入员工姓名，输出领导的姓名。

```sql
DELIMITER //

CREATE PROCEDURE show_mgr_name(INOUT empname VARCHAR(20))
  BEGIN
    SELECT ename INTO empname FROM emps
    WHERE eid = (SELECT MID FROM emps WHERE ename=empname);
  END //

DELIMITER ;
```

## 3. 调用存储过程

### 3.1 调用格式

存储过程有多种调用方法。存储过程必须使用 CALL 语句调用，并且存储过程和数据库相关，如果要执行其他数据库中的存储过程，需要指定数据库名称，例如 CALL dbname.procname。

> CALL 存储过程名(实参列表)

**格式：**

1、调用 in 模式的参数：

> CALL sp1('值');

2、调用 out 模式的参数：

```sql
SET @name;
CALL sp1(@name);
SELECT @name;
```

3、调用 inout 模式的参数：

> SET @name=值;
> CALL sp1(@name);
> SELECT @name;

### 3.2 代码举例

**举例 1：**

```sql
DELIMITER //

CREATE PROCEDURE CountProc(IN sid INT,OUT num INT)
BEGIN
  SELECT COUNT(*) INTO num FROM fruits
  WHERE s_id = sid;
END //

DELIMITER ;
```

调用存储过程：

```sh
mysql> CALL CountProc (101, @num);
Query OK, 1 row affected (0.00 sec)
```

查看返回结果：

```sh
mysql> SELECT @num;
```

该存储过程返回了指定 s_id=101 的水果商提供的水果种类，返回值存储在 num 变量中，使用 SELECT 查看，返回结果为 3。

**举例 2：** 创建存储过程，实现累加运算，计算 1 + 2 + ... + n 等于多少。具体的代码如下：

```sql
DELIMITER //
CREATE PROCEDURE `add_num`(IN n INT)
BEGIN
       DECLARE i INT;
       DECLARE sum INT;

       SET i = 1;
       SET sum = 0;
       WHILE i <= n DO
              SET sum = sum + i;
              SET i = i +1;
       END WHILE;
       SELECT sum;
END //
DELIMITER ;
```

如果你用的是 Navicat 工具，那么在编写存储过程的时候，Navicat 会自动设置 DELIMITER 为其他符号，我们不需要再进行 DELIMITER 的操作。

直接使用 `CALL add_num(50);`即可。这里我传入的参数为 50，也就是统计 1 + 2 + ... + 50 的积累之和。

### 3.3 如何调试

在 MySQL 中，存储过程不像普通的编程语言（比如 VC++、Java 等）那样有专门的集成开发环境。因此，你可以通过 SELECT 语句，把程序执行的中间结果查询出来，来调试一个 SQL 语句的正确性。调试成功之后，把 SELECT 语句后移到下一个 SQL 语句之后，再调试下一个 SQL 语句。这样`逐步推进`，就可以完成对存储过程中所有操作的调试了。当然，你也可以把存储过程中的 SQL 语句复制出来，逐段单独调试。

## 4. 存储函数的使用

前面学习了很多函数，使用这些函数可以对数据进行的各种处理操作，极大地提高用户对数据库的管理效率。MySQL 支持自定义函数，定义好之后，调用方式与调用 MySQL 预定义的系统函数一样。

### 4.1 语法分析

学过的函数：LENGTH、SUBSTR、CONCAT 等。

语法格式：

> CREATE FUNCTION 函数名(参数名 参数类型,...)
> RETURNS 返回值类型
> [characteristics ...]
> BEGIN
> &nbsp; # 函数体中肯定有 RETURN 语句
> &nbsp; 函数体
>
> END

说明：

1、参数列表：指定参数为 IN、OUT 或 INOUT 只对 PROCEDURE 是合法的，FUNCTION 中总是默认为 IN 参数。

2、RETURNS type 语句表示函数返回数据的类型；

RETURNS 子句只能对 FUNCTION 做指定，对函数而言这是`强制`的。它用来指定函数的返回类型，而且函数体必须包含一个`RETURN value`语句。

3、characteristic 创建函数时指定的对函数的约束。取值与创建存储过程时相同，这里不再赘述。

4、函数体也可以用 BEGIN...END 来表示 SQL 代码的开始和结束。如果函数体只有一条语句，也可以省略 BEGIN...END。

### 4.2 调用存储函数

在 MySQL 中，存储函数的使用方法与 MySQL 内部函数的使用方法是一样的。换言之，用户自己定义的存储函数与 MySQL 内部函数是一个性质的。区别在于，存储函数是`用户自己定义`的，而内部函数是 MySQL 的`开发者定义`的。

> SELECT 函数名(实参列表)

### 4.3 代码举例

**举例 1：**

创建存储函数，名称为 email_by_name()，参数定义为空，该函数查询 Abel 的 email，并返回，数据类型为字符串型。

```sql
DELIMITER //

CREATE FUNCTION email_by_name()
RETURNS VARCHAR(25)
DETERMINISTIC
CONTAINS SQL
BEGIN
  RETURN (SELECT email FROM employees WHERE last_name = 'Abel');
END //

DELIMITER ;
```

调用：

```sql
SELECT email_by_name();
```

**举例 2：**

创建存储函数，名称为 email_by_id()，参数传入 emp_id，该函数查询 emp_id 的 email，并返回，数据类型为字符串型。

```sql
DELIMITER //

CREATE FUNCTION email_by_id(emp_id INT)
RETURNS VARCHAR(25)
DETERMINISTIC
CONTAINS SQL
BEGIN
  RETURN (SELECT email FROM employees WHERE employee_id = emp_id);
END //

DELIMITER ;
```

调用：

```sql
SET @emp_id = 102;
SELECT email_by_id(102);
```

**举例 3：**

创建存储函数 count_by_id()，参数传入 dept_id，该函数查询 dept_id 部门的员工人数，并返回，数据类型为整型。

```sql
DELIMITER //

CREATE FUNCTION count_by_id(dept_id INT)
RETURNS INT
  LANGUAGE SQL
  NOT DETERMINISTIC
  READS SQL DATA
  SQL SECURITY DEFINER
  COMMENT '查询部门平均工资'
BEGIN
  RETURN (SELECT COUNT(*) FROM employees WHERE department_id = dept_id);

END //

DELIMITER ;
```

调用：

```sql
SET @dept_id = 50;
SELECT count_by_id(@dept_id);
```

**注意：**

若在创建存储函数中报错“`you might want to use the less safe log_bin_trust_function_creators variable`”，有两种处理方法：

- 方式 1：加上必要的函数特性“[NOT] DETERMINISTIC”和“{CONTAINS SQL | NO SQL | READS SQL DATA | MODIFIES SQL DATA}”

- 方式 2：

  ```sh
  mysql> SET GLOBAL log_bin_trust_function_creators = 1;
  ```

### 4.4 对比存储函数和存储过程

|          | 关键字    | 调用语法        | 返回值              | 应用场景                           |
| -------- | --------- | --------------- | ------------------- | ---------------------------------- |
| 存储过程 | PROCEDURE | CALL 存储过程() | 理解为有 0 个或多个 | 一般用于更新。                     |
| 存储函数 | FUNCTION  | SELECT 函数()   | 只能是一个          | 一般用于查询结果为一个值并返回时。 |

此外，**存储函数可以放在查询语句中使用，存储过程不行**。反之，存储过程的功能更加强大，包括能够执行对表的操作（比如创建表，删除表等）和事务操作，这些功能是存储函数不具备的。

## 5. 存储过程和函数的查看、修改、删除

### 5.1 查看

创建完之后，怎么知道我们创建的存储过程、存储函数是否成功了呢？

MySQL 存储了存储过程和函数的状态信息，用户可以使用 SHOW STATUS 语句或 SHOW CREATE 语句来查看，也可直接从系统的 information_schema 数据库中查询。这里介绍 3 种方法。

**1. 使用 SHOW CREATE 语句查看存储过程和函数的创建信息**

基本语法结构如下：

> SHOW CREATE {PROCEDURE | FUNCTION} 存储过程名或函数名

举例：

```sql
SHOW CREATE FUNCTION test_db.CountProc \G
```

**2. 使用 SHOW STATUS 语句查看存储过程和函数的状态信息**

基本语法结构如下：

> SHOW {PROCEDURE | FUNCTION} STATUS [LIKE 'pattern']

这个语句返回子程序的特征，如数据库、名字、类型、创建者及创建和修改日期。

[LIKE 'pattern']：匹配存储过程或函数的名称，可以省略。当省略不写时，会列出 MySQL 数据库中存在的所有存储过程或函数的信息。

举例：SHOW STATUS 语句示例，代码如下：

```sh
mysql> SHOW PROCEDURE STATUS LIKE 'SELECT%' \G
*************************** 1. row ***************************
                  Db: test_db
                Name: SelectAllData
                Type: PROCEDURE
             Definer: root@localhost
            Modified: 2023-8-21 15:00:00
             Created: 2023-8-21 15:00:00
       Security_type: DEFINER
             Comment:
character_set_client: utf8mb4
collation_connection: utf8mb4_general_ci
  Database Collation: utf8mb4_general_ci
1 row in set (0.00 sec)
```

**3. 从 information_schema.Routines 表中查看存储过程和函数的信息**

MySQL 中存储过程和函数的信息存储在 information_schema 数据库下的 Routines 表中。可以通过查询该表的记录来查询存储过程和函数的信息。其基本语法形式如下：

> SELECT \* FROM information_schema.Routines
> WHERE ROUTINE_NAME='存储过程或函数的名' [AND ROUTINE_TYPE = {'PROCEDURE|FUNCTION'}];

说明：如果在 MySQL 数据库中存在存储过程和函数名称相同的情况，最好指定 ROUTINE_TYPE 查询条件来指明查询的是存储过程还是函数。

举例：从 Routines 表中查询名称为 CountProc 的存储函数的信息，代码如下：

```sql
SELECT * FROM information_schema.Routines
WHERE ROUTINE_NAME='count_by_id'　AND　ROUTINE_TYPE = 'FUNCTION' \G
```

### 5.2 修改

修改存储过程或函数，不影响存储过程或函数功能，只是修改相关特性。使用 ALTER 语句实现。

> ALTER {PROCEDURE | FUNCTION} 存储过程或函数的名 [characteristic ...]

其中，characteristic 指定存储过程或函数的特性，其取值信息与创建存储过程、函数时的取值信息略有不同。

> { CONTAINS SQL | NO SQL | READS SQL DATA | MODIFIES SQL DATA }
> | SQL SECURITY { DEFINER | INVOKER }
> | COMMENT 'string'

- `CONTAINS SQL`，表示子程序包含 SQL 语句，但不包含读或写数据的语句。

- `NO SQL`，表示子程序中不包含 SQL 语句。

- `READS SQL DATA`，表示子程序中包含读数据的语句。

- `MODIFIES SQL DATA`，表示子程序中包含写数据的语句。

- `SQL SECURITY { DEFINER | INVOKER }`，指明谁有权限来执行。

  - `DEFINER`，表示只有定义者自己才能够执行。

  - `INVOKER`，表示调用者可以执行。

- `COMMENT 'string'`，表示注释信息。

> 修改存储过程使用 ALTER PROCEDURE 语句，修改存储函数使用 ALTER FUNCTION 语句。但是，这两个语句的结构是一样的，语句中的所有参数也是一样的。

**举例 1：**

修改存储过程 CountProc 的定义。将读写权限改为 MODIFIES SQL DATA，并指明调用者可以执行，代码如下：

```sql
ALTER　PROCEDURE　CountProc
MODIFIES SQL DATA
SQL SECURITY INVOKER ;
```

查询修改后的信息：

```sql
SELECT specific_name,sql_data_access,security_type
FROM information_schema.`ROUTINES`
WHERE routine_name = 'CountProc' AND routine_type = 'PROCEDURE';
```

结果显示，存储过程修改成功。从查询的结果可以看出，访问数据的权限（SQL*DATA* ACCESS）已经变成 MODIFIES SQL DATA，安全类型（SECURITY_TYPE）已经变成 INVOKER。

**举例 2：**

修改存储函数 CountProc 的定义。将读写权限改为 READS SQL DATA，并加上注释信息“FIND NAME”，代码如下：

```sql
ALTER　FUNCTION　CountProc
READS SQL DATA
COMMENT 'FIND NAME' ;
```

存储函数修改成功。从查询的结果可以看出，访问数据的权限（SQL_DATA_ACCESS）已经变成 READS SQL DATA，函数注释（ROUTINE_COMMENT）已经变成 FIND NAME。

### 5.3 删除

删除存储过程和函数，可以使用 DROP 语句，其语法结构如下：

> DROP {PROCEDURE | FUNCTION} [IF EXISTS] 存储过程或函数的名

IF EXISTS：如果程序或函数不存储，它可以防止发生错误，产生一个用 SHOW WARNINGS 查看的警告。

举例：

```sql
DROP PROCEDURE CountProc;
```

```sql
DROP FUNCTION CountProc;
```

## 6. 关于存储过程使用的争议

尽管存储过程有诸多优点，但是对于存储过程的使用，**一直都存在着很多争议**，比如有些公司对于大型项目要求使用存储过程，而有些公司在手册中明确禁止使用存储过程，为什么这些公司对存储过程的使用需求差别这么大呢？

### 6.1 优点

**1、存储过程可以一次编译多次使用。** 存储过程只在创建时进行编译，之后的使用都不需要重新编译，这就提升了 SQL 的执行效率。

**2、可以减少开发工作量。** 将代码`封装`成模块，实际上是编程的核心思想之一，这样可以把复杂的问题拆解成不同的模块，然后模块之间可以`重复使用`，在减少开发工作量的同时，还能保证代码的结构清晰。

**3、存储过程的安全性强。** 我们在设定存储过程的时候可以`设置对用户的使用权限`，这样就和视图一样具有较强的安全性。

**4、可以减少网络传输量。** 因为代码封装到存储过程中，每次使用只需要调用存储过程即可，这样就减少了网络传输量。

**5、良好的封装性。** 在进行相对复杂的数据库操作时，原本需要使用一条一条的 SQL 语句，可能要连接多次数据库才能完成的操作，现在变成了一次存储过程，只需要`连接一次即可`。

### 6.2 缺点

基于上面这些优点，不少大公司都要求大型项目使用存储过程，比如微软、IBM 等公司。但是国内的阿里并不推荐开发人员使用存储过程，这是为什么呢？

> #### 阿里开发规范
>
> 【强制】禁止使用存储过程，存储过程难以调试和扩展，更没有移植性。

存储过程虽然有诸如上面的好处，但缺点也是很明显的。

**1、可移植性差。** 存储过程不能跨数据库移植，比如在 MySQL、Oracle 和 SQL Server 里编写的存储过程，在换成其他数据库时都需要重新编写。

**2、调试困难。** 只有少数 DBMS 支持存储过程的调试。对于复杂的存储过程来说，开发和维护都不容易。虽然也有一些第三方工具可以对存储过程进行调试，但要收费。

**3、存储过程的版本管理很困难。** 比如数据表索引发生变化了，可能会导致存储过程失效。我们在开发软件的时候往往需要进行版本管理，但是存储过程本身没有版本控制，版本迭代更新的时候很麻烦。

**4、它不适合高并发的场景。** 高并发的场景需要减少数据库的压力，有时数据库会采用分库分表的方式，而且对可扩展性要求很高，在这种情况下，存储过程会变得难以维护，`增加数据库的压力`，显然就不适用了。

小结：

存储过程既方便，又有局限性。尽管不同的公司对存储过程的态度不一，但是对于我们开发人员来说，不论怎样，掌握存储过程都是必备的技能之一。

# 第 16 章 变量、流程控制与游标

## 1. 变量

在 MySQL 数据库的存储过程和函数中，可以使用变量来存储查询或计算的中间结果数据，或者输出最终的结果数据。

在 MySQL 数据库中，变量分为`系统变量`以及`用户自定义变量`。

### 1.1 系统变量

#### 1.1.1 系统变量分类

变量由系统定义，不是用户定义，属于`服务器`层面。启动 MySQL 服务，生成 MySQL 服务实例期间，MySQL 将为 MySQL 服务器内存中的系统变量赋值，这些系统变量定义了当前 MySQL 服务实例的属性、特征。这些系统变量的值要么是`编译MySQL时参数`的默认值，要么是`配置文件`（例如 my.ini 等）中的参数值。大家可以通过网址 https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html 查看 MySQL 文档的系统变量。

系统变量分为全局系统变量（需要添加`global` 关键字）以及会话系统变量（需要添加 `session` 关键字），有时也把全局系统变量简称为全局变量，有时也把会话系统变量称为 local 变量。**如果不写，默认会话级别。** 静态变量（在 MySQL 服务实例运行期间它们的值不能使用 set 动态修改）属于特殊的全局系统变量。

每一个 MySQL 客户机成功连接 MySQL 服务器后，都会产生与之对应的会话。会话期间，MySQL 服务实例会在 MySQL 服务器内存中生成与该会话对应的会话系统变量，这些会话系统变量的初始值是全局系统变量值的复制。如下图：

![系统变量分类](https://img-blog.csdnimg.cn/04d5b717dbdc4a58b4078f11d810c153.png)

- 全局系统变量针对于所有会话（连接）有效，但`不能跨重启`。

- 会话系统变量仅针对于当前会话（连接）有效。会话期间，当前会话对某个会话系统变量值的修改，不会影响其他会话同一个会话系统变量的值。

- 会话 1 对某个全局系统变量值的修改会导致会话 2 中同一个全局系统变量值的修改。

在 MySQL 中有些系统变量只能是全局的，例如 max_connections 用于限制服务器的最大连接数；有些系统变量作用域既可以是全局又可以是会话，例如 character_set_client 用于设置客户端的字符集；有些系统变量的作用域只能是当前会话，例如 pseudo_thread_id 用于标记当前会话的 MySQL 连接 ID。

#### 1.1.2 查看系统变量

- **查看所有或部分系统变量**

  ```sql
  # 查看所有全局变量
  SHOW GLOBAL VARIABLES;

  # 查看所有会话变量
  SHOW SESSION VARIABLES;

  # 或者
  SHOW VARIABLES;
  ```

  > \# 查看满足条件的部分系统变量
  > SHOW GLOBAL VARIABLES LIKE '%标识符%';
  >
  > \# 查看满足条件的部分会话变量
  > SHOW SESSION VARIABLES LIKE '%标识符%';

  举例：

  ```sql
  SHOW GLOBAL VARIABLES LIKE 'admin_%';
  ```

- **查看指定系统变量**

  作为 MySQL 编码规范，MySQL 中的系统变量以`两个“@”`开头，其中“@@global”仅用于标记全局系统变量，“@@session”仅用于标记会话系统变量。“@@”首先标记会话系统变量，如果会话系统变量不存在，则标记全局系统变量。

  > \# 查看指定的系统变量的值
  > SELECT @@global.变量名;
  >
  > \# 查看指定的会话变量的值
  > SELECT @@session.变量名;
  >
  > \# 或者
  > SELECT @@变量名;

- **修改系统变量的值**

  有些时候，数据库管理员需要修改系统变量的默认值，以便修改当前会话或者 MySQL 服务实例的属性、特征。具体方法：

  方式 1：修改 MySQL`配置文件`，继而修改 MySQL 系统变量的值（该方法需要重启 MySQL 服务）。

  方式 2：在 MySQL 服务运行期间，使用“set”命令重新设置系统变量的值。

  > \# 为某个系统变量赋值
  > \# 方式 1：
  > SET @@global.变量名=变量值;
  >
  > \# 方式 2：
  > SET GLOBAL 变量名=变量值;
  >
  > \# 为某个会话变量赋值
  > \# 方式 1：
  > SET @@session.变量名=变量值;
  > \# 方式 2：
  > SET SESSION 变量名=变量值;

  举例：

  ```sql
  SELECT @@global.autocommit;
  SET GLOBAL autocommit=0;
  ```

  ```sql
  SELECT @@session.tx_isolation;
  SET @@session.tx_isolation='read-uncommitted';
  ```

  ```sql
  SET GLOBAL max_connections = 1000;
  SELECT @@global.max_connections;
  ```

### 1.2 用户变量

#### 1.2.1 用户变量分类

用户变量是用户自己定义的，作为 MySQL 编码规范，MySQL 中的用户变量以`一个“@”`开头。根据作用范围不同，又分为`会话用户变量`和`局部变量`。

- 会话用户变量：作用域和会话变量一样，只对`当前连接`会话有效。

- 局部变量：只在 BEGIN 和 END 语句块中有效。局部变量只能在`存储过程和函数`中使用。

#### 1.2.2 会话用户变量

- 变量的定义

  > \# 方式 1：“=”或“:=”
  > SET @用户变量 = 值;
  > SET @用户变量 := 值;
  >
  > \# 方式 2：“:=” 或 INTO 关键字
  > SELECT @用户变量 := 表达式 [FROM 等子句];
  > SELECT 表达式 INTO @用户变量 [FROM 等子句];

- 查看用户变量的值 （查看、比较、运算等）

  > SELECT @用户变量

- 举例

  ```sql
  SET @a = 1;

  SELECT @a;
  ```

  ```sql
  SELECT @num := COUNT(*) FROM employees;

  SELECT @num;
  ```

  ```sql
  SELECT AVG(salary) INTO @avgsalary FROM employees;

  SELECT @avgsalary;
  ```

  ```sql
  # 查看某个未声明的变量时，将得到 NULL 值
  SELECT @big;
  ```

#### 1.2.3 局部变量

定义：可以使用`DECLARE`语句定义一个局部变量。

作用域：仅仅在定义它的 BEGIN ... END 中有效。

位置：只能放在 BEGIN ... END 中，而且只能放在第一句。

> BEGIN
> &nbsp; \# 声明局部变量
> &nbsp; DECLARE 变量名 1 变量数据类型 [DEFAULT 变量默认值];
> &nbsp; DECLARE 变量名 2,变量名 3,... 变量数据类型 [DEFAULT 变量默认值];
>
> &nbsp; \# 为局部变量赋值
> &nbsp; SET 变量名 1 = 值;
> &nbsp; SELECT 值 INTO 变量名 2 [FROM 子句];
>
> &nbsp; \# 查看局部变量的值
> &nbsp; SELECT 变量 1,变量 2,变量 3;
> END

**1.定义变量**

> \# 如果没有 DEFAULT 子句，初始值为 NULL
> DECLARE 变量名 类型 [default 值];

举例：

```sql
DECLARE　myparam　INT　DEFAULT 100;
```

**2.变量赋值**

方式 1：一般用于赋简单的值

> SET 变量名=值;
> SET 变量名:=值;

方式 2：一般用于赋表中的字段值

> SELECT 字段名或表达式 INTO 变量名 FROM 表;

**3.使用变量**（查看、比较、运算等）

> SELECT 局部变量名;

举例 1：声明局部变量，并分别赋值为 employees 表中 employee_id 为 102 的 last_name 和 salary。

```sql
DELIMITER //

CREATE PROCEDURE set_value()
BEGIN
  DECLARE emp_name VARCHAR(25);
  DECLARE sal DOUBLE(10,2);

  SELECT last_name,salary INTO emp_name,sal
  FROM employees
  WHERE employee_id = 102;

  SELECT emp_name,sal;
END //

DELIMITER ;
```

举例 2：声明两个变量，求和并打印 （分别使用会话用户变量、局部变量的方式实现）。

```sql
# 方式1：使用用户变量
SET @m=1;
SET @n=1;
SET @sum=@m+@n;

SELECT @sum;
```

```sql
# 方式2：使用局部变量
DELIMITER //

CREATE PROCEDURE add_value()
BEGIN
  # 局部变量
  DECLARE m INT DEFAULT 1;
  DECLARE n INT DEFAULT 3;
  DECLARE SUM INT;

  SET SUM = m+n;
  SELECT SUM;
END //

DELIMITER ;
```

举例 3：创建存储过程“different_salary”查询某员工和他领导的薪资差距，并用 IN 参数 emp_id 接收员工 id，用 OUT 参数 dif_salary 输出薪资差距结果。

```sql
# 声明
DELIMITER //

CREATE PROCEDURE different_salary(IN emp_id INT,OUT dif_salary DOUBLE)
BEGIN
  # 声明局部变量
  DECLARE emp_sal,mgr_sal DOUBLE DEFAULT 0.0;
  DECLARE mgr_id INT;

  SELECT salary INTO emp_sal FROM employees WHERE employee_id = emp_id;
  SELECT manager_id INTO mgr_id FROM employees WHERE employee_id = emp_id;
  SELECT salary INTO mgr_sal FROM employees WHERE employee_id = mgr_id;
  SET dif_salary = mgr_sal - emp_sal;

END //

DELIMITER ;

# 调用
SET @emp_id = 102;
CALL different_salary(@emp_id,@diff_sal);


# 查看
SELECT @diff_sal;
```

#### 1.2.4 对比会话用户变量与局部变量

|              | 作用域                | 定义位置             | 语法                       |     |
| ------------ | --------------------- | -------------------- | -------------------------- | --- |
| 会话用户变量 | 当前会话              | 会话的任何地方       | 加@符号，不用指定类型。    |     |
| 局部变量     | 定义它的 BEGIN END 中 | BEGIN END 的第一句话 | 一般不用加@,需要指定类型。 |     |

## 2. 定义条件与处理程序

`定义条件`是事先定义程序执行过程中可能遇到的问题，`处理程序`定义了在遇到问题时应当采取的处理方式，并且保证存储过程或函数在遇到警告或错误时能继续执行。这样可以增强存储程序处理问题的能力，避免程序异常停止运行。

说明：定义条件和处理程序在存储过程、存储函数中都是支持的。

### 2.1 案例分析

**案例分析：** 创建一个名称为“UpdateDataNoCondition”的存储过程。代码如下：

```sql
DELIMITER //

CREATE PROCEDURE UpdateDataNoCondition()
  BEGIN
    SET @x = 1;
    UPDATE employees SET email = NULL WHERE last_name = 'Abel';
    SET @x = 2;
    UPDATE employees SET email = 'aabbel' WHERE last_name = 'Abel';
    SET @x = 3;
  END //

DELIMITER ;
```

调用存储过程：

```sh
mysql> CALL UpdateDataNoCondition();
ERROR 1048 (23000): Column 'email' cannot be null

mysql> SELECT @x;
+------+
| @x   |
+------+
|   1  |
+------+
1 row in set (0.00 sec)

```

可以看到，此时@x 变量的值为 1。结合创建存储过程的 SQL 语句代码可以得出：在存储过程中未定义条件和处理程序，且当存储过程中执行的 SQL 语句报错时，MySQL 数据库会抛出错误，并退出当前 SQL 逻辑，不再向下继续执行。

### 2.2 定义条件

定义条件就是给 MySQL 中的错误码命名，这有助于存储的程序代码更清晰。它将一个`错误名字`和`指定的错误条件`关联起来。这个名字可以随后被用在定义处理程序的`DECLARE HANDLER`语句中。

定义条件使用 DECLARE 语句，语法格式如下：

> DECLARE 错误名称 CONDITION FOR 错误码（或错误条件）

错误码的说明：

- `MySQL_error_code`和`sqlstate_value`都可以表示 MySQL 的错误。

  - MySQL_error_code 是数值类型错误代码。

  - sqlstate_value 是长度为 5 的字符串类型错误代码。

- 例如，在 ERROR 1418 (HY000)中，1418 是 MySQL_error_code，'HY000'是 sqlstate_value。

- 例如，在 ERROR 1142（42000）中，1142 是 MySQL_error_code，'42000'是 sqlstate_value。

**举例 1：** 定义“Field_Not_Be_NULL”错误名与 MySQL 中违反非空约束的错误类型是“ERROR 1048 (23000)”对应。

```sql
# 使用 MySQL_error_code
DECLARE Field_Not_Be_NULL CONDITION FOR 1048;

# 使用 sqlstate_value
DECLARE Field_Not_Be_NULL CONDITION FOR SQLSTATE '23000';
```

**举例 2：** 定义"ERROR 1148(42000)"错误，名称为 command_not_allowed。

```sql
# 使用 MySQL_error_code
DECLARE command_not_allowed CONDITION FOR 1148;

# 使用 sqlstate_value
DECLARE command_not_allowed CONDITION FOR SQLSTATE '42000';
```

### 2.3 定义处理程序

可以为 SQL 执行过程中发生的某种类型的错误定义特殊的处理程序。定义处理程序时，使用 DECLARE 语句的语法如下：

> DECLARE 处理方式 HANDLER FOR 错误类型 处理语句

- **处理方式**：处理方式有 3 个取值：CONTINUE、EXIT、UNDO。

  - `CONTINUE`：表示遇到错误不处理，继续执行；

  - `EXIT`：表示遇到错误马上退出；

  - `UNDO`：表示遇到错误后撤回之前的操作。MySQL 中暂时不支持这样的操作。

- **错误类型**（即条件）可以有如下取值：

  - `SQLSTATE '字符串错误码'`：表示长度为 5 的 sqlstate_value 类型的错误代码；

  - `MySQL_error_code`：匹配数值类型错误代码；

  - `错误名称`：表示 DECLARE ... CONDITION 定义的错误条件名称；

  - `SQLWARNING`：匹配所有以 01 开头的 SQLSTATE 错误代码；

  - `NOT FOUND`：匹配所有以 02 开头的 SQLSTATE 错误代码；

  - `SQLEXCEPTION`：匹配所有没有被 SQLWARNING 或 NOT FOUND 捕获的 SQLSTATE 错误代码。

- **处理语句**：如果出现上述条件之一，则采用对应的处理方式，并执行指定的处理语句。语句可以是像“`SET 变量 = 值`”这样的简单语句，也可以是使用`BEGIN ... END`编写的复合语句。

定义处理程序的几种方式，代码如下：

```sql
# 方法1：捕获 sqlstate_value
DECLARE CONTINUE HANDLER FOR SQLSTATE '42S02' SET @info = 'NO_SUCH_TABLE';

# 方法2：捕获 mysql_error_value
DECLARE CONTINUE HANDLER FOR 1146 SET @info = 'NO_SUCH_TABLE';

# 方法3：先定义条件，再调用
DECLARE no_such_table CONDITION FOR 1146;
DECLARE CONTINUE HANDLER FOR NO_SUCH_TABLE SET @info = 'NO_SUCH_TABLE';

# 方法4：使用 SQLWARNING
DECLARE EXIT HANDLER FOR SQLWARNING SET @info = 'ERROR';

# 方法5：使用 NOT FOUND
DECLARE EXIT HANDLER FOR NOT FOUND SET @info = 'NO_SUCH_TABLE';

# 方法6：使用 SQLEXCEPTION
DECLARE EXIT HANDLER FOR SQLEXCEPTION SET @info = 'ERROR';
```

### 2.4 案例解决

在存储过程中，定义处理程序，捕获 sqlstate_value 值，当遇到 MySQL_error_code 值为 1048 时，执行 CONTINUE 操作，并且将@proc_value 的值设置为-1。

```sql
DELIMITER //

CREATE PROCEDURE UpdateDataNoCondition()
  BEGIN
    # 定义处理程序
    DECLARE CONTINUE HANDLER FOR 1048 SET @proc_value = -1;

    SET @x = 1;
    UPDATE employees SET email = NULL WHERE last_name = 'Abel';
    SET @x = 2;
    UPDATE employees SET email = 'aabbel' WHERE last_name = 'Abel';
    SET @x = 3;
  END //

DELIMITER ;
```

调用过程：

```sh
mysql> CALL UpdateDataWithCondition();
Query OK, 0 rows affected (0.01 sec)

mysql> SELECT @x,@proc_value;
+------+-------------+
| @x   | @proc_value |
+------+-------------+
|    3 |         -1  |
+------+-------------+
1 row in set (0.00 sec)

```

**举例：**

创建一个名称为“InsertDataWithCondition”的存储过程，代码如下。

在存储过程中，定义处理程序，捕获 sqlstate_value 值，当遇到 sqlstate_value 值为 23000 时，执行 EXIT 操作，并且将@proc_value 的值设置为-1。

```sql
# 准备工作
CREATE TABLE departments
AS
SELECT * FROM atguigudb.`departments`;

ALTER TABLE departments
ADD CONSTRAINT uk_dept_name UNIQUE(department_id);
```

```sql
DELIMITER //

CREATE PROCEDURE InsertDataWithCondition()
  BEGIN
    DECLARE duplicate_entry CONDITION FOR SQLSTATE '23000' ;
    DECLARE EXIT HANDLER FOR duplicate_entry SET @proc_value = -1;

    SET @x = 1;
    INSERT INTO departments(department_name) VALUES('测试');
    SET @x = 2;
    INSERT INTO departments(department_name) VALUES('测试');
    SET @x = 3;
  END //

DELIMITER ;
```

调用存储过程：

```sh
mysql> CALL InsertDataWithCondition();
Query OK, 0 rows affected (0.01 sec)

mysql> SELECT @x,@proc_value;
+------+-------------+
| @x   | @proc_value |
+------+-------------+
|    2 |       	 -1  |
+------+-------------+
1 row in set (0.00 sec)

```

## 3. 流程控制

解决复杂问题不可能通过一个 SQL 语句完成，我们需要执行多个 SQL 操作。流程控制语句的作用就是控制存储过程中 SQL 语句的执行顺序，是我们完成复杂操作必不可少的一部分。只要是执行的程序，流程就分为三大类：

- `顺序结构`：程序从上往下依次执行。

- `分支结构`：程序按条件进行选择执行，从两条或多条路径中选择一条执行。

- `循环结构`：程序满足一定条件下，重复执行一组语句。

针对于 MySQL 的流程控制语句主要有 3 类。注意：只能用于存储程序。

- `条件判断语句`：IF 语句和 CASE 语句。

- `循环语句`：LOOP、WHILE 和 REPEAT 语句。

- `跳转语句`：ITERATE 和 LEAVE 语句。

### 3.1 分支结构之 IF

- IF 语句的语法结构是：

  > IF 表达式 1 THEN 操作 1
  > [ELSEIF 表达式 2 THEN 操作 2]……
  > [ELSE 操作 N]
  > END IF

  根据表达式的结果为 TRUE 或 FALSE 执行相应的语句。这里“[]”中的内容是可选的。

- 特点：① 不同的表达式对应不同的操作 ② 使用在 begin end 中。

- **举例 1：**

  ```sql
  IF val IS NULL
    THEN SELECT 'val is null';
  ELSE SELECT 'val is not null';

  END IF;
  ```

- **举例 2：** 声明存储过程“update_salary_by_eid1”，定义 IN 参数 emp_id，输入员工编号。判断该员工薪资如果低于 8000 元并且入职时间超过 5 年，就涨薪 500 元；否则就不变。

  ```sql
  DELIMITER //

  CREATE PROCEDURE update_salary_by_eid1(IN emp_id INT)
  BEGIN
    DECLARE emp_salary DOUBLE;
    DECLARE hire_year DOUBLE;

    SELECT salary INTO emp_salary FROM employees WHERE employee_id = emp_id;

    SELECT DATEDIFF(CURDATE(),hire_date)/365 INTO hire_year
    FROM employees WHERE employee_id = emp_id;

    IF emp_salary < 8000 AND hire_year > 5
    THEN UPDATE employees SET salary = salary + 500 WHERE employee_id = emp_id;
    END IF;
  END //


  DELIMITER ;
  ```

- **举例 3：** 声明存储过程“update_salary_by_eid2”，定义 IN 参数 emp_id，输入员工编号。判断该员工薪资如果低于 9000 元并且入职时间超过 5 年，就涨薪 500 元；否则就涨薪 100 元。

  ```sql
  DELIMITER //

  CREATE PROCEDURE update_salary_by_eid2(IN emp_id INT)
  BEGIN
    DECLARE emp_salary DOUBLE;
    DECLARE hire_year DOUBLE;

    SELECT salary INTO emp_salary FROM employees WHERE employee_id = emp_id;

    SELECT DATEDIFF(CURDATE(),hire_date)/365 INTO hire_year
    FROM employees WHERE employee_id = emp_id;

    IF emp_salary < 8000 AND hire_year > 5
      THEN UPDATE employees SET salary = salary + 500 WHERE employee_id = emp_id;
    ELSE
      UPDATE employees SET salary = salary + 100 WHERE employee_id = emp_id;
    END IF;
  END //


  DELIMITER ;
  ```

- **举例 4：** 声明存储过程“update_salary_by_eid3”，定义 IN 参数 emp_id，输入员工编号。判断该员工薪资如果低于 9000 元，就更新薪资为 9000 元；薪资如果大于等于 9000 元且低于 10000 的，但是奖金比例为 NULL 的，就更新奖金比例为 0.01；其他的涨薪 100 元。

  ```sql
  DELIMITER //

  CREATE PROCEDURE update_salary_by_eid3(IN emp_id INT)
  BEGIN
    DECLARE emp_salary DOUBLE;
    DECLARE bonus DECIMAL(3,2);

    SELECT salary INTO emp_salary FROM employees WHERE employee_id = emp_id;
    SELECT commission_pct INTO bonus FROM employees WHERE employee_id = emp_id;

    IF emp_salary < 9000
      THEN UPDATE employees SET salary = 9000 WHERE employee_id = emp_id;
    ELSEIF emp_salary < 10000 AND bonus IS NULL
      THEN UPDATE employees SET commission_pct = 0.01 WHERE employee_id = emp_id;
    ELSE
      UPDATE employees SET salary = salary + 100 WHERE employee_id = emp_id;
    END IF;
  END //

  DELIMITER ;
  ```

### 3.2 分支结构之 CASE

CASE 语句的语法结构 1：

> \# 情况一：类似于 switch
> CASE 表达式
> WHEN 值 1 THEN 结果 1 或语句 1(如果是语句，需要加分号)
> WHEN 值 2 THEN 结果 2 或语句 2(如果是语句，需要加分号)
> ...
> ELSE 结果 n 或语句 n(如果是语句，需要加分号)
> END [case]（如果是放在 begin end 中需要加上 case，如果放在 select 后面不需要）

CASE 语句的语法结构 2：

> \# 情况二：类似于多重 if
> CASE
> WHEN 条件 1 THEN 结果 1 或语句 1(如果是语句，需要加分号)
> WHEN 条件 2 THEN 结果 2 或语句 2(如果是语句，需要加分号)
> ...
> ELSE 结果 n 或语句 n(如果是语句，需要加分号)
> END [case]（如果是放在 begin end 中需要加上 case，如果放在 select 后面不需要）

- **举例 1：**

  使用 CASE 流程控制语句的第 1 种格式，判断 val 值等于 1、等于 2，或者两者都不等。

  ```sql
  CASE val
  　　　WHEN 1 THEN SELECT 'val is 1';
  　　　WHEN 2 THEN SELECT 'val is 2';
  　　　ELSE SELECT 'val is not 1 or 2';
  END CASE;
  ```

- **举例 2：**

  使用 CASE 流程控制语句的第 2 种格式，判断 val 是否为空、小于 0、大于 0 或者等于 0。

  ```sql
  CASE
    WHEN val IS NULL THEN SELECT 'val is null';
    WHEN val < 0 THEN SELECT 'val is less than 0';
    WHEN val > 0 THEN SELECT 'val is greater than 0';
    ELSE SELECT 'val is 0';
  END CASE;
  ```

- **举例 3：** 声明存储过程“update_salary_by_eid4”，定义 IN 参数 emp_id，输入员工编号。判断该员工薪资如果低于 9000 元，就更新薪资为 9000 元；薪资大于等于 9000 元且低于 10000 的，但是奖金比例为 NULL 的，就更新奖金比例为 0.01；其他的涨薪 100 元。

  ```sql
  DELIMITER //

  CREATE PROCEDURE update_salary_by_eid4(IN emp_id INT)
  BEGIN
    DECLARE emp_sal DOUBLE;
    DECLARE bonus DECIMAL(3,2);

    SELECT salary INTO emp_sal FROM employees WHERE employee_id = emp_id;
    SELECT commission_pct INTO bonus FROM employees WHERE employee_id = emp_id;

    CASE
    WHEN emp_sal<9000
      THEN UPDATE employees SET salary=9000 WHERE employee_id = emp_id;
    WHEN emp_sal<10000 AND bonus IS NULL
      THEN UPDATE employees SET commission_pct=0.01 WHERE employee_id = emp_id;
    ELSE
      UPDATE employees SET salary=salary+100 WHERE employee_id = emp_id;
    END CASE;
  END //

  DELIMITER ;
  ```

- 举例 4：声明存储过程 update_salary_by_eid5，定义 IN 参数 emp_id，输入员工编号。判断该员工的入职年限，如果是 0 年，薪资涨 50；如果是 1 年，薪资涨 100；如果是 2 年，薪资涨 200；如果是 3 年，薪资涨 300；如果是 4 年，薪资涨 400；其他的涨薪 500。

  ```sql
  DELIMITER //

  CREATE PROCEDURE update_salary_by_eid5(IN emp_id INT)
  BEGIN
    DECLARE emp_sal DOUBLE;
    DECLARE hire_year DOUBLE;

    SELECT salary INTO emp_sal FROM employees WHERE employee_id = emp_id;

    SELECT ROUND(DATEDIFF(CURDATE(),hire_date)/365) INTO hire_year FROM employees WHERE employee_id = emp_id;

    CASE hire_year
      WHEN 0 THEN UPDATE employees SET salary=salary+50 WHERE employee_id = emp_id;
      WHEN 1 THEN UPDATE employees SET salary=salary+100 WHERE employee_id = emp_id;
      WHEN 2 THEN UPDATE employees SET salary=salary+200 WHERE employee_id = emp_id;
      WHEN 3 THEN UPDATE employees SET salary=salary+300 WHERE employee_id = emp_id;
      WHEN 4 THEN UPDATE employees SET salary=salary+400 WHERE employee_id = emp_id;
      ELSE UPDATE employees SET salary=salary+500 WHERE employee_id = emp_id;
    END CASE;
  END //

  DELIMITER ;
  ```

### 3.3 循环结构之 LOOP

LOOP 循环语句用来重复执行某些语句。LOOP 内的语句一直重复执行直到循环被退出（使用 LEAVE 子句），跳出循环过程。

LOOP 语句的基本格式如下：

> [loop_label:] LOOP
> &nbsp; 循环执行的语句
> END LOOP [loop_label]

其中，loop_label 表示 LOOP 语句的标注名称，该参数可以省略。

**举例 1：**

使用 LOOP 语句进行循环操作，id 值小于 10 时将重复执行循环过程。

```sql
DECLARE id INT DEFAULT 0;
add_loop:LOOP
  SET id = id +1;
  IF id >= 10 THEN LEAVE add_loop;
  END IF;

END LOOP add_loop;
```

**举例 2：** 当市场环境变好时，公司为了奖励大家，决定给大家涨工资。声明存储过程“update_salary_loop()”，声明 OUT 参数 num，输出循环次数。存储过程中实现循环给大家涨薪，薪资涨为原来的 1.1 倍。直到全公司的平均薪资达到 12000 结束。并统计循环次数。

```sql
DELIMITER //

CREATE PROCEDURE update_salary_loop(OUT num INT)
BEGIN
  DECLARE avg_salary DOUBLE;
  DECLARE loop_count INT DEFAULT 0;

  SELECT AVG(salary) INTO avg_salary FROM employees;

  label_loop:LOOP
    IF avg_salary >= 12000 THEN LEAVE label_loop;
    END IF;

    UPDATE employees SET salary = salary * 1.1;
    SET loop_count = loop_count + 1;
    SELECT AVG(salary) INTO avg_salary FROM employees;
  END LOOP label_loop;

  SET num = loop_count;

END //

DELIMITER ;
```

### 3.4 循环结构之 WHILE

WHILE 语句创建一个带条件判断的循环过程。WHILE 在执行语句执行时，先对指定的表达式进行判断，如果为真，就执行循环内的语句，否则退出循环。WHILE 语句的基本格式如下：

> [while_label:] WHILE 循环条件 DO
> &nbsp; 循环体
> END WHILE [while_label];

while_label 为 WHILE 语句的标注名称；如果循环条件结果为真，WHILE 语句内的语句或语句群被执行，直至循环条件为假，退出循环。

**举例 1：**

WHILE 语句示例，i 值小于 10 时，将重复执行循环过程，代码如下：

```sql
DELIMITER //

CREATE PROCEDURE test_while()
BEGIN
  DECLARE i INT DEFAULT 0;

  WHILE i < 10 DO
    SET i = i + 1;
  END WHILE;

  SELECT i;
END //

DELIMITER ;
#调用
CALL test_while();
```

**举例 2：** 市场环境不好时，公司为了渡过难关，决定暂时降低大家的薪资。声明存储过程“update_salary_while()”，声明 OUT 参数 num，输出循环次数。存储过程中实现循环给大家降薪，薪资降为原来的 90%。直到全公司的平均薪资达到 5000 结束。并统计循环次数。

```sql
DELIMITER //

CREATE PROCEDURE update_salary_while(OUT num INT)
BEGIN
  DECLARE avg_sal DOUBLE ;
  DECLARE while_count INT DEFAULT 0;

  SELECT AVG(salary) INTO avg_sal FROM employees;

  WHILE avg_sal > 5000 DO
    UPDATE employees SET salary = salary * 0.9;

    SET while_count = while_count + 1;

    SELECT AVG(salary) INTO avg_sal FROM employees;
  END WHILE;

  SET num = while_count;

END //

DELIMITER ;
```

### 3.5 循环结构之 REPEAT

REPEAT 语句创建一个带条件判断的循环过程。与 WHILE 循环不同的是，REPEAT 循环首先会执行一次循环，然后在 UNTIL 中进行表达式的判断，如果满足条件就退出，即 END REPEAT；如果条件不满足，则会就继续执行循环，直到满足退出条件为止。

REPEAT 语句的基本格式如下：

> [repeat_label:] REPEAT
> &nbsp; 循环体的语句
> UNTIL 结束循环的条件表达式
> END REPEAT [repeat_label]

repeat_label 为 REPEAT 语句的标注名称，该参数可以省略；REPEAT 语句内的语句或语句群被重复，直至 expr_condition 为真。

**举例 1：**

```sql
DELIMITER //

CREATE PROCEDURE test_repeat()
BEGIN
  DECLARE i INT DEFAULT 0;

  REPEAT
    SET i = i + 1;
  UNTIL i >= 10
  END REPEAT;

  SELECT i;
END //

DELIMITER ;
```

**举例 2：** 当市场环境变好时，公司为了奖励大家，决定给大家涨工资。声明存储过程“update_salary_repeat()”，声明 OUT 参数 num，输出循环次数。存储过程中实现循环给大家涨薪，薪资涨为原来的 1.15 倍。直到全公司的平均薪资达到 13000 结束。并统计循环次数。

```sql
DELIMITER //

CREATE PROCEDURE update_salary_repeat(OUT num INT)
BEGIN
  DECLARE avg_sal DOUBLE ;
  DECLARE repeat_count INT DEFAULT 0;

  SELECT AVG(salary) INTO avg_sal FROM employees;

  REPEAT
    UPDATE employees SET salary = salary * 1.15;

    SET repeat_count = repeat_count + 1;

    SELECT AVG(salary) INTO avg_sal FROM employees;
  UNTIL avg_sal >= 13000
  END REPEAT;

  SET num = repeat_count;

END //

DELIMITER ;
```

**对比三种循环结构：**

1、这三种循环都可以省略名称，但如果循环中添加了循环控制语句（LEAVE 或 ITERATE）则必须添加名称。

2、
LOOP：一般用于实现简单的"死"循环。
WHILE：先判断后执行。
REPEAT：先执行后判断，无条件至少执行一次。

### 3.6 跳转语句之 LEAVE 语句

LEAVE 语句：可以用在循环语句内，或者以 BEGIN 和 END 包裹起来的程序体内，表示跳出循环或者跳出程序体的操作。如果你有面向过程的编程语言的使用经验，你可以把 LEAVE 理解为 break。

基本格式如下：

> LEAVE 标记名

其中，label 参数表示循环的标志。LEAVE 和 BEGIN ... END 或循环一起被使用。

**举例 1：** 创建存储过程 “leave_begin()”，声明 INT 类型的 IN 参数 num。给 BEGIN...END 加标记名，并在 BEGIN...END 中使用 IF 语句判断 num 参数的值。

- 如果 num<=0，则使用 LEAVE 语句退出 BEGIN...END；

- 如果 num=1，则查询“employees”表的平均薪资；

- 如果 num=2，则查询“employees”表的最低薪资；

- 如果 num>2，则查询“employees”表的最高薪资。

IF 语句结束后查询“employees”表的总人数。

```sql
DELIMITER //

CREATE PROCEDURE leave_begin(IN num INT)

  begin_label: BEGIN
    IF num<=0
      THEN LEAVE begin_label;
    ELSEIF num=1
      THEN SELECT AVG(salary) FROM employees;
    ELSEIF num=2
      THEN SELECT MIN(salary) FROM employees;
    ELSE
      SELECT MAX(salary) FROM employees;
    END IF;

    SELECT COUNT(*) FROM employees;
  END //


DELIMITER ;
```

**举例 2：**

当市场环境不好时，公司为了渡过难关，决定暂时降低大家的薪资。声明存储过程“leave_while()”，声明 OUT 参数 num，输出循环次数，存储过程中使用 WHILE 循环给大家降低薪资为原来薪资的 90%，直到全公司的平均薪资小于等于 10000，并统计循环次数。

```sql
DELIMITER //
CREATE PROCEDURE leave_while(OUT num INT)

BEGIN
  # 记录平均工资
  DECLARE avg_sal DOUBLE;

  # 记录循环次数
  DECLARE while_count INT DEFAULT 0;

  # ① 初始化条件
  SELECT AVG(salary) INTO avg_sal FROM employees;

  # ② 循环条件
  while_label:WHILE TRUE DO

    # ③ 循环体
    IF avg_sal <= 10000 THEN
      LEAVE while_label;
    END IF;

    UPDATE employees SET salary  = salary * 0.9;
    SET while_count = while_count + 1;

    # ④ 迭代条件
    SELECT AVG(salary) INTO avg_sal FROM employees;

  END WHILE;

  # 赋值
  SET num = while_count;

END //

DELIMITER ;
```

### 3.7 跳转语句之 ITERATE 语句

ITERATE 语句：只能用在循环语句（LOOP、REPEAT 和 WHILE 语句）内，表示重新开始循环，将执行顺序转到语句段开头处。如果你有面向过程的编程语言的使用经验，你可以把 ITERATE 理解为 continue，意思为“再次循环”。

语句基本格式如下：

> ITERATE label

label 参数表示循环的标志。ITERATE 语句必须跟在循环标志前面。

**举例：** 定义局部变量 num，初始值为 0。循环结构中执行 num + 1 操作。

- 如果 num < 10，则继续执行循环；

- 如果 num > 15，则退出循环结构；

```sql
DELIMITER //

CREATE PROCEDURE test_iterate()

BEGIN
  DECLARE num INT DEFAULT 0;

  my_loop:LOOP
    SET num = num + 1;

    IF num < 10
      THEN ITERATE my_loop;
    ELSEIF num > 15
      THEN LEAVE my_loop;
    END IF;

    SELECT '在夜空所有星星熄灭的时候，所有梦想、所有溪流，都能汇入同一片大海中，那时我们终会相见。';

  END LOOP my_loop;

END //

DELIMITER ;
```

## 4. 游标

### 4.1 什么是游标（或光标）

虽然我们也可以通过筛选条件 WHERE 和 HAVING，或者是限定返回记录的关键字 LIMIT 返回一条记录，但是，却无法在结果集中像指针一样，向前定位一条记录、向后定位一条记录，或者是`随意定位到某一条记录`，并对记录的数据进行处理。

这个时候，就可以用到游标。游标，提供了一种灵活的操作方式，让我们能够对结果集中的每一条记录进行定位，并对指向的记录中的数据进行操作的数据结构。**游标让 SQL 这种面向集合的语言有了面向过程开发的能力。**

在 SQL 中，游标是一种临时的数据库对象，可以指向存储在数据库表中的数据行指针。这里游标`充当了指针的作用`，我们可以通过操作游标来对数据行进行操作。

MySQL 中游标可以在存储过程和函数中使用。

比如，我们查询了 employees 数据表中工资高于 15000 的员工都有哪些：

```sql
SELECT employee_id,last_name,salary FROM employees
WHERE salary > 15000;
```

![什么是游标（或光标）](https://img-blog.csdnimg.cn/468e9122256e4f7283b23aa3a82b4c9f.png)

这里我们就可以通过游标来操作数据行，如图所示此时游标所在的行是“108”的记录，我们也可以在结果集上滚动游标，指向结果集中的任意一行。

### 4.2 使用游标步骤

游标必须在声明处理程序之前被声明，并且变量和条件还必须在声明游标或处理程序之前被声明。

如果我们想要使用游标，一般需要经历四个步骤。不同的 DBMS 中，使用游标的语法可能略有不同。

**第一步，声明游标**

在 MySQL 中，使用 DECLARE 关键字来声明游标，其语法的基本形式如下：

```sql
DECLARE cursor_name CURSOR FOR select_statement;
```

这个语法适用于 MySQL，SQL Server，DB2 和 MariaDB。如果是用 Oracle 或者 PostgreSQL，需要写成：

```sql
DECLARE cursor_name CURSOR IS select_statement;
```

要使用 SELECT 语句来获取数据结果集，而此时还没有开始遍历数据，这里 select_statement 代表的是 SELECT 语句，返回一个用于创建游标的结果集。

比如：

```sql
DECLARE cur_emp CURSOR FOR
SELECT employee_id,salary FROM employees;
```

```sql
DECLARE cursor_fruit CURSOR FOR
SELECT f_name, f_price FROM fruits ;
```

**第二步，打开游标**

打开游标的语法如下：

```sql
OPEN cursor_name
```

当我们定义好游标之后，如果想要使用游标，必须先打开游标。打开游标的时候 SELECT 语句的查询结果集就会送到游标工作区，为后面游标的`逐条读取`结果集中的记录做准备。

```sql
OPEN　cur_emp ;
```

**第三步，使用游标（从游标中取得数据）**

语法如下：

> FETCH cursor_name INTO var_name [, var_name] ...

这句的作用是使用 cursor_name 这个游标来读取当前行，并且将数据保存到 var_name 这个变量中，游标指针指到下一行。如果游标读取的数据行有多个列名，则在 INTO 关键字后面赋值给多个变量名即可。

注意：var_name 必须在声明游标之前就定义好。

```sql
FETCH　cur_emp INTO emp_id, emp_sal ;
```

注意：**游标的查询结果集中的字段数，必须跟 INTO 后面的变量数一致**，否则，在存储过程执行的时候，MySQL 会提示错误。

**第四步，关闭游标**

```sql
CLOSE cursor_name
```

有 OPEN 就会有 CLOSE，也就是打开和关闭游标。当我们使用完游标后需要关闭掉该游标。因为游标会`占用系统资源`，如果不及时关闭，**游标会一直保持到存储过程结束**，影响系统运行的效率。而关闭游标的操作，会释放游标占用的系统资源。

关闭游标之后，我们就不能再检索查询结果中的数据行，如果需要检索只能再次打开游标。

```sql
CLOSE　cur_emp;
```

### 4.3 举例

创建存储过程“get_count_by_limit_total_salary()”，声明 IN 参数 limit_total_salary，DOUBLE 类型；声明 OUT 参数 total_count，INT 类型。函数的功能可以实现累加薪资最高的几个员工的薪资值，直到薪资总和达到 limit_total_salary 参数的值，返回累加的人数给 total_count。

```sql
DELIMITER //

CREATE PROCEDURE get_count_by_limit_total_salary(IN limit_total_salary DOUBLE,OUT total_count INT)

BEGIN
  # 记录累加的总工资
  DECLARE sum_salary DOUBLE DEFAULT 0;

  # 记录某一个工资值
  DECLARE cursor_salary DOUBLE DEFAULT 0;

  # 记录循环个数
  DECLARE emp_count INT DEFAULT 0;

  # 定义游标
  DECLARE emp_cursor CURSOR FOR SELECT salary FROM employees ORDER BY salary DESC;

  # 打开游标
  OPEN emp_cursor;

  REPEAT
    # 使用游标（从游标中获取数据）
    FETCH emp_cursor INTO cursor_salary;

    SET sum_salary = sum_salary + cursor_salary;
    SET emp_count = emp_count + 1;

    UNTIL sum_salary >= limit_total_salary
  END REPEAT;

  SET total_count = emp_count;

  # 关闭游标
  CLOSE emp_cursor;

END //

DELIMITER ;
```

### 4.5 小结

游标是 MySQL 的一个重要的功能，为`逐条读取`结果集中的数据，提供了完美的解决方案。跟在应用层面实现相同的功能相比，游标可以在存储程序中使用，效率高，程序也更加简洁。

但同时也会带来一些性能问题，比如在使用游标的过程中，会对数据行进行`加锁`，这样在业务并发量大的时候，不仅会影响业务之间的效率，还会`消耗系统资源`，造成内存不足，这是因为游标是在内存中进行的处理。

建议：养成用完之后就关闭的习惯，这样才能提高系统的整体效率。

## 5. 补充：MySQL 8.0 的新特性—全局变量的持久化

在 MySQL 数据库中，全局变量可以通过 SET GLOBAL 语句来设置。例如，设置服务器语句超时的限制，可以通过设置系统变量 max_execution_time 来实现：

```sql
SET GLOBAL MAX_EXECUTION_TIME=2000;
```

使用 SET GLOBAL 语句设置的变量值只会`临时生效`。`数据库重启`后，服务器又会从 MySQL 配置文件中读取变量的默认值。

MySQL 8.0 版本新增了`SET PERSIST`命令。例如，设置服务器的最大连接数为 1000：

```sql
SET PERSIST global max_connections = 1000;
```

MySQL 会将该命令的配置保存到数据目录下的`mysqld-auto.cnf`文件中，下次启动时会读取该文件，用其中的配置来覆盖默认的配置文件。

举例：

查看全局变量 max_connections 的值，结果如下：

```sh
mysql> show variables like '%max_connections%';
+------------------------+-------+
| Variable_name          | Value |
+------------------------+-------+
| max_connections        | 151   |
| mysqlx_max_connections | 100   |
+------------------------+-------+
2 rows in set, 1 warning (0.00 sec)
```

设置全局变量 max_connections 的值：

```sh
mysql> set persist max_connections=1000;
Query OK, 0 rows affected (0.00 sec)
```

`重启MySQL服务器`，再次查询 max_connections 的值：

```sh
mysql> show variables like '%max_connections%';
+------------------------+-------+
| Variable_name          | Value |
+------------------------+-------+
| max_connections        | 1000  |
| mysqlx_max_connections | 100   |
+------------------------+-------+
2 rows in set, 1 warning (0.00 sec)
```

# 第 17 章 触发器

在实际开发中，我们经常会遇到这样的情况：有 2 个或者多个相互关联的表，如`商品信息`和`库存信息`分别存放在 2 个不同的数据表中，我们在添加一条新商品记录的时候，为了保证数据的完整性，必须同时在库存表中添加一条库存记录。

这样一来，我们就必须把这两个关联的操作步骤写到程序里面，而且要用`事务`包裹起来，确保这两个操作成为一个`原子操作`，要么全部执行，要么全部不执行。要是遇到特殊情况，可能还需要对数据进行手动维护，这样就很`容易忘记其中的一步`，导致数据缺失。

这个时候，咱们可以使用触发器。**你可以创建一个触发器，让商品信息数据的插入操作自动触发库存数据的插入操作。** 这样一来，就不用担心因为忘记添加库存数据而导致的数据缺失了。

## 1. 触发器概述

MySQL 从`5.0.2`版本开始支持触发器。MySQL 的触发器和存储过程一样，都是嵌入到 MySQL 服务器的一段程序。

触发器是由`事件来触发`某个操作，这些事件包括`INSERT`、`UPDATE`、`DELETE`事件。所谓事件就是指用户的动作或者触发某项行为。如果定义了触发程序，当数据库执行这些语句时候，就相当于事件发生了，就会`自动`激发触发器执行相应的操作。

当对数据表中的数据执行插入、更新和删除操作，需要自动执行一些数据库逻辑时，可以使用触发器来实现。

## 2. 触发器的创建

### 2.1 创建触发器语法

创建触发器的语法结构是：

> CREATE TRIGGER 触发器名称
> {BEFORE|AFTER} {INSERT|UPDATE|DELETE} ON 表名
> FOR EACH ROW
> 触发器执行的语句块;

说明：

- `表名`：表示触发器监控的对象。

- `BEFORE|AFTER`：表示触发的时间。BEFORE 表示在事件之前触发；AFTER 表示在事件之后触发。

- `INSERT|UPDATE|DELETE`：表示触发的事件。

  - INSERT 表示插入记录时触发；

  - UPDATE 表示更新记录时触发；

  - DELETE 表示删除记录时触发。

- `触发器执行的语句块`：可以是单条 SQL 语句，也可以是由 BEGIN…END 结构组成的复合语句块。

### 2.2 代码举例

**举例 1：**

1、创建数据表：

```sql
CREATE TABLE test_trigger
(
  id INT PRIMARY KEY AUTO_INCREMENT,
  t_note VARCHAR(30)
);


CREATE TABLE test_trigger_log
(
  id INT PRIMARY KEY AUTO_INCREMENT,
  t_log VARCHAR(30)
);
```

2、创建触发器：创建名称为 before_insert 的触发器，向 test_trigger 数据表插入数据之前，向 test_trigger_log 数据表中插入 before_insert 的日志信息。

```sql
DELIMITER //

CREATE TRIGGER before_insert
BEFORE INSERT ON test_trigger
FOR EACH ROW
BEGIN
  INSERT INTO test_trigger_log (t_log)
  VALUES('before_insert');

END //

DELIMITER ;
```

3、向 test_trigger 数据表中插入数据。

```sql
INSERT INTO test_trigger (t_note) VALUES ('测试 BEFORE INSERT 触发器');
```

4、查看 test_trigger_log 数据表中的数据。

```sh
mysql> SELECT * FROM test_trigger_log;
+----+---------------+
| id | t_log         |
+----+---------------+
|  1 | before_insert |
+----+---------------+
1 row in set (0.00 sec)
```

**举例 2：**

1、创建名称为 after_insert 的触发器，向 test_trigger 数据表插入数据之后，向 test_trigger_log 数据表中插入 after_insert 的日志信息。

```sql
DELIMITER //

CREATE TRIGGER after_insert
AFTER INSERT ON test_trigger
FOR EACH ROW
BEGIN
  INSERT INTO test_trigger_log (t_log)
  VALUES('after_insert');
END //

DELIMITER ;
```

2、向 test_trigger 数据表中插入数据。

```sql
INSERT INTO test_trigger (t_note) VALUES ('测试 AFTER INSERT 触发器');
```

3、查看 test_trigger_log 数据表中的数据。

```sh
mysql> SELECT * FROM test_trigger_log;
+----+---------------+
| id | t_log         |
+----+---------------+
|  1 | before_insert |
|  2 | before_insert |
|  3 | after_insert  |
+----+---------------+
3 rows in set (0.00 sec)
```

**举例 3：** 定义触发器“salary_check_trigger”，基于员工表“employees”的 INSERT 事件，在 INSERT 之前检查将要添加的新员工薪资是否大于他领导的薪资，如果大于领导薪资，则报 sqlstate_value 为'HY000'的错误，从而使得添加失败。

```sql
DELIMITER //

CREATE TRIGGER salary_check_trigger
BEFORE INSERT ON employees FOR EACH ROW
BEGIN
  DECLARE mgrsalary DOUBLE;
  SELECT salary INTO mgrsalary FROM employees WHERE employee_id = NEW.manager_id;

  IF NEW.salary > mgrsalary THEN
    SIGNAL SQLSTATE 'HY000' SET MESSAGE_TEXT = '薪资高于领导薪资错误';
  END IF;
END //

DELIMITER ;
```

上面触发器声明过程中的 NEW 关键字代表 INSERT 添加语句的新记录。

## 3. 查看、删除触发器

### 3.1 查看触发器

查看触发器是查看数据库中已经存在的触发器的定义、状态和语法信息等。

方式 1：查看当前数据库的所有触发器的定义。

```sql
SHOW TRIGGERS\G
```

方式 2：查看当前数据库中某个触发器的定义。

> SHOW CREATE TRIGGER 触发器名

方式 3：从系统库 information_schema 的 TRIGGERS 表中查询“salary_check_trigger”触发器的信息。

```sql
SELECT * FROM information_schema.TRIGGERS;
```

### 3.2 删除触发器

触发器也是数据库对象，删除触发器也用 DROP 语句，语法格式如下：

> DROP TRIGGER IF EXISTS 触发器名称;

## 4. 触发器的优缺点

### 4.1 优点

**1、触发器可以确保数据的完整性**。

假设我们用`进货单头表`（demo.importhead）来保存进货单的总体信息，包括进货单编号、供货商编号、仓库编号、总计进货数量、总计进货金额和验收日期。

![优点](https://img-blog.csdnimg.cn/752cedd00545490f85553a098b17ce7f.png)

用`进货单明细表`（demo.importdetails）来保存进货商品的明细，包括进货单编号、商品编号、进货数量、进货价格和进货金额。

![优点](https://img-blog.csdnimg.cn/b0a1fb00f17440dcbc14db2eb0aab1aa.png)

每当我们录入、删除和修改一条进货单明细数据的时候，进货单明细表里的数据就会发生变动。这个时候，在进货单头表中的总计数量和总计金额就必须重新计算，否则，进货单头表中的总计数量和总计金额就不等于进货单明细表中数量合计和金额合计了，这就是数据不一致。

为了解决这个问题，我们就可以使用触发器，**规定每当进货单明细表有数据插入、修改和删除的操作时，自动触发 2 步操作：**

① 重新计算进货单明细表中的数量合计和金额合计；

② 用第一步中计算出来的值更新进货单头表中的合计数量与合计金额。

这样一来，进货单头表中的合计数量与合计金额的值，就始终与进货单明细表中计算出来的合计数量与合计金额的值相同，数据就是一致的，不会互相矛盾。

**2、触发器可以帮助我们记录操作日志。**

利用触发器，可以具体记录什么时间发生了什么。比如，记录修改会员储值金额的触发器，就是一个很好的例子。这对我们还原操作执行时的具体场景，更好地定位问题原因很有帮助。

**3、触发器还可以用在操作数据前，对数据进行合法性检查。**

比如，超市进货的时候，需要库管录入进货价格。但是，人为操作很容易犯错误，比如说在录入数量的时候，把条形码扫进去了；录入金额的时候，看串了行，录入的价格远超售价，导致账面上的巨亏……这些都可以通过触发器，在实际插入或者更新操作之前，对相应的数据进行检查，及时提示错误，防止错误数据进入系统。

### 4.2 缺点

**1、触发器最大的一个问题就是可读性差。**

因为触发器存储在数据库中，并且由事件驱动，这就意味着触发器有可能`不受应用层的控制`。这对系统维护是非常有挑战的。

比如，创建触发器用于修改会员储值操作。如果触发器中的操作出了问题，会导致会员储值金额更新失败。我用下面的代码演示一下：

```sh
mysql> update demo.membermaster set memberdeposit=20 where memberid = 2;
ERROR 1054 (42S22): Unknown column 'aa' in 'field list'
```

结果显示，系统提示错误，字段“aa”不存在。

这是因为，触发器中的数据插入操作多了一个字段，系统提示错误。可是，如果你不了解这个触发器，很可能会认为是更新语句本身的问题，或者是会员信息表的结构出了问题。说不定你还会给会员信息表添加一个叫“aa”的字段，试图解决这个问题，结果只能是白费力。

**2、相关数据的变更，可能会导致触发器出错。**

特别是数据表结构的变更，都可能会导致触发器出错，进而影响数据操作的正常运行。这些都会由于触发器本身的隐蔽性，影响到应用中错误原因排查的效率。

### 4.3 注意点

注意，如果在子表中定义了外键约束，并且外键指定了 ON UPDATE/DELETE CASCADE/SET NULL 子句，此时修改父表被引用的键值或删除父表被引用的记录行时，也会引起子表的修改和删除操作，此时基于子表的 UPDATE 和 DELETE 语句定义的触发器并不会被激活。

例如：基于子表员工表（t_employee）的 DELETE 语句定义了触发器 t1，而子表的部门编号（did）字段定义了外键约束引用了父表部门表（t_department）的主键列部门编号（did），并且该外键加了“ON DELETE SET NULL”子句，那么如果此时删除父表部门表（t_department）在子表员工表（t_employee）有匹配记录的部门记录时，会引起子表员工表（t_employee）匹配记录的部门编号（did）修改为 NULL，但是此时不会激活触发器 t1。只有直接对子表员工表（t_employee）执行 DELETE 语句时才会激活触发器 t1。

# 第 18 章 MySQL8 其它新特性

## 1. MySQL8 新特性概述

`MySQL从5.7版本直接跳跃发布了8.0版本`，可见这是一个令人兴奋的里程碑版本。MySQL 8 版本在功能上做了显著的改进与增强，开发者对 MySQL 的源代码进行了重构，最突出的一点是多 MySQL Optimizer 优化器进行了改进。不仅在速度上得到了改善，还为用户带来了更好的性能和更棒的体验。

### 1.1 MySQL8.0 新增特性

**1. 更简便的 NoSQL 支持**

NoSQL 泛指非关系型数据库和数据存储。随着互联网平台的规模飞速发展，传统的关系型数据库已经越来越不能满足需求。从 5.6 版本开始，MySQL 就开始支持简单的 NoSQL 存储功能。MySQL 8 对这一功能做了优化，以更灵活的方式实现 NoSQL 功能，不再依赖模式（schema）。

**2. 更好的索引**

在查询中，正确地使用索引可以提高查询的效率。MySQL 8 中新增了`隐藏索引`和`降序索引`。隐藏索引可以用来测试去掉索引对查询性能的影响。在查询中混合存在多列索引时，使用降序索引可以提高查询的性能。

**3. 更完善的 JSON 支持**

MySQL 从 5.7 开始支持原生 JSON 数据的存储，MySQL 8 对这一功能做了优化，增加了聚合函数`JSON_ARRAYAGG()`和`JSON_OBJECTAGG()`，将参数聚合为 JSON 数组或对象，新增了行内操作符 ->>，是列路径运算符 ->的增强，对 JSON 排序做了提升，并优化了 JSON 的更新操作。

**4. 安全和账户管理**

MySQL 8 中新增了`caching_sha2_password` 授权插件、角色、密码历史记录和 FIPS 模式支持，这些特性提高了数据库的安全性和性能，使数据库管理员能够更灵活地进行账户管理工作。

**5. InnoDB 的变化**

`InnoDB是MySQL默认的存储引擎`，是事务型数据库的首选引擎，支持事务安全表（ACID），支持行锁定和外键。在 MySQL 8 版本中，InnoDB 在自增、索引、加密、死锁、共享锁等方面做了大量的`改进和优化`，并且支持原子数据定义语言（DDL），提高了数据安全性，对事务提供更好的支持。

**6. 数据字典**

在之前的 MySQL 版本中，字典数据都存储在元数据文件和非事务表中。从 MySQL 8 开始新增了事务数据字典，在这个字典里存储着数据库对象信息，这些数据字典存储在内部事务表中。

**7. 原子数据定义语句**

MySQL 8 开始支持原子数据定义语句（Automic DDL），即`原子DDL`。目前，只有 InnoDB 存储引擎支持原子 DDL。原子数据定义语句（DDL）将与 DDL 操作相关的数据字典更新、存储引擎操作、二进制日志写入结合到一个单独的原子事务中，这使得即使服务器崩溃，事务也会提交或回滚。

使用支持原子操作的存储引擎所创建的表，在执行 DROP TABLE、CREATE TABLE、ALTER TABLE、 RENAME TABLE、TRUNCATE TABLE、CREATE TABLESPACE、DROP TABLESPACE 等操作时，都支持原子操作，即事务要么完全操作成功，要么失败后回滚，不再进行部分提交。

对于从 MySQL 5.7 复制到 MySQL 8 版本中的语句，可以添加`IF EXISTS`或`IF NOT EXISTS`语句来避免发生错误。

**8. 资源管理**

MySQL 8 开始支持创建和管理资源组，允许将服务器内运行的线程分配给特定的分组，以便线程根据组内可用资源执行。组属性能够控制组内资源，启用或限制组内资源消耗。数据库管理员能够根据不同的工作负载适当地更改这些属性。

目前，CPU 时间是可控资源，由“虚拟 CPU”这个概念来表示，此术语包含 CPU 的核心数，超线程，硬件线程等等。服务器在启动时确定可用的虚拟 CPU 数量。拥有对应权限的数据库管理员可以将这些 CPU 与资源组关联，并为资源组分配线程。

资源组组件为 MySQL 中的资源组管理提供了 SQL 接口。资源组的属性用于定义资源组。MySQL 中存在两个默认组，系统组和用户组，默认的组不能被删除，其属性也不能被更改。对于用户自定义的组，资源组创建时可初始化所有的属性，除去名字和类型，其他属性都可在创建之后进行更改。

在一些平台下，或进行了某些 MySQL 的配置时，资源管理的功能将受到限制，甚至不可用。例如，如果安装了线程池插件，或者使用的是 macOS 系统，资源管理将处于不可用状态。在 FreeBSD 和 Solaris 系统中，资源线程优先级将失效。在 Linux 系统中，只有配置了 CAP_SYS_NICE 属性，资源管理优先级才能发挥作用。

**9. 字符集支持**

MySQL 8 中默认的字符集由`latin1`更改为`utf8mb4`，并首次增加了日语所特定使用的集合，utf8mb4_ja_0900_as_cs。

**10. 优化器增强**

MySQL 优化器开始支持隐藏索引和降序索引。隐藏索引不会被优化器使用，验证索引的必要性时不需要删除索引，先将索引隐藏，如果优化器性能无影响就可以真正地删除索引。降序索引允许优化器对多个列进行排序，并且允许排序顺序不一致。

**11. 公用表表达式**

公用表表达式（Common Table Expressions）简称为 CTE，MySQL 现在支持递归和非递归两种形式的 CTE。CTE 通过在 SELECT 语句或其他特定语句前`使用WITH语句对临时结果集`进行命名。

基础语法如下：

> WITH cte_name (col_name1,col_name2 ...) AS (Subquery)
> SELECT \* FROM cte_name;

Subquery 代表子查询，子查询前使用 WITH 语句将结果集命名为 cte_name，在后续的查询中即可使用 cte_name 进行查询。

**12. 窗口函数**

MySQL 8 开始支持窗口函数。在之前的版本中已存在的大部分`聚合函数`在 MySQL 8 中也可以作为窗口函数来使用。

![窗口函数](https://img-blog.csdnimg.cn/e38806da43de438ba4b8cbf281ac5398.png)

**13. 正则表达式支持**

MySQL 在 8.0.4 以后的版本中采用支持 Unicode 的国际化组件库实现正则表达式操作，这种方式不仅能提供完全的 Unicode 支持，而且是多字节安全编码。MySQL 增加了 REGEXP_LIKE()、EGEXP_INSTR()、REGEXP_REPLACE()和 REGEXP_SUBSTR()等函数来提升性能。另外，regexp_stack_limit 和 regexp_time_limit 系统变量能够通过匹配引擎来控制资源消耗。

**14. 内部临时表**

`TempTable存储引擎取代MEMORY存储引擎成为内部临时表的默认存储引擎`。TempTable 存储引擎为 VARCHAR 和 VARBINARY 列提供高效存储。internal_tmp_mem_storage_engine 会话变量定义了内部临时表的存储引擎，可选的值有两个，TempTable 和 MEMORY，其中 TempTable 为默认的存储引擎。temptable_max_ram 系统配置项定义了 TempTable 存储引擎可使用的最大内存数量。

**15. 日志记录**

在 MySQL 8 中错误日志子系统由一系列 MySQL 组件构成。这些组件的构成由系统变量 log_error_services 来配置，能够实现日志事件的过滤和写入。

**16. 备份锁**

新的备份锁允许在线备份期间执行数据操作语句，同时阻止可能造成快照不一致的操作。新备份锁由 LOCK INSTANCE FOR BACKUP 和 UNLOCK INSTANCE 语法提供支持，执行这些操作需要备份管理员特权。

**17. 增强的 MySQL 复制**

MySQL 8 复制支持对`JSON文档`进行部分更新的`二进制日志记录`，该记录`使用紧凑的二进制格式`，从而节省记录完整 JSON 文档的空间。当使用基于语句的日志记录时，这种紧凑的日志记录会自动完成，并且可以通过将新的 binlog_row_value_options 系统变量值设置为 PARTIAL_JSON 来启用。

### 1.2 MySQL8.0 移除的旧特性

在 MySQL 5.7 版本上开发的应用程序如果使用了 MySQL8.0 移除的特性，语句可能会失败，或者产生不同的执行结果。为了避免这些问题，对于使用了移除特性的应用，应当尽力修正避免使用这些特性，并尽可能使用替代方法。

**1. 查询缓存**

`查询缓存已被移除`，删除的项有：

**（1）语句：** FLUSH QUERY CACHE 和 RESET QUERY CACHE。

**（2）系统变量：** query_cache_limit、query_cache_min_res_unit、query_cache_size、query_cache_type、query_cache_wlock_invalidate。

**（3）状态变量：** Qcache_free_blocks、Qcache_free_memory、Qcache_hits、Qcache_inserts、Qcache_lowmem_prunes、Qcache_not_cached、Qcache_queries_in_cache、Qcache_total_blocks。

**（4）线程状态：** checking privileges on cached query、checking query cache for query、invalidating query cache entries、sending cached result to client、storing result in query cache、waiting for query cache lock。

**2.加密相关**

删除的加密相关的内容有：ENCODE()、DECODE()、ENCRYPT()、DES_ENCRYPT()和 DES_DECRYPT()函数，配置项 des-key-file，系统变量 have_crypt，FLUSH 语句的 DES_KEY_FILE 选项，HAVE_CRYPT CMake 选项。

对于移除的 ENCRYPT()函数，考虑使用 SHA2()替代，对于其他移除的函数，使用 AES_ENCRYPT()和 AES_DECRYPT()替代。

**3.空间函数相关**

在 MySQL 5.7 版本中，多个空间函数已被标记为过时。这些过时函数在 MySQL 8 中都已被移除，只保留了对应的 ST\_和 MBR 函数。

**4.\N 和 NULL**

在 SQL 语句中，解析器不再将\N 视为 NULL，所以在 SQL 语句中应使用 NULL 代替\N。这项变化不会影响使用 LOAD DATA INFILE 或者 SELECT...INTO OUTFILE 操作文件的导入和导出。在这类操作中，NULL 仍等同于\N。

**5. mysql_install_db**

在 MySQL 分布中，已移除了 mysql_install_db 程序，数据字典初始化需要调用带着--initialize 或者--initialize-insecure 选项的 mysqld 来代替实现。另外，--bootstrap 和 INSTALL_SCRIPTDIR CMake 也已被删除。

**6.通用分区处理程序**

通用分区处理程序已从 MySQL 服务中被移除。为了实现给定表分区，表所使用的存储引擎需要自有的分区处理程序。

提供本地分区支持的 MySQL 存储引擎有两个，即 InnoDB 和 NDB，而在 MySQL 8 中只支持 InnoDB。

**7.系统和状态变量信息**

在 INFORMATION_SCHEMA 数据库中，对系统和状态变量信息不再进行维护。GLOBAL_VARIABLES、SESSION_VARIABLES、GLOBAL_STATUS、SESSION_STATUS 表都已被删除。另外，系统变量 show_compatibility_56 也已被删除。被删除的状态变量有 Slave_heartbeat_period、Slave_last_heartbeat,Slave_received_heartbeats、Slave_retried_transactions、Slave_running。以上被删除的内容都可使用性能模式中对应的内容进行替代。

**8.mysql_plugin 工具**

mysql_plugin 工具用来配置 MySQL 服务器插件，现已被删除，可使用--plugin-load 或--plugin-load-add 选项在服务器启动时加载插件或者在运行时使用 INSTALL PLUGIN 语句加载插件来替代该工具。

## 2. 新特性 1：窗口函数

### 2.1 使用窗口函数前后对比

假设我现在有这样一个数据表，它显示了某购物网站在每个城市每个区的销售额：

```sql
CREATE TABLE sales
(
  id INT PRIMARY KEY AUTO_INCREMENT,
  city VARCHAR(15),
  county VARCHAR(15),
  sales_value DECIMAL
);

INSERT INTO sales(city,county,sales_value)
VALUES
('北京','海淀',10.00),
('北京','朝阳',20.00),
('上海','黄埔',30.00),
('上海','长宁',10.00);
```

查询：

```sh
mysql> SELECT * FROM sales;
+----+------+--------+-------------+
| id | city | county | sales_value |
+----+------+--------+-------------+
|  1 | 北京 | 海淀    |          10 |
|  2 | 北京 | 朝阳    |          20 |
|  3 | 上海 | 黄埔    |          30 |
|  4 | 上海 | 长宁    |          10 |
+----+------+--------+-------------+
4 rows in set (0.00 sec)
```

**需求：** 现在计算这个网站在每个城市的销售总额、在全国的销售总额、每个区的销售额占所在城市销售额中的比率，以及占总销售额中的比率。

如果用分组和聚合函数，就需要分好几步来计算。

第一步，计算总销售金额，并存入临时表 a：

```sql
# 创建临时表
CREATE TEMPORARY TABLE a

# 计算总计金额
SELECT SUM(sales_value) AS sales_value
FROM sales;
```

查看一下临时表 a ：

```sh
mysql> SELECT * FROM a;
+-------------+
| sales_value |
+-------------+
|          70 |
+-------------+
1 row in set (0.00 sec)
```

第二步，计算每个城市的销售总额并存入临时表 b：

```sql
# 创建临时表
CREATE TEMPORARY TABLE b

# 计算城市销售合计
SELECT city,SUM(sales_value) AS sales_value
FROM sales
GROUP BY city;
```

查看临时表 b ：

```sh
mysql> SELECT * FROM b;
+------+-------------+
| city | sales_value |
+------+-------------+
| 北京 |          30 |
| 上海 |          40 |
+------+-------------+
2 rows in set (0.00 sec)
```

第三步，计算各区的销售占所在城市的总计金额的比例，和占全部销售总计金额的比例。我们可以通过下面的连接查询获得需要的结果：

```sh
mysql> SELECT s.city AS 城市,s.county AS 区,s.sales_value AS 区销售额,
    -> b.sales_value AS 市销售额,s.sales_value/b.sales_value AS 市比率,
    -> a.sales_value AS 总销售额,s.sales_value/a.sales_value AS 总比率
    -> FROM sales s
    -> JOIN b ON (s.city=b.city)  # 连接市统计结果临时表
    -> JOIN a  # 连接总计金额临时表
    -> ORDER BY s.city,s.county;
+------+------+----------+----------+--------+----------+--------+
| 城市  | 区   | 区销售额  | 市销售额   | 市比率  | 总销售额  | 总比率  |
+------+------+----------+----------+--------+----------+--------+
| 上海  | 长宁 |       10 |       40 | 0.2500 |       70 | 0.1429 |
| 上海  | 黄埔 |       30 |       40 | 0.7500 |       70 | 0.4286 |
| 北京  | 朝阳 |       20 |       30 | 0.6667 |       70 | 0.2857 |
| 北京  | 海淀 |       10 |       30 | 0.3333 |       70 | 0.1429 |
+------+------+----------+----------+--------+----------+--------+
4 rows in set (0.00 sec)
```

结果显示：市销售金额、市销售占比、总销售金额、总销售占比都计算出来了。

同样的查询，如果用窗口函数，就简单多了。我们可以用下面的代码来实现：

```sh
mysql> SELECT city AS 城市,county AS 区,sales_value AS 区销售额,
    -> SUM(sales_value) OVER(PARTITION BY city) AS 市销售额,  # 计算市销售额
    -> sales_value/SUM(sales_value) OVER(PARTITION BY city) AS 市比率,
    -> SUM(sales_value) OVER() AS 总销售额,  # 计算总销售额
    -> sales_value/SUM(sales_value) OVER() AS 总比率
    -> FROM sales
    -> ORDER BY city,county;
+------+------+----------+----------+--------+----------+--------+
| 城市  | 区   | 区销售额  | 市销售额   | 市比率  | 总销售额  | 总比率  |
+------+------+----------+----------+--------+----------+--------+
| 上海  | 长宁 |       10 |       40  | 0.2500 |       70 | 0.1429 |
| 上海  | 黄埔 |       30 |       40  | 0.7500 |       70 | 0.4286 |
| 北京  | 朝阳 |       20 |       30  | 0.6667 |       70 | 0.2857 |
| 北京  | 海淀 |       10 |       30  | 0.3333 |       70 | 0.1429 |
+------+------+----------+-----------+--------+----------+--------+
4 rows in set (0.00 sec)
```

结果显示，我们得到了与上面那种查询同样的结果。

使用窗口函数，只用了一步就完成了查询。而且，由于没有用到临时表，执行的效率也更高了。很显然，**在这种需要用到分组统计的结果对每一条记录进行计算的场景下，使用窗口函数更好**。

### 2.2 窗口函数分类

MySQL 从 8.0 版本开始支持窗口函数。窗口函数的作用类似于在查询中对数据进行分组，不同的是，分组操作会把分组的结果聚合成一条记录，而窗口函数是将结果置于每一条数据记录中。

窗口函数可以分为`静态窗口函数`和`动态窗口函数`。

- 静态窗口函数的窗口大小是固定的，不会因为记录的不同而不同；

- 动态窗口函数的窗口大小会随着记录的不同而变化。

  MySQL 官方网站窗口函数的网址为 https://dev.mysql.com/doc/refman/8.0/en/window-function-descriptions.html#function_row-number 。

窗口函数总体上可以分为序号函数、分布函数、前后函数、首尾函数和其他函数，如下表：

![窗口函数分类](https://img-blog.csdnimg.cn/abdc490bf3424240bb919a1b067dd195.png)

### 2.3 语法结构

窗口函数的语法结构是：

> 函数 OVER（[PARTITION BY 字段名 ORDER BY 字段名 ASC|DESC]）

或者是：

> 函数 OVER 窗口名 ... WINDOW 窗口名 AS （[PARTITION BY 字段名 ORDER BY 字段名 ASC|DESC]）

- OVER 关键字指定函数窗口的范围。

  - 如果省略后面括号中的内容，则窗口会包含满足 WHERE 条件的所有记录，窗口函数会基于所有满足 WHERE 条件的记录进行计算。

  - 如果 OVER 关键字后面的括号不为空，则可以使用如下语法设置窗口。

- 窗口名：为窗口设置一个别名，用来标识窗口。

- PARTITION BY 子句：指定窗口函数按照哪些字段进行分组。分组后，窗口函数可以在每个分组中分别执行。

- ORDER BY 子句：指定窗口函数按照哪些字段进行排序。执行排序操作使窗口函数按照排序后的数据记录的顺序进行编号。

- FRAME 子句：为分区中的某个子集定义规则，可以用来作为滑动窗口使用。

### 2.4 分类讲解

创建表：

```sql
CREATE TABLE goods
(
  id INT PRIMARY KEY AUTO_INCREMENT,
  category_id INT,
  category VARCHAR(15),
  NAME VARCHAR(30),
  price DECIMAL(10,2),
  stock INT,
  upper_time DATETIME
);
```

添加数据：

```sql
INSERT INTO goods(category_id,category,NAME,price,stock,upper_time)
VALUES
(1, '女装/女士精品', 'T恤', 39.90, 1000, '2023-8-21 00:00:00'),
(1, '女装/女士精品', '连衣裙', 79.90, 2500, '2023-8-21 00:00:00'),
(1, '女装/女士精品', '卫衣', 89.90, 1500, '2023-8-21 00:00:00'),
(1, '女装/女士精品', '牛仔裤', 89.90, 3500, '2023-8-21 00:00:00'),
(1, '女装/女士精品', '百褶裙', 29.90, 500, '2023-8-21 00:00:00'),
(1, '女装/女士精品', '呢绒外套', 399.90, 1200, '2023-8-21 00:00:00'),
(2, '户外运动', '自行车', 399.90, 1000, '2023-8-21 00:00:00'),
(2, '户外运动', '山地自行车', 1399.90, 2500, '2023-8-21 00:00:00'),
(2, '户外运动', '登山杖', 59.90, 1500, '2023-8-21 00:00:00'),
(2, '户外运动', '骑行装备', 399.90, 3500, '2023-8-21 00:00:00'),
(2, '户外运动', '运动外套', 799.90, 500, '2023-8-21 00:00:00'),
(2, '户外运动', '滑板', 499.90, 1200, '2023-8-21 00:00:00');
```

下面针对 goods 表中的数据来验证每个窗口函数的功能。

#### 2.4.1 序号函数

**1．ROW_NUMBER()函数**

ROW_NUMBER()函数能够对数据中的序号进行顺序显示。

举例：查询 goods 数据表中每个商品分类下价格降序排列的各个商品信息。

```sh
mysql> SELECT ROW_NUMBER() OVER(PARTITION BY category_id ORDER BY price DESC) AS row_num,
    -> id, category_id, category, NAME, price, stock
    -> FROM goods;
+---------+----+-------------+---------------+------------+---------+-------+
| row_num | id | category_id | category      | NAME       | price   | stock |
+---------+----+-------------+---------------+------------+---------+-------+
|       1 |  6 |           1 | 女装/女士精品   | 呢绒外套    |  399.90 |  1200 |
|       2 |  3 |           1 | 女装/女士精品   | 卫衣        |   89.90 |  1500 |
|       3 |  4 |           1 | 女装/女士精品   | 牛仔裤      |   89.90 |  3500 |
|       4 |  2 |           1 | 女装/女士精品   | 连衣裙      |   79.90 |  2500 |
|       5 |  1 |           1 | 女装/女士精品   | T恤        |   39.90 |  1000 |
|       6 |  5 |           1 | 女装/女士精品   | 百褶裙      |   29.90 |   500 |
|       1 |  8 |           2 | 户外运动       | 山地自行车   | 1399.90 |  2500 |
|       2 | 11 |           2 | 户外运动       | 运动外套     |  799.90 |   500 |
|       3 | 12 |           2 | 户外运动       | 滑板        |  499.90 |  1200 |
|       4 |  7 |           2 | 户外运动       | 自行车      |  399.90 |  1000 |
|       5 | 10 |           2 | 户外运动       | 骑行装备    |  399.90 |  3500 |
|       6 |  9 |           2 | 户外运动       | 登山杖      |   59.90 |  1500 |
+---------+----+-------------+---------------+------------+---------+-------+
12 rows in set (0.00 sec)
```

举例：查询 goods 数据表中每个商品分类下价格最高的 3 种商品信息。

```sh
mysql> SELECT *
    -> FROM (
    ->  SELECT ROW_NUMBER() OVER(PARTITION BY category_id ORDER BY price DESC) AS row_num,
    ->  id, category_id, category, NAME, price, stock
    ->  FROM goods) t
    -> WHERE row_num <= 3;
+---------+----+-------------+---------------+------------+---------+-------+
| row_num | id | category_id | category      | NAME       | price   | stock |
+---------+----+-------------+---------------+------------+---------+-------+
|       1 |  6 |           1 | 女装/女士精品   | 呢绒外套    |  399.90  |  1200 |
|       2 |  3 |           1 | 女装/女士精品   | 卫衣        |   89.90 |  1500 |
|       3 |  4 |           1 | 女装/女士精品   | 牛仔裤      |   89.90  |  3500 |
|       1 |  8 |           2 | 户外运动       | 山地自行车   | 1399.90  |  2500 |
|       2 | 11 |           2 | 户外运动       | 运动外套     |  799.90  |   500 |
|       3 | 12 |           2 | 户外运动       | 滑板        |  499.90  |  1200 |
+---------+----+-------------+---------------+------------+----------+-------+
6 rows in set (0.00 sec)
```

在名称为“女装/女士精品”的商品类别中，有两款商品的价格为 89.90 元，分别是卫衣和牛仔裤。两款商品的序号都应该为 2，而不是一个为 2，另一个为 3。此时，可以使用 RANK()函数和 DENSE_RANK()函数解决。

**2．RANK()函数**

使用 RANK()函数能够对序号进行并列排序，并且会跳过重复的序号，比如序号为 1、1、3。

举例：使用 RANK()函数获取 goods 数据表中各类别的价格从高到低排序的各商品信息。

```sh
mysql> SELECT RANK() OVER(PARTITION BY category_id ORDER BY price DESC) AS row_num,
    -> id, category_id, category, NAME, price, stock
    -> FROM goods;
+---------+----+-------------+---------------+------------+---------+-------+
| row_num | id | category_id | category      | NAME       | price   | stock |
+---------+----+-------------+---------------+------------+---------+-------+
|       1 |  6 |           1 | 女装/女士精品   | 呢绒外套    |  399.90 |  1200 |
|       2 |  3 |           1 | 女装/女士精品   | 卫衣        |   89.90 |  1500 |
|       2 |  4 |           1 | 女装/女士精品   | 牛仔裤      |   89.90 |  3500 |
|       4 |  2 |           1 | 女装/女士精品   | 连衣裙      |   79.90 |  2500 |
|       5 |  1 |           1 | 女装/女士精品   | T恤         |   39.90 |  1000 |
|       6 |  5 |           1 | 女装/女士精品   | 百褶裙      |   29.90 |   500 |
|       1 |  8 |           2 | 户外运动       | 山地自行车   | 1399.90 |  2500 |
|       2 | 11 |           2 | 户外运动       | 运动外套     |  799.90 |   500 |
|       3 | 12 |           2 | 户外运动       | 滑板        |  499.90 |  1200 |
|       4 |  7 |           2 | 户外运动       | 自行车      |  399.90 |  1000 |
|       4 | 10 |           2 | 户外运动       | 骑行装备    |  399.90 |  3500 |
|       6 |  9 |           2 | 户外运动       | 登山杖      |   59.90 |  1500 |
+---------+----+-------------+---------------+------------+---------+-------+
12 rows in set (0.00 sec)
```

举例：使用 RANK()函数获取 goods 数据表中类别为“女装/女士精品”的价格最高的 4 款商品信息。

```sh
mysql> SELECT *
    -> FROM(
    ->  SELECT RANK() OVER(PARTITION BY category_id ORDER BY price DESC) AS row_num,
    ->  id, category_id, category, NAME, price, stock
    ->  FROM goods) t
    -> WHERE category_id = 1 AND row_num <= 4;
+---------+----+-------------+---------------+----------+--------+-------+
| row_num | id | category_id | category      | NAME     | price  | stock |
+---------+----+-------------+---------------+----------+--------+-------+
|       1 |  6 |           1 | 女装/女士精品   | 呢绒外套  | 399.90 |  1200 |
|       2 |  3 |           1 | 女装/女士精品   | 卫衣      |  89.90 |  1500 |
|       2 |  4 |           1 | 女装/女士精品   | 牛仔裤    |  89.90 |  3500 |
|       4 |  2 |           1 | 女装/女士精品   | 连衣裙    |  79.90 |  2500 |
+---------+----+-------------+---------------+----------+--------+-------+
4 rows in set (0.00 sec)
```

可以看到，使用 RANK()函数得出的序号为 1、2、2、4，相同价格的商品序号相同，后面的商品序号是不连续的，跳过了重复的序号。

**3．DENSE_RANK()函数**

DENSE_RANK()函数对序号进行并列排序，并且不会跳过重复的序号，比如序号为 1、1、2。

举例：使用 DENSE_RANK()函数获取 goods 数据表中各类别的价格从高到低排序的各商品信息。

```sh
mysql> SELECT DENSE_RANK() OVER(PARTITION BY category_id ORDER BY price DESC) AS row_num,
    -> id, category_id, category, NAME, price, stock
    -> FROM goods;
+---------+----+-------------+---------------+------------+---------+-------+
| row_num | id | category_id | category      | NAME       | price   | stock |
+---------+----+-------------+---------------+------------+---------+-------+
|       1 |  6 |           1 | 女装/女士精品   | 呢绒外套    |  399.90 |  1200 |
|       2 |  3 |           1 | 女装/女士精品   | 卫衣        |   89.90 |  1500 |
|       2 |  4 |           1 | 女装/女士精品   | 牛仔裤      |   89.90 |  3500 |
|       3 |  2 |           1 | 女装/女士精品   | 连衣裙      |   79.90 |  2500 |
|       4 |  1 |           1 | 女装/女士精品   | T恤        |   39.90 |  1000 |
|       5 |  5 |           1 | 女装/女士精品   | 百褶裙      |   29.90 |   500 |
|       1 |  8 |           2 | 户外运动       | 山地自行车   | 1399.90 |  2500 |
|       2 | 11 |           2 | 户外运动       | 运动外套     |  799.90 |   500 |
|       3 | 12 |           2 | 户外运动       | 滑板        |  499.90 |  1200 |
|       4 |  7 |           2 | 户外运动       | 自行车       |  399.90 |  1000 |
|       4 | 10 |           2 | 户外运动       | 骑行装备     |  399.90 |  3500 |
|       5 |  9 |           2 | 户外运动       | 登山杖       |   59.90 |  1500 |
+---------+----+-------------+---------------+------------+---------+-------+
12 rows in set (0.00 sec)
```

举例：使用 DENSE_RANK()函数获取 goods 数据表中类别为“女装/女士精品”的价格最高的 4 款商品信息。

```sh
mysql> SELECT *
    -> FROM(
    ->  SELECT DENSE_RANK() OVER(PARTITION BY category_id ORDER BY price DESC) AS row_num,
    ->  id, category_id, category, NAME, price, stock
    ->  FROM goods) t
    -> WHERE category_id = 1 AND row_num <= 3;
+---------+----+-------------+---------------+----------+--------+-------+
| row_num | id | category_id | category      | NAME     | price  | stock |
+---------+----+-------------+---------------+----------+--------+-------+
|       1 |  6 |           1 | 女装/女士精品   | 呢绒外套  | 399.90 |  1200 |
|       2 |  3 |           1 | 女装/女士精品   | 卫衣     |  89.90  |  1500 |
|       2 |  4 |           1 | 女装/女士精品   | 牛仔裤    |  89.90 |  3500 |
|       3 |  2 |           1 | 女装/女士精品   | 连衣裙    |  79.90 |  2500 |
+---------+----+-------------+---------------+----------+--------+-------+
4 rows in set (0.00 sec)
```

可以看到，使用 DENSE_RANK()函数得出的行号为 1、2、2、3，相同价格的商品序号相同，后面的商品序号是连续的，并且没有跳过重复的序号。

#### 2.4.2 分布函数

**1．PERCENT_RANK()函数**

PERCENT_RANK()函数是等级值百分比函数。按照如下方式进行计算。

> (rank - 1) / (rows - 1)

其中，rank 的值为使用 RANK()函数产生的序号，rows 的值为当前窗口的总记录数。

举例：计算 goods 数据表中名称为“女装/女士精品”的类别下的商品的 PERCENT_RANK 值。

```sh
# 写法一：
SELECT RANK() OVER (PARTITION BY category_id ORDER BY price DESC) AS r,
PERCENT_RANK() OVER (PARTITION BY category_id ORDER BY price DESC) AS pr,
id, category_id, category, NAME, price, stock
FROM goods
WHERE category_id = 1;

# 写法二：
mysql> SELECT RANK() OVER w AS r,
    -> PERCENT_RANK() OVER w AS pr,
    -> id, category_id, category, NAME, price, stock
    -> FROM goods
    -> WHERE category_id = 1 WINDOW w AS (PARTITION BY category_id ORDER BY price DESC);
+---+-----+----+-------------+---------------+----------+--------+-------+
| r | pr  | id | category_id | category      | NAME     | price  | stock |
+---+-----+----+-------------+---------------+----------+--------+-------+
| 1 |   0 |  6 |           1 | 女装/女士精品   | 呢绒外套  | 399.90 |  1200 |
| 2 | 0.2 |  3 |           1 | 女装/女士精品   | 卫衣     |  89.90 |  1500 |
| 2 | 0.2 |  4 |           1 | 女装/女士精品   | 牛仔裤   |  89.90 |  3500  |
| 4 | 0.6 |  2 |           1 | 女装/女士精品   | 连衣裙   |  79.90 |  2500  |
| 5 | 0.8 |  1 |           1 | 女装/女士精品   | T恤      |  39.90 |  1000 |
| 6 |   1 |  5 |           1 | 女装/女士精品   | 百褶裙   |  29.90  |   500 |
+---+-----+----+-------------+---------------+----------+--------+-------+
6 rows in set (0.00 sec)
```

**2．CUME_DIST()函数**

CUME_DIST()函数主要用于查询小于或等于某个值的比例。

举例：查询 goods 数据表中小于或等于当前价格的比例。

```sh
mysql> SELECT CUME_DIST() OVER(PARTITION BY category_id ORDER BY price ASC) AS cd,
    -> id, category, NAME, price
    -> FROM goods;
+---------------------+----+---------------+------------+---------+
| cd                  | id | category      | NAME       | price   |
+---------------------+----+---------------+------------+---------+
| 0.16666666666666666 |  5 | 女装/女士精品   | 百褶裙      |   29.90 |
|  0.3333333333333333 |  1 | 女装/女士精品   | T恤        |   39.90 |
|                 0.5 |  2 | 女装/女士精品   | 连衣裙      |   79.90 |
|  0.8333333333333334 |  3 | 女装/女士精品   | 卫衣        |   89.90 |
|  0.8333333333333334 |  4 | 女装/女士精品   | 牛仔裤      |   89.90 |
|                   1 |  6 | 女装/女士精品   | 呢绒外套    |  399.90 |
| 0.16666666666666666 |  9 | 户外运动       | 登山杖      |   59.90 |
|                 0.5 |  7 | 户外运动       | 自行车      |  399.90 |
|                 0.5 | 10 | 户外运动       | 骑行装备     |  399.90 |
|  0.6666666666666666 | 12 | 户外运动       | 滑板        |  499.90 |
|  0.8333333333333334 | 11 | 户外运动       | 运动外套    |  799.90 |
|                   1 |  8 | 户外运动       | 山地自行车   | 1399.90 |
+---------------------+----+---------------+------------+---------+
12 rows in set (0.00 sec)
```

#### 2.4.3 前后函数

**1．LAG(expr,n)函数**

LAG(expr,n)函数返回当前行的前 n 行的 expr 的值。

举例：查询 goods 数据表中前一个商品价格与当前商品价格的差值。

```sh
mysql> SELECT id, category, NAME, price, pre_price, price - pre_price AS diff_price
    -> FROM (
    ->  SELECT  id, category, NAME, price,LAG(price,1) OVER w AS pre_price
    ->  FROM goods
    ->  WINDOW w AS (PARTITION BY category_id ORDER BY price)) t;
+----+---------------+------------+---------+-----------+------------+
| id | category      | NAME       | price   | pre_price | diff_price |
+----+---------------+------------+---------+-----------+------------+
|  5 | 女装/女士精品   | 百褶裙      |   29.90 |      NULL |       NULL |
|  1 | 女装/女士精品   | T恤        |   39.90 |     29.90 |      10.00 |
|  2 | 女装/女士精品   | 连衣裙      |   79.90 |     39.90 |      40.00 |
|  3 | 女装/女士精品   | 卫衣       |   89.90 |     79.90 |      10.00 |
|  4 | 女装/女士精品   | 牛仔裤      |   89.90 |     89.90 |       0.00 |
|  6 | 女装/女士精品   | 呢绒外套    |  399.90 |     89.90 |     310.00 |
|  9 | 户外运动       | 登山杖      |   59.90 |      NULL |       NULL |
|  7 | 户外运动       | 自行车      |  399.90 |     59.90 |     340.00 |
| 10 | 户外运动       | 骑行装备    |  399.90 |    399.90 |       0.00 |
| 12 | 户外运动       | 滑板       |  499.90 |    399.90 |     100.00 |
| 11 | 户外运动       | 运动外套    |  799.90 |    499.90 |     300.00 |
|  8 | 户外运动       | 山地自行车  | 1399.90 |    799.90 |     600.00 |
+----+---------------+------------+---------+-----------+------------+
12 rows in set (0.00 sec)
```

**2．LEAD(expr,n)函数**

LEAD(expr,n)函数返回当前行的后 n 行的 expr 的值。

举例：查询 goods 数据表中后一个商品价格与当前商品价格的差值。

```sh
mysql> SELECT id, category, NAME, behind_price, price,behind_price - price AS diff_price
    -> FROM(
    ->  SELECT id, category, NAME, price,LEAD(price, 1) OVER w AS behind_price
    ->  FROM goods WINDOW w AS (PARTITION BY category_id ORDER BY price)) t;
+----+---------------+------------+--------------+---------+------------+
| id | category      | NAME       | behind_price | price   | diff_price |
+----+---------------+------------+--------------+---------+------------+
|  5 | 女装/女士精品   | 百褶裙      |        39.90 |   29.90 |      10.00 |
|  1 | 女装/女士精品   | T恤        |        79.90 |   39.90 |      40.00 |
|  2 | 女装/女士精品   | 连衣裙      |        89.90 |   79.90 |      10.00 |
|  3 | 女装/女士精品   | 卫衣        |        89.90 |   89.90 |       0.00 |
|  4 | 女装/女士精品   | 牛仔裤      |       399.90 |   89.90 |     310.00 |
|  6 | 女装/女士精品   | 呢绒外套     |         NULL |  399.90 |       NULL |
|  9 | 户外运动       | 登山杖       |       399.90 |   59.90 |     340.00 |
|  7 | 户外运动       | 自行车       |       399.90 |  399.90 |       0.00 |
| 10 | 户外运动       | 骑行装备     |       499.90 |  399.90 |     100.00 |
| 12 | 户外运动       | 滑板        |       799.90 |  499.90 |     300.00 |
| 11 | 户外运动       | 运动外套     |      1399.90 |  799.90 |     600.00 |
|  8 | 户外运动       | 山地自行车   |         NULL | 1399.90 |       NULL |
+----+---------------+------------+--------------+---------+------------+
12 rows in set (0.00 sec)
```

#### 2.4.4 首尾函数

**1．FIRST_VALUE(expr)函数**

FIRST_VALUE(expr)函数返回第一个 expr 的值。

举例：按照价格排序，查询第 1 个商品的价格信息。

```sh
mysql> SELECT id, category, NAME, price, stock,FIRST_VALUE(price) OVER w AS first_price
    -> FROM goods WINDOW w AS (PARTITION BY category_id ORDER BY price);
+----+---------------+------------+---------+-------+-------------+
| id | category      | NAME       | price   | stock | first_price |
+----+---------------+------------+---------+-------+-------------+
|  5 | 女装/女士精品   | 百褶裙      |   29.90 |   500 |       29.90 |
|  1 | 女装/女士精品   | T恤        |   39.90 |  1000 |       29.90 |
|  2 | 女装/女士精品   | 连衣裙      |   79.90 |  2500 |       29.90 |
|  3 | 女装/女士精品   | 卫衣       |   89.90 |  1500 |       29.90 |
|  4 | 女装/女士精品   | 牛仔裤      |   89.90 |  3500 |       29.90 |
|  6 | 女装/女士精品   | 呢绒外套    |  399.90 |  1200 |       29.90 |
|  9 | 户外运动       | 登山杖      |   59.90 |  1500 |       59.90 |
|  7 | 户外运动       | 自行车      |  399.90 |  1000 |       59.90 |
| 10 | 户外运动       | 骑行装备    |  399.90 |  3500 |       59.90 |
| 12 | 户外运动       | 滑板       |  499.90 |  1200 |       59.90 |
| 11 | 户外运动       | 运动外套    |  799.90 |   500 |       59.90 |
|  8 | 户外运动       | 山地自行车  | 1399.90 |  2500 |       59.90 |
+----+---------------+------------+---------+-------+-------------+
12 rows in set (0.00 sec)
```

**2．LAST_VALUE(expr)函数**

LAST_VALUE(expr)函数返回最后一个 expr 的值。

举例：按照价格排序，查询最后一个商品的价格信息。

```sh
mysql> SELECT id, category, NAME, price, stock,LAST_VALUE(price) OVER w AS last_price
    -> FROM goods WINDOW w AS (PARTITION BY category_id ORDER BY price);
+----+---------------+------------+---------+-------+------------+
| id | category      | NAME       | price   | stock | last_price |
+----+---------------+------------+---------+-------+------------+
|  5 | 女装/女士精品   | 百褶裙     |   29.90 |   500 |      29.90 |
|  1 | 女装/女士精品   | T恤        |   39.90 |  1000 |      39.90 |
|  2 | 女装/女士精品   | 连衣裙     |   79.90 |  2500 |      79.90 |
|  3 | 女装/女士精品   | 卫衣       |   89.90 |  1500 |      89.90 |
|  4 | 女装/女士精品   | 牛仔裤     |   89.90 |  3500 |      89.90 |
|  6 | 女装/女士精品   | 呢绒外套   |  399.90 |  1200 |     399.90 |
|  9 | 户外运动       | 登山杖     |   59.90 |  1500 |      59.90 |
|  7 | 户外运动       | 自行车     |  399.90 |  1000 |     399.90 |
| 10 | 户外运动       | 骑行装备   |  399.90 |  3500 |     399.90 |
| 12 | 户外运动       | 滑板       |  499.90 |  1200 |     499.90 |
| 11 | 户外运动       | 运动外套   |  799.90 |   500 |     799.90 |
|  8 | 户外运动       | 山地自行车 | 1399.90 |  2500 |    1399.90 |
+----+---------------+------------+---------+-------+------------+
12 rows in set (0.00 sec)
```

#### 2.4.5 其他函数

**1．NTH_VALUE(expr,n)函数**

NTH_VALUE(expr,n)函数返回第 n 个 expr 的值。

举例：查询 goods 数据表中排名第 2 和第 3 的价格信息。

```sh
mysql> SELECT id, category, NAME, price,NTH_VALUE(price,2) OVER w AS second_price,
    -> NTH_VALUE(price,3) OVER w AS third_price
    -> FROM goods WINDOW w AS (PARTITION BY category_id ORDER BY price);
+----+---------------+------------+---------+--------------+-------------+
| id | category      | NAME       | price   | second_price | third_price |
+----+---------------+------------+---------+--------------+-------------+
|  5 | 女装/女士精品   | 百褶裙     |   29.90 |         NULL |        NULL |
|  1 | 女装/女士精品   | T恤        |   39.90 |        39.90 |        NULL |
|  2 | 女装/女士精品   | 连衣裙     |   79.90 |        39.90 |       79.90 |
|  3 | 女装/女士精品   | 卫衣       |   89.90 |        39.90 |       79.90 |
|  4 | 女装/女士精品   | 牛仔裤     |   89.90 |        39.90 |       79.90 |
|  6 | 女装/女士精品   | 呢绒外套   |  399.90 |        39.90 |       79.90 |
|  9 | 户外运动       | 登山杖     |   59.90 |         NULL |        NULL |
|  7 | 户外运动       | 自行车     |  399.90 |       399.90 |      399.90 |
| 10 | 户外运动       | 骑行装备   |  399.90 |       399.90 |      399.90 |
| 12 | 户外运动       | 滑板       |  499.90 |       399.90 |      399.90 |
| 11 | 户外运动       | 运动外套   |  799.90 |       399.90 |      399.90 |
|  8 | 户外运动       | 山地自行车 | 1399.90 |       399.90 |      399.90 |
+----+---------------+------------+---------+--------------+-------------+
12 rows in set (0.00 sec)
```

**2．NTILE(n)函数**

NTILE(n)函数将分区中的有序数据分为 n 个桶，记录桶编号。

举例：将 goods 表中的商品按照价格分为 3 组。

```sh
mysql> SELECT NTILE(3) OVER w AS nt,id, category, NAME, price
    -> FROM goods WINDOW w AS (PARTITION BY category_id ORDER BY price);
+----+----+---------------+------------+---------+
| nt | id | category      | NAME       | price   |
+----+----+---------------+------------+---------+
|  1 |  5 | 女装/女士精品 | 百褶裙     |   29.90 |
|  1 |  1 | 女装/女士精品 | T恤        |   39.90 |
|  2 |  2 | 女装/女士精品 | 连衣裙     |   79.90 |
|  2 |  3 | 女装/女士精品 | 卫衣       |   89.90 |
|  3 |  4 | 女装/女士精品 | 牛仔裤     |   89.90 |
|  3 |  6 | 女装/女士精品 | 呢绒外套   |  399.90 |
|  1 |  9 | 户外运动      | 登山杖     |   59.90 |
|  1 |  7 | 户外运动      | 自行车     |  399.90 |
|  2 | 10 | 户外运动      | 骑行装备   |  399.90 |
|  2 | 12 | 户外运动      | 滑板       |  499.90 |
|  3 | 11 | 户外运动      | 运动外套   |  799.90 |
|  3 |  8 | 户外运动      | 山地自行车 | 1399.90 |
+----+----+---------------+------------+---------+
12 rows in set (0.00 sec)
```

### 2.5 小 结

窗口函数的特点是可以分组，而且可以在分组内排序。另外，窗口函数不会因为分组而减少原表中的行数，这对我们在原表数据的基础上进行统计和排序非常有用。

## 3. 新特性 2：公用表表达式

公用表表达式（或通用表表达式）简称为 CTE（Common Table Expressions）。CTE 是一个命名的临时结果集，作用范围是当前语句。CTE 可以理解成一个可以复用的子查询，当然跟子查询还是有点区别的，CTE 可以引用其他 CTE，但子查询不能引用其他子查询。所以，可以考虑代替子查询。

依据语法结构和执行方式的不同，公用表表达式分为`普通公用表表达式`和`递归公用表表达式` 2 种。

### 3.1 普通公用表表达式

普通公用表表达式的语法结构是：

> WITH CTE 名称
> AS （子查询）
> SELECT|DELETE|UPDATE 语句;

普通公用表表达式类似于子查询，不过，跟子查询不同的是，它可以被多次引用，而且可以被其他的普通公用表表达式所引用。

举例：查询员工所在的部门的详细信息。

```sh
mysql> SELECT * FROM departments
    -> WHERE department_id IN (
    ->                  SELECT DISTINCT department_id
    ->                  FROM employees
    ->                  );
+---------------+------------------+------------+-------------+
| department_id | department_name  | manager_id | location_id |
+---------------+------------------+------------+-------------+
|            10 | Administration   |        200 |        1700 |
|            20 | Marketing        |        201 |        1800 |
|            30 | Purchasing       |        114 |        1700 |
|            40 | Human Resources  |        203 |        2400 |
|            50 | Shipping         |        121 |        1500 |
|            60 | IT               |        103 |        1400 |
|            70 | Public Relations |        204 |        2700 |
|            80 | Sales            |        145 |        2500 |
|            90 | Executive        |        100 |        1700 |
|           100 | Finance          |        108 |        1700 |
|           110 | Accounting       |        205 |        1700 |
+---------------+------------------+------------+-------------+
11 rows in set (0.00 sec)
```

这个查询也可以用普通公用表表达式的方式完成：

```sh
mysql> WITH emp_dept_id
    -> AS (SELECT DISTINCT department_id FROM employees)
    -> SELECT *
    -> FROM departments d JOIN emp_dept_id e
    -> ON d.department_id = e.department_id;
+---------------+------------------+------------+-------------+---------------+
| department_id | department_name  | manager_id | location_id | department_id |
+---------------+------------------+------------+-------------+---------------+
|            90 | Executive        |        100 |        1700 |            90 |
|            60 | IT               |        103 |        1400 |            60 |
|           100 | Finance          |        108 |        1700 |           100 |
|            30 | Purchasing       |        114 |        1700 |            30 |
|            50 | Shipping         |        121 |        1500 |            50 |
|            80 | Sales            |        145 |        2500 |            80 |
|            10 | Administration   |        200 |        1700 |            10 |
|            20 | Marketing        |        201 |        1800 |            20 |
|            40 | Human Resources  |        203 |        2400 |            40 |
|            70 | Public Relations |        204 |        2700 |            70 |
|           110 | Accounting       |        205 |        1700 |           110 |
+---------------+------------------+------------+-------------+---------------+
11 rows in set (0.00 sec)
```

例子说明，公用表表达式可以起到子查询的作用。以后如果遇到需要使用子查询的场景，你可以在查询之前，先定义公用表表达式，然后在查询中用它来代替子查询。而且，跟子查询相比，公用表表达式有一个优点，就是定义过公用表表达式之后的查询，可以像一个表一样多次引用公用表表达式，而子查询则不能。

### 3.2 递归公用表表达式

递归公用表表达式也是一种公用表表达式，只不过，除了普通公用表表达式的特点以外，它还有自己的特点，就是**可以调用自己**。它的语法结构是：

> WITH RECURSIVE
> CTE 名称 AS （子查询）
> SELECT|DELETE|UPDATE 语句;

递归公用表表达式由 2 部分组成，分别是种子查询和递归查询，中间通过关键字 UNION [ALL]进行连接。这里的**种子查询，意思就是获得递归的初始值**。这个查询只会运行一次，以创建初始数据集，之后递归查询会一直执行，直到没有任何新的查询数据产生，递归返回。

**案例：** 针对于我们常用的 employees 表，包含 employee_id，last_name 和 manager_id 三个字段。如果 a 是 b 的管理者，那么，我们可以把 b 叫做 a 的下属，如果同时 b 又是 c 的管理者，那么 c 就是 b 的下属，是 a 的下下属。

下面我们尝试用查询语句列出所有具有下下属身份的人员信息。

如果用我们之前学过的知识来解决，会比较复杂，至少要进行 4 次查询才能搞定：

- 第一步，先找出初代管理者，就是不以任何别人为管理者的人，把结果存入临时表；

- 第二步，找出所有以初代管理者为管理者的人，得到一个下属集，把结果存入临时表；

- 第三步，找出所有以下属为管理者的人，得到一个下下属集，把结果存入临时表；

- 第四步，找出所有以下下属为管理者的人，得到一个结果集。

如果第四步的结果集为空，则计算结束，第三步的结果集就是我们需要的下下属集了，否则就必须继续进行第四步，一直到结果集为空为止。比如上面的这个数据表，就需要到第五步，才能得到空结果集。而且，最后还要进行第六步：把第三步和第四步的结果集合并，这样才能最终获得我们需要的结果集。

如果用递归公用表表达式，就非常简单了。我介绍下具体的思路。

- 用递归公用表表达式中的种子查询，找出初代管理者。字段 n 表示代次，初始值为 1，表示是第一代管理者。

- 用递归公用表表达式中的递归查询，查出以这个递归公用表表达式中的人为管理者的人，并且代次的值加 1。直到没有人以这个递归公用表表达式中的人为管理者了，递归返回。

- 在最后的查询中，选出所有代次大于等于 3 的人，他们肯定是第三代及以上代次的下属了，也就是下下属了。这样就得到了我们需要的结果集。

这里看似也是 3 步，实际上是一个查询的 3 个部分，只需要执行一次就可以了。而且也不需要用临时表保存中间结果，比刚刚的方法简单多了。

**代码实现：**

```sql
WITH RECURSIVE cte
AS
(
  # 种子查询，找到第一代领导
  SELECT employee_id,last_name,manager_id,1 AS n FROM employees WHERE employee_id = 100
  UNION ALL
  SELECT a.employee_id,a.last_name,a.manager_id,n+1 FROM employees AS a JOIN cte

  # 递归查询，找出以递归公用表表达式的人为领导的人
  ON (a.manager_id = cte.employee_id)
)
SELECT employee_id,last_name FROM cte WHERE n >= 3;
```

总之，递归公用表表达式对于查询一个有共同的根节点的树形结构数据，非常有用。它可以不受层级的限制，轻松查出所有节点的数据。如果用其他的查询方式，就比较复杂了。

### 3.3 小 结

公用表表达式的作用是可以替代子查询，而且可以被多次引用。递归公用表表达式对查询有一个共同根节点的树形结构数据非常高效，可以轻松搞定其他查询方式难以处理的查询。

# 第 19 章 写在最后

## 1. 分享 1

![分享 1](https://img-blog.csdnimg.cn/2ebcdaa608e24d71bb2531e3a0a80621.png)

## 2. 分享 2

如何看待生活上、工作上的冗余、反冗余？

又如何看待社会的脆弱性？反脆弱性？

个人如何应对？
