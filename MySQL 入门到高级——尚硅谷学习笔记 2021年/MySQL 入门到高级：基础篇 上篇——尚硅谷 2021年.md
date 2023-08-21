<!-- @import "[TOC]" {cmd="toc" depthFrom=1 depthTo=6 orderedList=false} -->

# MySQL 入门到高级：基础篇 上篇——尚硅谷 2021 年

<!-- code_chunk_output -->

- [MySQL 入门到高级：基础篇 上篇——尚硅谷 2021 年](#mysql-入门到高级基础篇-上篇尚硅谷-2021-年)
- [第 0 章 写在前面](#第-0-章-写在前面)
  - [1. MySQL 数据库基础篇大纲](#1-mysql-数据库基础篇大纲)
    - [1.1 数据库概述与 MySQL 安装篇](#11-数据库概述与-mysql-安装篇)
    - [1.2 SQL 之 SELECT 使用篇](#12-sql-之-select-使用篇)
    - [1.3 SQL 之 DDL、DML、DCL 使用篇](#13-sql-之-ddl-dml-dcl-使用篇)
    - [1.4 其它数据库对象篇](#14-其它数据库对象篇)
    - [1.5 MySQL8 新特性篇](#15-mysql8-新特性篇)
  - [2. MySQL 高级特性篇大纲](#2-mysql-高级特性篇大纲)
    - [2.1 MySQL 架构篇](#21-mysql-架构篇)
    - [2.2 索引及调优篇](#22-索引及调优篇)
    - [2.3 事务篇](#23-事务篇)
    - [2.4 日志与备份篇](#24-日志与备份篇)
  - [3. MySQL 高手是怎样炼成的](#3-mysql-高手是怎样炼成的)
  - [4. 本套课程适合人群](#4-本套课程适合人群)
  - [5. 希望你能获取的](#5-希望你能获取的)
- [第 1 章 数据库概述](#第-1-章-数据库概述)
  - [1. 为什么要使用数据库](#1-为什么要使用数据库)
  - [2. 数据库与数据库管理系统](#2-数据库与数据库管理系统)
    - [2.1 数据库的相关概念](#21-数据库的相关概念)
    - [2.2 数据库与数据库管理系统的关系](#22-数据库与数据库管理系统的关系)
    - [2.3 常见的数据库管理系统排名(DBMS)](#23-常见的数据库管理系统排名dbms)
    - [2.4 常见的数据库介绍](#24-常见的数据库介绍)
  - [3. MySQL 介绍](#3-mysql-介绍)
    - [3.1 概述](#31-概述)
    - [3.2 MySQL 发展史重大事件](#32-mysql-发展史重大事件)
    - [1.4 关于 MySQL 8.0](#14-关于-mysql-80)
    - [1.5 Why choose MySQL?](#15-why-choose-mysql)
    - [1.6 Oracle vs MySQL](#16-oracle-vs-mysql)
  - [4. RDBMS 与 非 RDBMS](#4-rdbms-与-非-rdbms)
    - [4.1 关系型数据库(RDBMS)](#41-关系型数据库rdbms)
      - [4.1.1 实质](#411-实质)
      - [4.1.2 优势](#412-优势)
    - [4.2 非关系型数据库(非 RDBMS)](#42-非关系型数据库非-rdbms)
      - [4.2.1 介绍](#421-介绍)
      - [4.2.2 有哪些非关系型数据库](#422-有哪些非关系型数据库)
      - [4.2.3 NoSQL 的演变](#423-nosql-的演变)
    - [4.3 小结](#43-小结)
  - [5. 关系型数据库设计规则](#5-关系型数据库设计规则)
    - [5.1 表、记录、字段](#51-表-记录-字段)
    - [5.2 表的关联关系](#52-表的关联关系)
      - [5.2.1 一对一关联（one-to-one）](#521-一对一关联one-to-one)
      - [5.2.2 一对多关系（one-to-many）](#522-一对多关系one-to-many)
      - [5.2.3 多对多（many-to-many）](#523-多对多many-to-many)
      - [5.3.4 自我引用(Self reference)](#534-自我引用self-reference)
- [第 2 章 MySQL 环境搭建](#第-2-章-mysql-环境搭建)
  - [1. MySQL 的卸载](#1-mysql-的卸载)
    - [1.1 步骤 1：停止 MySQL 服务](#11-步骤-1停止-mysql-服务)
    - [1.2 步骤 2：软件的卸载](#12-步骤-2软件的卸载)
    - [1.3 步骤 3：残余文件的清理](#13-步骤-3残余文件的清理)
    - [1.4 步骤 4：清理注册表（选做）](#14-步骤-4清理注册表选做)
    - [1.5 步骤 5：删除环境变量配置](#15-步骤-5删除环境变量配置)
  - [2. MySQL 的下载、安装、配置](#2-mysql-的下载-安装-配置)
    - [2.1 MySQL 的 4 大版本](#21-mysql-的-4-大版本)
    - [2.2 软件的下载](#22-软件的下载)
    - [2.3 MySQL8.0 版本的安装](#23-mysql80-版本的安装)
    - [2.4 配置 MySQL8.0](#24-配置-mysql80)
    - [2.5 配置 MySQL8.0 环境变量](#25-配置-mysql80-环境变量)
    - [2.6 MySQL5.7 版本的安装、配置](#26-mysql57-版本的安装-配置)
    - [2.7 安装失败问题](#27-安装失败问题)
  - [3. MySQL 的登录](#3-mysql-的登录)
    - [3.1 服务的启动与停止](#31-服务的启动与停止)
      - [3.1.1 方式 1：使用图形界面工具](#311-方式-1使用图形界面工具)
      - [3.1.2 方式 2：使用命令行工具](#312-方式-2使用命令行工具)
    - [3.2 自带客户端的登录与退出](#32-自带客户端的登录与退出)
      - [3.2.1 登录方式 1：MySQL 自带客户端](#321-登录方式-1mysql-自带客户端)
      - [3.2.2 登录方式 2：windows 命令行](#322-登录方式-2windows-命令行)
      - [3.2.3 退出登录](#323-退出登录)
  - [4. MySQL 演示使用](#4-mysql-演示使用)
    - [4.1 MySQL 的使用演示](#41-mysql-的使用演示)
    - [4.2 MySQL 的编码设置](#42-mysql-的编码设置)
      - [4.2.1 MySQL5.7 中](#421-mysql57-中)
      - [4.2.2 MySQL8.0 中](#422-mysql80-中)
  - [5. MySQL 图形化管理工具](#5-mysql-图形化管理工具)
    - [5.1 工具 1. MySQL Workbench](#51-工具-1-mysql-workbench)
    - [5.2 工具 2. Navicat](#52-工具-2-navicat)
    - [5.3 工具 3. SQLyog](#53-工具-3-sqlyog)
    - [5.4 工具 4：dbeaver](#54-工具-4dbeaver)
    - [5.5 可能出现连接问题：](#55-可能出现连接问题)
  - [6. MySQL 目录结构与源码](#6-mysql-目录结构与源码)
    - [6.1 主要目录结构](#61-主要目录结构)
    - [6.2 MySQL 源代码获取](#62-mysql-源代码获取)
  - [7. 常见问题的解决(课外内容)](#7-常见问题的解决课外内容)
    - [7.1 问题 1：root 用户密码忘记，重置的操作](#71-问题-1root-用户密码忘记重置的操作)
    - [7.2 问题 2：mysql 命令报“不是内部或外部命令”](#72-问题-2mysql-命令报不是内部或外部命令)
    - [7.3 问题 3：错误 ERROR ：没有选择数据库就操作表格和数据](#73-问题-3错误-error-没有选择数据库就操作表格和数据)
    - [7.4 问题 4：命令行客户端的字符集问题](#74-问题-4命令行客户端的字符集问题)
    - [7.5 问题 5：修改数据库和表的字符编码](#75-问题-5修改数据库和表的字符编码)
- [第 3 章 基本的 SELECT 语句](#第-3-章-基本的-select-语句)
  - [1. SQL 概述](#1-sql-概述)
    - [1.1 SQL 背景知识](#11-sql-背景知识)
    - [1.2 SQL 语言排行榜](#12-sql-语言排行榜)
    - [1.3 SQL 分类](#13-sql-分类)
  - [2. SQL 语言的规则与规范](#2-sql-语言的规则与规范)
    - [2.1 基本规则](#21-基本规则)
    - [2.2 SQL 大小写规范 （建议遵守）](#22-sql-大小写规范-建议遵守)
    - [2.3 注释](#23-注释)
    - [2.4 命名规则（暂时了解）](#24-命名规则暂时了解)
    - [2.5 数据导入指令](#25-数据导入指令)
  - [3. 基本的 SELECT 语句](#3-基本的-select-语句)
    - [3.1 SELECT...](#31-select)
    - [3.2 SELECT ... FROM](#32-select--from)
    - [3.3 列的别名](#33-列的别名)
    - [3.4 去除重复行](#34-去除重复行)
    - [3.5 空值参与运算](#35-空值参与运算)
    - [3.6 着重号](#36-着重号)
    - [3.7 查询常数](#37-查询常数)
  - [4. 显示表结构](#4-显示表结构)
  - [5. 过滤数据](#5-过滤数据)
- [第 4 章 运算符](#第-4-章-运算符)
  - [1. 算术运算符](#1-算术运算符)
  - [2. 比较运算符](#2-比较运算符)
  - [3. 逻辑运算符](#3-逻辑运算符)
  - [4. 位运算符](#4-位运算符)
  - [5. 运算符的优先级](#5-运算符的优先级)
  - [6. 拓展：使用正则表达式查询](#6-拓展使用正则表达式查询)
- [第 5 章 排序与分页](#第-5-章-排序与分页)
  - [1. 排序数据](#1-排序数据)
    - [1.1 排序规则](#11-排序规则)
    - [1.2 单列排序](#12-单列排序)
    - [1.3 多列排序](#13-多列排序)
  - [2. 分页](#2-分页)
    - [2.1 背景](#21-背景)
    - [2.2 实现规则](#22-实现规则)
    - [2.3 拓展](#23-拓展)
- [第 6 章 多表查询](#第-6-章-多表查询)
  - [1. 一个案例引发的多表连接](#1-一个案例引发的多表连接)
    - [1.1 案例说明](#11-案例说明)
    - [1.2 笛卡尔积（或交叉连接）的理解](#12-笛卡尔积或交叉连接的理解)
    - [1.3 案例分析与问题解决](#13-案例分析与问题解决)
  - [2. 多表查询分类讲解](#2-多表查询分类讲解)
    - [2.1 分类 1：等值连接 vs 非等值连接](#21-分类-1等值连接-vs-非等值连接)
      - [2.1.1 等值连接](#211-等值连接)
      - [2.1.2 非等值连接](#212-非等值连接)
    - [2.2 分类 2：自连接 vs 非自连接](#22-分类-2自连接-vs-非自连接)
    - [2.3 分类 3：内连接 vs 外连接](#23-分类-3内连接-vs-外连接)
      - [2.3.1 SQL92：使用(+)创建连接](#231-sql92使用创建连接)
  - [3. SQL99 语法实现多表查询](#3-sql99-语法实现多表查询)
    - [3.1 基本语法](#31-基本语法)
    - [3.2 内连接(INNER JOIN)的实现](#32-内连接inner-join的实现)
    - [3.3 外连接(OUTER JOIN)的实现](#33-外连接outer-join的实现)
      - [3.3.1 左外连接(LEFT OUTER JOIN)](#331-左外连接left-outer-join)
      - [3.3.2 右外连接(RIGHT OUTER JOIN)](#332-右外连接right-outer-join)
      - [3.3.3 满外连接(FULL OUTER JOIN)](#333-满外连接full-outer-join)
  - [4. UNION 的使用](#4-union-的使用)
  - [5. 7 种 SQL JOINS 的实现](#5-7-种-sql-joins-的实现)
    - [5.7.1 代码实现](#571-代码实现)
    - [5.7.2 语法格式小结](#572-语法格式小结)
  - [6. SQL99 语法新特性](#6-sql99-语法新特性)
    - [6.1 自然连接](#61-自然连接)
    - [6.2 USING 连接](#62-using-连接)
  - [7. 章节小结](#7-章节小结)
  - [8. 附录：常用的 SQL 标准有哪些](#8-附录常用的-sql-标准有哪些)
- [第 7 章 单行函数](#第-7-章-单行函数)
  - [1. 函数的理解](#1-函数的理解)
    - [1.1 什么是函数](#11-什么是函数)
    - [1.2 不同 DBMS 函数的差异](#12-不同-dbms-函数的差异)
    - [1.3 MySQL 的内置函数及分类](#13-mysql-的内置函数及分类)
  - [2. 数值函数](#2-数值函数)
    - [2.1 基本函数](#21-基本函数)
    - [2.2 角度与弧度互换函数](#22-角度与弧度互换函数)
    - [2.3 三角函数](#23-三角函数)
    - [2.4 指数与对数](#24-指数与对数)
    - [2.5 进制间的转换](#25-进制间的转换)
  - [3. 字符串函数](#3-字符串函数)
  - [4. 日期和时间函数](#4-日期和时间函数)
    - [4.1 获取日期、时间](#41-获取日期-时间)
    - [4.2 日期与时间戳的转换](#42-日期与时间戳的转换)
    - [4.3 获取月份、星期、星期数、天数等函数](#43-获取月份-星期-星期数-天数等函数)
    - [4.4 日期的操作函数](#44-日期的操作函数)
    - [4.5 时间和秒钟转换的函数](#45-时间和秒钟转换的函数)
    - [4.6 计算日期和时间的函数](#46-计算日期和时间的函数)
    - [4.7 日期的格式化与解析](#47-日期的格式化与解析)
  - [5. 流程控制函数](#5-流程控制函数)
  - [6. 加密与解密函数](#6-加密与解密函数)
  - [7. MySQL 信息函数](#7-mysql-信息函数)
  - [8. 其他函数](#8-其他函数)
- [第 8 章 聚合函数](#第-8-章-聚合函数)
  - [1. 聚合函数介绍](#1-聚合函数介绍)
    - [1.1 AVG 和 SUM 函数](#11-avg-和-sum-函数)
    - [1.2 MIN 和 MAX 函数](#12-min-和-max-函数)
    - [1.3 COUNT 函数](#13-count-函数)
  - [2. GROUP BY](#2-group-by)
    - [2.1 基本使用](#21-基本使用)
    - [2.2 使用多个列分组](#22-使用多个列分组)
    - [2.3 GROUP BY 中使用 WITH ROLLUP](#23-group-by-中使用-with-rollup)
  - [3. HAVING](#3-having)
    - [3.1 基本使用](#31-基本使用)
    - [3.2 WHERE 和 HAVING 的对比](#32-where-和-having-的对比)
  - [4. SELECT 的执行过程](#4-select-的执行过程)
    - [4.1 查询的结构](#41-查询的结构)
    - [4.2 SELECT 执行顺序](#42-select-执行顺序)
    - [4.3 SQL 的执行原理](#43-sql-的执行原理)
- [第 9 章 子查询](#第-9-章-子查询)
  - [1. 需求分析与问题解决](#1-需求分析与问题解决)
    - [1.1 实际问题](#11-实际问题)
    - [1.2 子查询的基本使用](#12-子查询的基本使用)
    - [1.3 子查询的分类](#13-子查询的分类)
  - [2. 单行子查询](#2-单行子查询)
    - [2.1 单行比较操作符](#21-单行比较操作符)
    - [2.2 代码示例](#22-代码示例)
    - [2.3 HAVING 中的子查询](#23-having-中的子查询)
    - [2.4 CASE 中的子查询](#24-case-中的子查询)
    - [2.5 子查询中的空值问题](#25-子查询中的空值问题)
    - [2.5 非法使用子查询](#25-非法使用子查询)
  - [3. 多行子查询](#3-多行子查询)
    - [3.1 多行比较操作符](#31-多行比较操作符)
    - [3.2 代码示例](#32-代码示例)
    - [3.3 空值问题](#33-空值问题)
  - [4. 相关子查询](#4-相关子查询)
    - [4.1 相关子查询执行流程](#41-相关子查询执行流程)
    - [4.2 代码示例](#42-代码示例)
    - [4.3 EXISTS 与 NOT EXISTS 关键字](#43-exists-与-not-exists-关键字)
    - [4.4 相关更新](#44-相关更新)
    - [4.4 相关删除](#44-相关删除)
  - [5. 抛一个思考题](#5-抛一个思考题)

<!-- /code_chunk_output -->

# 第 0 章 写在前面

## 1. MySQL 数据库基础篇大纲

**MySQL 数据库基础篇分为 5 个篇章：**

### 1.1 数据库概述与 MySQL 安装篇

- 第 1 章：数据库概述

- 第 2 章：MySQL 环境搭建

### 1.2 SQL 之 SELECT 使用篇

- 第 3 章：基本的 SELECT 语句

- 第 4 章：运算符

- 第 5 章：排序与分页

- 第 6 章：多表查询

- 第 7 章：单行函数

- 第 8 章：聚合函数

- 第 9 章：子查询

### 1.3 SQL 之 DDL、DML、DCL 使用篇

- 第 10 章：创建和管理表

- 第 11 章：数据处理之增删改

- 第 12 章：MySQL 数据类型精讲

- 第 13 章：约束

### 1.4 其它数据库对象篇

- 第 14 章：视图

- 第 15 章：存储过程与函数

- 第 16 章：变量、流程控制与游标

- 第 17 章：触发器

### 1.5 MySQL8 新特性篇

- 第 18 章：MySQL8 其它新特性

## 2. MySQL 高级特性篇大纲

**MySQL 高级特性分为 4 个篇章：**

### 2.1 MySQL 架构篇

- 第 1 章：Linux 下 MySQL 的安装与使用

- 第 2 章：MySQL 的数据目录

- 第 3 章：用户与权限管理

- 第 4 章：逻辑架构

- 第 5 章：存储引擎

- 第 6 章：InnoDB 数据页结构

### 2.2 索引及调优篇

- 第 7 章：索引

- 第 8 章：性能分析工具的使用

- 第 9 章：索引优化与 SQL 优化

- 第 10 章：数据库的设计规范

- 第 11 章：数据库其他调优策略

### 2.3 事务篇

- 第 12 章：事务基础知识

- 第 13 章：MySQL 事务日志

- 第 14 章：锁

- 第 15 章：多版本并发控制(MVCC)

### 2.4 日志与备份篇

- 第 16 章：其它数据库日志

- 第 17 章：主从复制

- 第 18 章：数据库备份与恢复

## 3. MySQL 高手是怎样炼成的

> 针对开发工程师、数据库管理员 DBA(Database Administrator)、运维

- mysql 服务器的安装配置

- SQL 编程(自定义函数、存储过程、触发器、定时任务)

- 数据库索引建立

- SQL 语句优化

- 数据库内部结构和原理

- 数据库的性能监控分析与系统优化

- 各种参数常量设定

- 数据库建模优化

- 主从复制

- 分布式架构搭建、垂直切割和水平切割

- MyCat

- 数据迁移

- 容灾备份和恢复

- 对开源数据库进行二次开发

> **数据库就像一棵常青的技能树**，不管是普通开发还是首席架构、首席技术官 CTO(Chief Technology Officer) 都能够从中汲取足够的技术养料。
>
> **普通开发**往往积累单点技术、比如 CRUD、锁类型、索引的数据结构...而对于**技术骨干、架构师**则往往需要对底层原理吃透，数据库事务 ACID 是如何实现的？何时命中索引、何时不能，为什么？分布式场景下数据库怎么优化才能保持高性能？
>
> 说白了，知道怎么用是一方面，知道为什么则是更为**稀缺的能力**。

很多技术专家在总结程序员核心能力的时候都会提到至关重要的一点：**精通数据库。精通意味着：**

> 第一，形成知识网，更灵活地应对突发问题；
>
> 第二，底层原理要懂，懂了才能更自由地应对复杂多变的业务场景。

## 4. 本套课程适合人群

1、MySQL 数据库初学者。建议按照顺序从套课程的“基础篇”开始学习。

2、从事后台开发(Java、Python、GO、PHP 等)、MySQL 开发 1~3 年的开发人员和运维人员。建议选择“基础篇”部分内容学习，或者跳过“基础篇”，直接从“高级特性篇”开始学习。

3、有资历的 MySQL DBA。本课程可以作为“案头书”。在解决问题时，如果记不清某些概念或者细节比较模糊，则可以拿来参考。

## 5. 希望你能获取的

先说一个笑话。这个笑话是我从万维钢的专栏里看到的。

三个逻辑学家走进酒吧，酒保问他们，三位都喝啤酒吗？
第一个逻辑学家说，我不知道。
第二个逻辑学家说，我不知道。
第三个逻辑学家说，是的。

对于知识，是需要`认真`和`讲究逻辑`的。希望这份认真、严谨你在课程的每个细节都能体会到。希望通过这套课程的系统性训练，你也能感受到这种思维方式的美，最终也能获得这种思维方式。

`具备优秀的思维能力`才是在未来可以迁移的能力，如果只是学习一些命令，则很快会过时，`思维能力`和`学习能力`的提升才是不会变的东西。

# 第 1 章 数据库概述

## 1. 为什么要使用数据库

- 持久化(persistence)：**把数据保存到可掉电式存储设备中以供之后使用**。大多数情况下，特别是企业级应用，**数据持久化意味着将内存中的数据保存到硬盘上加以”固化”**，而持久化的实现过程大多通过各种关系数据库来完成。
- 持久化的主要作用是**将内存中的数据存储在关系型数据库中**，当然也可以存储在磁盘文件、XML 数据文件中。

![为什么要使用数据库](https://img-blog.csdnimg.cn/e96a15f36d3340cfa947f96d61654f07.png)

- 生活中的例子：

  - QQ 消息列表的数据存储。

## 2. 数据库与数据库管理系统

### 2.1 数据库的相关概念

| **DB：数据库（Database）**                                                                                                               |
| ---------------------------------------------------------------------------------------------------------------------------------------- |
| 即存储数据的“仓库”，其本质是一个文件系统。它保存了一系列有组织的数据。                                                                   |
| **DBMS：数据库管理系统（Database Management System）**                                                                                   |
| 是一种操纵和管理数据库的大型软件，用于建立、使用和维护数据库，对数据库进行统一管理和控制。用户通过数据库管理系统访问数据库中表内的数据。 |
| **SQL：结构化查询语言（Structured Query Language）**                                                                                     |
| 专门用来与数据库通信的语言。                                                                                                             |

### 2.2 数据库与数据库管理系统的关系

数据库管理系统(DBMS)可以管理多个数据库，一般开发人员会针对每一个应用创建一个数据库。为保存应用中实体的数据，一般会在数据库创建多个表，以保存程序中实体用户的数据。

数据库管理系统、数据库和表的关系如图所示：

![数据库与数据库管理系统的关系](https://img-blog.csdnimg.cn/111d7d834b9148c696dbc0207e4a74de.png)

![数据库与数据库管理系统的关系](https://img-blog.csdnimg.cn/511e8acddbf34066a61bfbc5b97d3da3.png)

### 2.3 常见的数据库管理系统排名(DBMS)

目前互联网上常见的数据库管理软件有 Oracle、MySQL、MS SQL Server、DB2、PostgreSQL、Access、Sybase、Informix 这几种。以下是 2021 年**DB-Engines Ranking** 对各数据库受欢迎程度进行调查后的统计结果：（ 查看数据库最新排名：https://db-engines.com/en/ranking ）

![常见的数据库管理系统排名(DBMS)](https://img-blog.csdnimg.cn/c8d48aa31861450cb6149d006b2c0919.png)

……

![常见的数据库管理系统排名(DBMS)](https://img-blog.csdnimg.cn/eaab6c4893814b8598258551108fea2d.png)

对应的走势图：（ https://db-engines.com/en/ranking_trend ）

![常见的数据库管理系统排名(DBMS)](https://img-blog.csdnimg.cn/19bfa6cbacf14caa9146d2833e9f16ab.png)

### 2.4 常见的数据库介绍

**Oracle**

1979 年，Oracle 2 诞生，它是第一个商用的 RDBMS（关系型数据库管理系统）。随着 Oracle 软件的名气越来越大，公司也改名叫 Oracle 公司。

2007 年，总计 85 亿美金收购 BEA Systems。

2009 年，总计 74 亿美金收购 SUN。此前的 2008 年，SUN 以 10 亿美金收购 MySQL。意味着 Oracle 同时拥有了 MySQL 的管理权，至此 Oracle 在数据库领域中成为绝对的领导者。

2013 年，甲骨文超越 IBM，成为继 Microsoft 后全球第二大软件公司。

如今 Oracle 的年收入达到了 400 亿美金，足以证明商用（收费）数据库软件的价值。

**SQL Server**

SQL Server 是微软开发的大型商业数据库，诞生于 1989 年。C#、.net 等语言常使用，与 WinNT 完全集成，也可以很好地与 Microsoft BackOffice 产品集成。

**DB2**

IBM 公司的数据库产品,收费的。常应用在银行系统中。

**PostgreSQL**

PostgreSQL 的稳定性极强，最符合 SQL 标准，开放源码，具备商业级 DBMS 质量。PG 对数据量大的文本以及 SQL 处理较快。

**SyBase**

已经淡出历史舞台。提供了一个非常专业数据建模的工具 PowerDesigner。

**SQLite**

嵌入式的小型数据库，应用在手机端。 零配置，SQlite3 不用安装，不用配置，不用启动，关闭或者配置数据库实例。当系统崩溃后不用做任何恢复操作，再下次使用数据库的时候自动恢复。

**informix**

IBM 公司出品，取自 Information 和 Unix 的结合，它是第一个被移植到 Linux 上的商业数据库产品。仅运行于 unix/linux 平台，命令行操作。 性能较高，支持集群，适应于安全性要求极高的系统，尤其是银行，证券系统的应用。

## 3. MySQL 介绍

![MySQL 介绍](https://img-blog.csdnimg.cn/a4cec74736534d9286c4a0262cd86156.png)

### 3.1 概述

- MySQL 是一个`开放源代码的关系型数据库管理系统`，由瑞典 MySQL AB（创始人 Michael Widenius）公司 1995 年开发，迅速成为开源数据库的 No.1。

- 2008 被`Sun`收购（10 亿美金），2009 年 Sun 被`Oracle`收购。`MariaDB`应运而生。（MySQL 的创造者担心 MySQL 有闭源的风险，因此创建了 MySQL 的分支项目 MariaDB）

- MySQL6.x 版本之后分为`社区版`和`商业版`。

- MySQL 是一种关联数据库管理系统，将数据保存在不同的表中，而不是将所有数据放在一个大仓库内，这样就增加了速度并提高了灵活性。

- MySQL 是开源的，所以你不需要支付额外的费用。

- MySQL 是可以定制的，采用了`GPL（GNU General Public License）`协议，你可以修改源码来开发自己的 MySQL 系统。

- MySQL 支持大型的数据库。可以处理拥有上千万条记录的大型数据库。

- MySQL 支持大型数据库，支持 5000 万条记录的数据仓库，32 位系统表文件最大可支持`4GB`，64 位系统支持最大的表文件为`8TB`。

- MySQL 使用`标准的SQL数据语言`形式。

- MySQL 可以允许运行于多个系统上，并且支持多种语言。这些编程语言包括 C、C++、Python、Java、Perl、PHP 和 Ruby 等。

### 3.2 MySQL 发展史重大事件

MySQL 的历史就是整个互联网的发展史。互联网业务从社交领域、电商领域到金融领域的发展，推动着应用对数据库的需求提升，对传统的数据库服务能力提出了挑战。高并发、高性能、高可用、轻资源、易维护、易扩展的需求，促进了 MySQL 的长足发展。

![MySQL 发展史重大事件](https://img-blog.csdnimg.cn/9ef40aa9cd5744a7884a45a253c41c85.png)

### 1.4 关于 MySQL 8.0

`MySQL从5.7版本直接跳跃发布了8.0版本`，可见这是一个令人兴奋的里程碑版本。MySQL 8 版本在功能上做了显著的改进与增强，开发者对 MySQL 的源代码进行了重构，最突出的一点是多 MySQL Optimizer 优化器进行了改进。不仅在速度上得到了改善，还为用户带来了更好的性能和更棒的体验。

### 1.5 Why choose MySQL?

![Why choose MySQL?](https://img-blog.csdnimg.cn/3f3c372c91264ad596634f3248ab0aec.png)

为什么如此多的厂商要选用 MySQL？大概总结的原因主要有以下几点：

1. 开放源代码，使用成本低。

2. 性能卓越，服务稳定。

3. 软件体积小，使用简单，并且易于维护。

4. 历史悠久，社区用户非常活跃，遇到问题可以寻求帮助。

5. 许多互联网公司在用，经过了时间的验证。

### 1.6 Oracle vs MySQL

Oracle 更适合大型跨国企业的使用，因为他们对费用不敏感，但是对性能要求以及安全性有更高的要求。

MySQL 由于其**体积小、速度快、总体拥有成本低，可处理上千万条记录的大型数据库，尤其是开放源码这一特点，使得很多互联网公司、中小型网站选择了 MySQL 作为网站数据库**（Facebook，Twitter，YouTube，阿里巴巴/蚂蚁金服，去哪儿，美团外卖，腾讯）。

## 4. RDBMS 与 非 RDBMS

从排名中我们能看出来，关系型数据库绝对是 DBMS 的主流，其中使用最多的 DBMS 分别是 Oracle、MySQL 和 SQL Server。这些都是关系型数据库（RDBMS）。

### 4.1 关系型数据库(RDBMS)

#### 4.1.1 实质

- 这种类型的数据库是`最古老`的数据库类型，关系型数据库模型是把复杂的数据结构归结为简单的`二元关系`（即二维表格形式）。

- 关系型数据库以`行(row)`和`列(column)`的形式存储数据，以便于用户理解。这一系列的行和列被称为`表(table)`，一组表组成了一个库(database)。

- 表与表之间的数据记录有关系(relationship)。现实世界中的各种实体以及实体之间的各种联系均用`关系模型`来表示。关系型数据库，就是建立在`关系模型`基础上的数据库。

- SQL 就是关系型数据库的查询语言。

  ![关系型数据库(RDBMS)](https://img-blog.csdnimg.cn/2ede3ce9a1d342278a5fe493e00fc9a1.png)

#### 4.1.2 优势

- **复杂查询**

  可以用 SQL 语句方便的在一个表以及多个表之间做非常复杂的数据查询。

- **事务支持**

  使得对于安全性能很高的数据访问要求得以实现。

### 4.2 非关系型数据库(非 RDBMS)

#### 4.2.1 介绍

**非关系型数据库**，可看成传统关系型数据库的功能`阉割版本`，基于键值对存储数据，不需要经过 SQL 层的解析，`性能非常高`。同时，通过减少不常用的功能，进一步提高性能。

目前基本上大部分主流的非关系型数据库都是免费的。

#### 4.2.2 有哪些非关系型数据库

相比于 SQL，NoSQL 泛指非关系型数据库，包括了榜单上的键值型数据库、文档型数据库、搜索引擎和列存储等，除此以外还包括图形数据库。也只有用 NoSQL 一词才能将这些技术囊括进来。

**键值型数据库**

键值型数据库通过 Key-Value 键值的方式来存储数据，其中 Key 和 Value 可以是简单的对象，也可以是复杂的对象。Key 作为唯一的标识符，优点是查找速度快，在这方面明显优于关系型数据库，缺点是无法像关系型数据库一样使用条件过滤（比如 WHERE），如果你不知道去哪里找数据，就要遍历所有的键，这就会消耗大量的计算。

键值型数据库典型的使用场景是作为`内存缓存`。`Redis `是最流行的键值型数据库。

![键值型数据库](https://img-blog.csdnimg.cn/04dd3617a450431885915bf4e3069eb4.png)

**文档型数据库**

此类数据库可存放并获取文档，可以是 XML、JSON 等格式。在数据库中文档作为处理信息的基本单位，一个文档就相当于一条记录。文档数据库所存放的文档，就相当于键值数据库所存放的“值”。MongoDB 是最流行的文档型数据库。此外，还有 CouchDB 等。

**搜索引擎数据库**

虽然关系型数据库采用了索引提升检索效率，但是针对全文索引效率却较低。搜索引擎数据库是应用在搜索引擎领域的数据存储形式，由于搜索引擎会爬取大量的数据，并以特定的格式进行存储，这样在检索的时候才能保证性能最优。核心原理是“倒排索引”。

典型产品：Solr、Elasticsearch、sqlunk 等。

**列式数据库**

列式数据库是相对于行式存储的数据库，Oracle、MySQL、SQL Server 等数据库都是采用的行式存储（Row-based），而列式数据库是将数据按照列存储到数据库中，这样做的好处是可以大量降低系统的 I/O，适合于分布式文件系统，不足在于功能相对有限。典型产品：HBase 等。

![列式数据库](https://img-blog.csdnimg.cn/f624fb2c87674a7fa489ae743fc2ab00.png)

**图形数据库**

图形数据库，利用了图这种数据结构存储了实体（对象）之间的关系。图形数据库最典型的例子就是社交网络中人与人的关系，数据模型主要是以节点和边（关系）来实现，特点在于能高效地解决复杂的关系问题。

图形数据库顾名思义，就是一种存储图形关系的数据库。它利用了图这种数据结构存储了实体（对象）之间的关系。关系型数据用于存储明确关系的数据，但对于复杂关系的数据存储却有些力不从心。如社交网络中人物之间的关系，如果用关系型数据库则非常复杂，用图形数据库将非常简单。典型产品：Neo4J、InfoGrid 等。

![图形数据库](https://img-blog.csdnimg.cn/0368a2f18a764281aef0e6a23114a6e8.png)

#### 4.2.3 NoSQL 的演变

由于 SQL 一直称霸 DBMS，因此许多人在思考是否有一种数据库技术能远离 SQL，于是 NoSQL 诞生了，但是随着发展却发现越来越离不开 SQL。到目前为止 NoSQL 阵营中的 DBMS 都会有实现类似 SQL 的功能。下面是“NoSQL”这个名词在不同时期的诠释，从这些释义的变化中可以看出 `NoSQL 功能的演变`：

1970：NoSQL = We have no SQL

1980：NoSQL = Know SQL

2000：NoSQL = No SQL!

2005：NoSQL = Not only SQL

2013：NoSQL = No, SQL!

NoSQL 对 SQL 做出了很好的补充，比如实际开发中，有很多业务需求，其实并不需要完整的关系型数据库功能，非关系型数据库的功能就足够使用了。这种情况下，使用`性能更高`、`成本更低`的非关系型数据库当然是更明智的选择。比如：日志收集、排行榜、定时器等。

### 4.3 小结

NoSQL 的分类很多，即便如此，在 DBMS 排名中，还是 SQL 阵营的比重更大，影响力前 5 的 DBMS 中有 4 个是关系型数据库，而排名前 20 的 DBMS 中也有 12 个是关系型数据库。所以说，掌握 SQL 是非常有必要的。整套课程将围绕 SQL 展开。

## 5. 关系型数据库设计规则

- 关系型数据库的典型数据结构就是`数据表`，这些数据表的组成都是结构化的（Structured）。

- 将数据放到表中，表再放到库中。

- 一个数据库中可以有多个表，每个表都有一个名字，用来标识自己。表名具有唯一性。

- 表具有一些特性，这些特性定义了数据在表中如何存储，类似 Java 和 Python 中 “类”的设计。

### 5.1 表、记录、字段

- E-R（entity-relationship，实体-联系）模型中有三个主要概念是：`实体集`、`属性`、`联系集`。

- 一个实体集（class）对应于数据库中的一个表（table），一个实体（instance）则对应于数据库表中的一行（row），也称为一条记录（record）。一个属性（attribute）对应于数据库表中的一列（column），也称为一个字段（field）。

![表、记录、字段](https://img-blog.csdnimg.cn/efcacd9a7bd9415ca5f2709060e3791d.png)

> ORM 思想 (Object Relational Mapping)体现：
>
> 数据库中的一个表 <---> Java 或 Python 中的一个类
> 表中的一条数据 <---> 类中的一个对象、实体
> 表中的一个列 <----> 类中的一个字段、属性(field)

### 5.2 表的关联关系

- 表与表之间的数据记录有关系(relationship)。现实世界中的各种实体以及实体之间的各种联系均用关系模型来表示。

- 四种：一对一关联、一对多关联、多对多关联、自我引用。

#### 5.2.1 一对一关联（one-to-one）

- 在实际的开发中应用不多，因为一对一可以创建成一张表。

- 举例：设计`学生表`：学号、姓名、手机号码、班级、系别、身份证号码、家庭住址、籍贯、紧急联系人、……

  - 拆为两个表：两个表的记录是一一对应关系。

  - `基础信息表`（常用信息）：学号、姓名、手机号码、班级、系别。

  - `档案信息表`（不常用信息）：学号、身份证号码、家庭住址、籍贯、紧急联系人、……

- 两种建表原则：

  - 外键唯一：主表的主键和从表的外键（唯一），形成主外键关系，外键唯一。

  - 外键是主键：主表的主键和从表的主键，形成主外键关系。

![一对一关联（one-to-one）](https://img-blog.csdnimg.cn/8b793d6a1c8d4d71a04ef7267bef8f13.png)

#### 5.2.2 一对多关系（one-to-many）

- 常见实例场景：`客户表和订单表`，`分类表和商品表`，`部门表和员工表`。

- 举例：

  - 员工表：编号、姓名、……、所属部门。

  - 部门表：编号、名称、简介。

- 一对多建表原则：在从表(多方)创建一个字段，字段作为外键指向主表(一方)的主键。

![一对多关系（one-to-many）](https://img-blog.csdnimg.cn/2b5ea53361314ffe8287f2700cb52394.png)

![一对多关系（one-to-many）](https://img-blog.csdnimg.cn/77e50d68867648cc95562d3974b43c2f.png)

![一对多关系（one-to-many）](https://img-blog.csdnimg.cn/9b8ce4a8ba644a2da1887693f8e1a1c8.png)

#### 5.2.3 多对多（many-to-many）

要表示多对多关系，必须创建第三个表，该表通常称为`联接表`，它将多对多关系划分为两个一对多关系。将这两个表的主键都插入到第三个表中。

![多对多（many-to-many）](https://img-blog.csdnimg.cn/184ba3539efd4c1499680eaa051af97a.png)

- **举例 1：学生-课程**

  - `学生信息表`：一行代表一个学生的信息（学号、姓名、手机号码、班级、系别……）。

  - `课程信息表`：一行代表一个课程的信息（课程编号、授课老师、简介……）。

  - `选课信息表`：一个学生可以选多门课，一门课可以被多个学生选择。

  > 学号 &nbsp;&nbsp; 课程编号
  >
  > 1 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 1001
  > 2 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 1001
  > 1 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 1002

- **举例 2：产品-订单**

  “订单”表和“产品”表有一种多对多的关系，这种关系是通过与“订单明细”表建立两个一对多关系来定义的。一个订单可以有多个产品，每个产品可以出现在多个订单中。

  - `产品表`：“产品”表中的每条记录表示一个产品。

  - `订单表`：“订单”表中的每条记录表示一个订单。

  - `订单明细表`：每个产品可以与“订单”表中的多条记录对应，即出现在多个订单中。一个订单可以与“产品”表中的多条记录对应，即包含多个产品。

  ![举例 2：产品-订单](https://img-blog.csdnimg.cn/6fb3be0415d94695968fd6ed8bd87497.png)

- **举例 3：用户-角色**

  - 多对多关系建表原则：需要创建第三张表，中间表中至少两个字段，这两个字段分别作为外键指向各自一方的主键。

  ![举例 3：用户-角色](https://img-blog.csdnimg.cn/d5174d462b8d43c5b28299734b7ad520.png)

#### 5.3.4 自我引用(Self reference)

![自我引用(Self reference)](https://img-blog.csdnimg.cn/3a26214cc0c54ee2ab73f708ca8fe769.png)

# 第 2 章 MySQL 环境搭建

## 1. MySQL 的卸载

### 1.1 步骤 1：停止 MySQL 服务

在卸载之前，先停止 MySQL8.0 的服务。按键盘上的“Ctrl + Alt + Delete”组合键，打开“任务管理器”对话框，可以在“服务”列表找到“MySQL8.0”的服务，如果现在“正在运行”状态，可以右键单击服务，选择“停止”选项停止 MySQL8.0 的服务。

### 1.2 步骤 2：软件的卸载

**方式 1：通过控制面板方式**

卸载 MySQL8.0 的程序可以和其他桌面应用程序一样直接在“控制面板”选择“卸载程序”，并在程序列表中找到 MySQL8.0 服务器程序，直接双击卸载即可。这种方式删除，数据目录下的数据不会跟着删除。

**方式 2：通过电脑管家等软件卸载**

略

**方式 3：通过安装包提供的卸载功能卸载**

你也可以通过安装向导程序进行 MySQL8.0 服务器程序的卸载。

① 再次双击下载的 mysql-installer-community-8.0.31.0.msi 文件，打开安装向导。安装向导会自动检测已安装的 MySQL 服务器程序。

② 选择要卸载的 MySQL 服务器程序，单击“Remove”（移除），即可进行卸载。

③ 单击“Next”（下一步）按钮，确认卸载。

④ 弹出是否同时移除数据目录选择窗口。如果想要同时删除 MySQL 服务器中的数据，则勾选“Remove the data directory”。

⑤ 执行卸载。单击“Execute”（执行）按钮进行卸载。

⑥ 完成卸载。单击“Finish”（完成）按钮即可。如果想要同时卸载 MySQL8.0 的安装向导程序，勾选“Yes，Uninstall MySQL Installer”即可。

### 1.3 步骤 3：残余文件的清理

如果再次安装不成功，可以卸载后对残余文件进行清理后再安装。

（1）服务目录：mysql 服务的安装目录

（2）数据目录：默认在 C:\ProgramData\MySQL

如果自己单独指定过数据目录，就找到自己的数据目录进行删除即可。

> 注意：请在卸载前做好数据备份。
>
> 在操作完以后，需要重启计算机，然后进行安装即可。**如果仍然安装失败，需要继续操作如下步骤 4。**

### 1.4 步骤 4：清理注册表（选做）

如果前几步做了，再次安装还是失败，那么可以清理注册表。

如何打开注册表编辑器：在系统的搜索框中输入`regedit`。

> HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Services\Eventlog\Application\MySQL 服务 目录删除
>
> HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Services\MySQL 服务 目录删除
>
> HKEY_LOCAL_MACHINE\SYSTEM\ControlSet002\Services\Eventlog\Application\MySQL 服务 目录删除
>
> HKEY_LOCAL_MACHINE\SYSTEM\ControlSet002\Services\MySQL 服务 目录删除
>
> HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\Eventlog\Application\MySQL 服务目录删除
>
> HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\MySQL 服务删除
>
> 注册表中的 ControlSet001,ControlSet002,不一定是 001 和 002,可能是 ControlSet005、006 之类

### 1.5 步骤 5：删除环境变量配置

找到 path 环境变量，将其中关于 mysql 的环境变量删除，**切记不要全部删除。**

例如：删除 `D:\Program Files\CodePrograms\MySQL\MySQL Server 8.0\bin` 这个部分。

## 2. MySQL 的下载、安装、配置

### 2.1 MySQL 的 4 大版本

> - **MySQL Community Server 社区版本**，开源免费，自由下载，但不提供官方技术支持，适用于大多数普通用户。
>
> - **MySQL Enterprise Edition 企业版本**，需付费，不能在线下载，可以试用 30 天。提供了更多的功能和更完备的技术支持，更适合于对数据库的功能和可靠性要求较高的企业客户。
>
> - **MySQL Cluster 集群版**，开源免费。用于架设集群服务器，可将几个 MySQL Server 封装成一个 Server。需要在社区版或企业版的基础上使用。
>
> - **MySQL Cluster CGE 高级集群版**，需付费。
>
> - 目前最新版本为`8.0.31`，发布时间`2022年9月26日`。此前，8.0.0 在 2016.9.12 日就发布了。
>
> - 本课程中使用`8.0.31 版本`。

此外，官方还提供了`MySQL Workbench`（GUITOOL）一款专为 MySQL 设计的`图形界面管理工具`。
MySQLWorkbench 又分为两个版本，分别是`社区版`（MySQL Workbench OSS）、`商用版`（MySQL WorkbenchSE）。

### 2.2 软件的下载

**1. 下载地址**

官网：[https://www.mysql.com](https://www.mysql.com/)

**2. 打开官网，点击 DOWNLOADS**

然后，点击`MySQL Community(GPL) Downloads`。

![打开官网，点击 DOWNLOADS](https://img-blog.csdnimg.cn/5ad4f36143f04339a55671daeef36c8b.png)

**3. 点击 MySQL Community Server**

![点击 MySQL Community Server](https://img-blog.csdnimg.cn/c8672c7958894bc8b467538877c53f9f.png)

**4. 在 General Availability(GA) Releases 中选择适合的版本**

Windows 平台下提供两种安装文件：MySQL 二进制分发版（.msi 安装文件）和免安装版（.zip 压缩文件）。一般来讲，应当使用二进制分发版，因为该版本提供了图形化的安装向导过程，比其他的分发版使用起来要简单，不再需要其他工具启动就可以运行 MySQL。

- 这里在 Windows 系统下推荐下载`MSI安装程序`；点击`Go to Download Page`进行下载即可。

  ![在 General Availability(GA) Releases 中选择适合的版本](https://img-blog.csdnimg.cn/9ffb85afd67e40709beedeefafc5c6b5.png)

  ![在 General Availability(GA) Releases 中选择适合的版本](https://img-blog.csdnimg.cn/37c49f42873b4382b226fa7a5c5133b1.png)

- Windows 下的 MySQL8.0 安装有两种安装程序

  - `mysql-installer-web-community-8.0.34.0.msi` 下载程序大小：2.4M；安装时需要联网安装组件。

  - `mysql-installer-community-8.0.34.0.msi` 下载程序大小：331.3M；安装时离线安装即可。**推荐。**

- 如果安装 MySQL5.7 版本的话，选择`Select Version`，接着选择 MySQL5.7 的相应版本即可。这里下载最近期的 MySQL5.7.34 版本。

  ![在 General Availability(GA) Releases 中选择适合的版本](https://img-blog.csdnimg.cn/7f9bc01aa0494275a0a831194dbf6556.png)

  ![在 General Availability(GA) Releases 中选择适合的版本](https://img-blog.csdnimg.cn/8588b15301b04071a9bc67d6fd7ddd9a.png)

### 2.3 MySQL8.0 版本的安装

MySQL 下载完成后，找到下载文件，双击进行安装，具体操作步骤如下。

步骤 1：双击下载的 mysql-installer-community-8.0.31.0.msi 文件，打开安装向导。

步骤 2：打开“Choosing a Setup Type”（选择安装类型）窗口，在其中列出了 5 种安装类型，分别是 Developer Default（默认安装类型）、Server only（仅作为服务器）、Client only（仅作为客户端）、Full（完全安装）、Custom（自定义安装）。这里选择“Custom（自定义安装）”类型按钮，单击“Next(下一步)”按钮。

步骤 3：打开“Select Products” （选择产品）窗口，可以定制需要安装的产品清单。例如，选择“MySQL Server 8.0.31-X64”后，单击“→”添加按钮，即可选择安装 MySQL 服务器。采用通用的方法，可以添加其他你需要安装的产品。

此时如果直接“Next”（下一步），则产品的安装路径是默认的。如果想要自定义安装目录，则可以选中对应的产品，然后在下面会出现“Advanced Options”（高级选项）的超链接。

单击“Advanced Options”（高级选项）则会弹出安装目录的选择窗口，此时你可以分别设置 MySQL 的服务程序安装目录和数据存储目录。如果不设置，默认分别在 C 盘的 Program Files 目录和 ProgramData 目录（这是一个隐藏目录）。如果自定义安装目录，请避免“中文”目录。另外，建议服务目录和数据目录分开存放。

步骤 4：在上一步选择好要安装的产品之后，单击“Next”（下一步）进入确认窗口。单击“Execute”（执行）按钮开始安装。

步骤 5：安装完成后在“Status”（状态）列表下将显示“Complete”（安装完成）。

### 2.4 配置 MySQL8.0

MySQL 安装之后，需要对服务器进行配置。具体的配置步骤如下。

步骤 1：在上一个小节的最后一步，单击“Next”（下一步）按钮，就可以进入产品配置窗口。

步骤 2：单击“Next”（下一步）按钮，进入 MySQL 服务器类型配置窗口。端口号一般选择默认端口号 3306。

其中，“Config Type”选项用于设置服务器的类型。单击该选项右侧的下三角按钮，即可查看 3 个选项。

- `Development Machine（开发机器）`：该选项代表典型个人用桌面工作站。此时机器上需要运行多个应用程序，那么 MySQL 服务器将占用最少的系统资源。

- `Server Machine（服务器）`：该选项代表服务器，MySQL 服务器可以同其他服务器应用程序一起运行，例如 Web 服务器等。MySQL 服务器配置成适当比例的系统资源。

- `Dedicated Machine（专用服务器）`：该选项代表只运行 MySQL 服务的服务器。MySQL 服务器配置成使用所有可用系统资源。

步骤 3：单击“Next”（下一步）按钮，打开设置授权方式窗口。其中，上面的选项是 MySQL8.0 提供的新的授权方式，采用 SHA256 基础的密码加密方法；下面的选项是传统授权方法（保留 5.x 版本兼容性）。

步骤 4：单击“Next”（下一步）按钮，打开设置服务器 root 超级管理员的密码窗口，需要输入两次同样的登录密码。也可以通过“Add User”添加其他用户，添加其他用户时，需要指定用户名、允许该用户名在哪台/哪些主机上登录，还可以指定用户角色等。此处暂不添加用户，用户管理在 MySQL 高级特性篇中讲解。

步骤 5：单击“Next”（下一步）按钮，打开设置服务器名称窗口。该服务名会出现在 Windows 服务列表中，也可以在命令行窗口中使用该服务名进行启动和停止服务。本书将服务名设置为“MySQL80”。如果希望开机自启动服务，也可以勾选“Start the MySQL Server at System Startup”选项（推荐）。

下面是选择以什么方式运行服务？可以选择“Standard System Account”(标准系统用户)或者“Custom User”(自定义用户)中的一个。这里推荐前者。

步骤 6：单击“Next”（下一步）按钮，打开确认设置服务器窗口，单击“Execute”（执行）按钮。

步骤 7：完成配置。单击“Finish”（完成）按钮，即可完成服务器的配置。

步骤 8：如果还有其他产品需要配置，可以选择其他产品，然后继续配置。如果没有，直接选择“Next”（下一步），直接完成整个安装和配置过程。

步骤 9：结束安装和配置。

### 2.5 配置 MySQL8.0 环境变量

如果不配置 MySQL 环境变量，就不能在命令行直接输入 MySQL 登录命令。下面说如何配置 MySQL 的环境变量：

步骤 1：在桌面上右击【此电脑】图标，在弹出的快捷菜单中选择【属性】菜单命令。

步骤 2：打开【系统】窗口，单击【高级系统设置】链接。

步骤 3：打开【系统属性】对话框，选择【高级】选项卡，然后单击【环境变量】按钮。

步骤 4：打开【环境变量】对话框，在系统变量列表中选择 path 变量。

步骤 5：单击【编辑】按钮，在【编辑环境变量】对话框中，将 MySQL 应用程序的 bin 目录（D:\Program Files\CodePrograms\MySQL\MySQL Server 8.0\bin）添加到变量值中，用分号将其与其他路径分隔开。

步骤 6：添加完成之后，单击【确定】按钮，这样就完成了配置 path 变量的操作，然后就可以直接输入 MySQL 命令来登录数据库了。

### 2.6 MySQL5.7 版本的安装、配置

- **安装**

  此版本的安装过程与上述过程除了版本号不同之外，其它环节都是相同的。所以这里省略了 MySQL5.7.34 版本的安装截图。

- **配置**

  配置环节与 MySQL8.0 版本确有细微不同。大部分情况下直接选择“Next”即可，不影响整理使用。

  这里配置 MySQL5.7 时，重点强调：**与前面安装好的 MySQL8.0 不能使用相同的端口号。**

### 2.7 安装失败问题

MySQL 的安装和配置是一件非常简单的事，但是在操作过程中也可能出现问题，特别是初学者。

**问题 1：无法打开 MySQL8.0 软件安装包或者安装过程中失败，如何解决？**

在运行 MySQL8.0 软件安装包之前，用户需要确保系统中已经安装了 .Net Framework 相关软件，如果缺少此软件，将不能正常地安装 MySQL8.0 软件。

解决方案：到这个地址 https://www.microsoft.com/en-us/download/details.aspx?id=42642 下载 Microsoft .NET Framework 4.5 并安装后，再去安装 MySQL。

另外，还要确保 Windows Installer 正常安装。windows 上安装 mysql8.0 需要操作系统提前已安装好 Microsoft Visual C++ 2015-2019。

解决方案同样是，提前到微软官网 https://support.microsoft.com/en-us/topic/the-latest-supported-visual-c-downloads-2647da03-1eea-4433-9aff-95f26a218cc0 ，下载相应的环境。

**问题 2：卸载重装 MySQL 失败？**

该问题通常是因为 MySQL 卸载时，没有完全清除相关信息导致的。

解决办法是，把以前的安装目录删除。如果之前安装并未单独指定过服务安装目录，则默认安装目录是“C:\Program Files\MySQL”，彻底删除该目录。同时删除 MySQL 的 Data 目录，如果之前安装并未单独指定过数据目录，则默认安装目录是“C:\ProgramData\MySQL”，该目录一般为隐藏目录。删除后，重新安装即可。

**问题 3：如何在 Windows 系统删除之前的未卸载干净的 MySQL 服务列表？**

操作方法如下，在系统“搜索框”中输入“cmd”，按“Enter”（回车）键确认，弹出命令提示符界面。然后输入“sc delete MySQL 服务名”,按“Enter”（回车）键，就能彻底删除残余的 MySQL 服务了。

## 3. MySQL 的登录

### 3.1 服务的启动与停止

MySQL 安装完毕之后，需要启动服务器进程，不然客户端无法连接数据库。

在前面的配置过程中，已经将 MySQL 安装为 Windows 服务，并且勾选当 Windows 启动、停止时，MySQL 也自动启动、停止。

#### 3.1.1 方式 1：使用图形界面工具

- 步骤 1：打开 windows 服务

  - 方式 1：计算机（点击鼠标右键）→ 管理（点击）→ 服务和应用程序（点击）→ 服务（点击）

  - 方式 2：控制面板（点击）→ 系统和安全（点击）→ 管理工具（点击）→ 服务（点击）

  - 方式 3：任务栏（点击鼠标右键）→ 启动任务管理器（点击）→ 服务（点击）

  - 方式 4：单击【开始】菜单，在搜索框中输入“services.msc”，按 Enter 键确认

- 步骤 2：找到 MySQL80（点击鼠标右键）→ 启动或停止（点击）

#### 3.1.2 方式 2：使用命令行工具

> \# 启动 MySQL 服务命令
> net start MySQL 服务名

> \# 停止 MySQL 服务命令
> net stop MySQL 服务名

说明：

1. start 和 stop 后面的服务名应与之前配置时指定的服务名一致。

2. 如果当你输入命令后，提示“拒绝服务”，请以`系统管理员身份`打开命令提示符界面重新尝试。

### 3.2 自带客户端的登录与退出

当 MySQL 服务启动完成后，便可以通过客户端来登录 MySQL 数据库。注意：确认服务是开启的。

#### 3.2.1 登录方式 1：MySQL 自带客户端

开始菜单 → 所有程序 → MySQL → MySQL 8.0 Command Line Client

> 说明：仅限于 root 用户。

#### 3.2.2 登录方式 2：windows 命令行

- 格式：

  > mysql -h 主机名 -P 端口号 -u 用户名 -p 密码

- 举例：

  ```sql
  # 这里设置的 root 用户的密码是 520.ILY!
  mysql -h localhost -P 3306 -u root -p520.ILY!
  ```

注意：

（1）-p 与密码之间不能有空格，其他参数名与参数值之间可以有空格也可以没有空格。如：

```sh
mysql -hlocalhost -P3306 -uroot -p520.ILY!
```

（2）密码建议在下一行输入，保证安全。

```sh
mysql -h localhost -P 3306 -u root -p
Enter password:********
```

（3）客户端和服务器在同一台机器上，所以输入 localhost 或者 IP 地址 127.0.0.1。同时，因为是连接本机：-hlocalhost 就可以省略，如果端口号没有修改：-P3306 也可以省略。

简写成：

```sh
mysql -u root -p
Enter password:********
```

连接成功后，有关于 MySQL Server 服务版本的信息，还有第几次连接的 id 标识。

也可以在命令行通过以下方式获取 MySQL Server 服务版本的信息：

```sh
D:\> mysql -V
```

```sh
D:\> mysql --version
```

或**登录**后，通过以下方式查看当前版本信息：

```sh
mysql> select version();
```

#### 3.2.3 退出登录

```sh
exit
```

或

```sh
quit
```

## 4. MySQL 演示使用

### 4.1 MySQL 的使用演示

1、查看所有的数据库

```sql
show databases;
```

> “information_schema”是 MySQL 系统自带的数据库，主要保存 MySQL 数据库服务器的系统信息，比如数据库的名称、数据表的名称、字段名称、存取权限、数据文件 所在的文件夹和系统使用的文件夹，等等。
>
> “performance_schema”是 MySQL 系统自带的数据库，可以用来监控 MySQL 的各类性能指标。
>
> “sys”数据库是 MySQL 系统自带的数据库，主要作用是以一种更容易被理解的方式展示 MySQL 数据库服务器的各类性能指标，帮助系统管理员和开发人员监控 MySQL 的技术性能。
>
> “mysql”数据库保存了 MySQL 数据库服务器运行时需要的系统信息，比如数据文件夹、当前使用的字符集、约束检查信息，等等。

为什么 Workbench 里面我们只能看到“demo”和“sys”这 2 个数据库呢？

这是因为，Workbench 是图形化的管理工具，主要面向开发人 员，“demo”和“sys”这 2 个数据库已经够用了。如果有特殊需求，比如，需要监控 MySQL 数据库各项性能指标、直接操作 MySQL 数据库系统文件等，可以由 DBA 通过 SQL 语句，查看其它的系统数据库。

2、创建自己的数据库

> create database 数据库名;

```sql
# 创建 myxh 数据库，该名称不能与已经存在的数据库重名
create database myxh;
```

3、使用自己的数据库

> use 数据库名;

```sql
# 使用 myxh 数据库
use myxh;
```

说明：如果没有使用 use 语句，后面针对数据库的操作也没有加“数据名”的限定，那么会报“ERROR 1046 (3D000): No database selected”（没有选择数据库）。

使用完 use 语句之后，如果接下来的 SQL 都是针对一个数据库操作的，那就不用重复 use 了，如果要针对另一个数据库操作，那么要重新 use。

4、查看某个库的所有表格

> \# 要求前面有 use 语句
> show tables;
>
> show tables from 数据库名;

5、创建新的表格

> create table 表名称
> (
> &nbsp;&nbsp;&nbsp; 字段名 数据类型,
> &nbsp;&nbsp;&nbsp; 字段名 数据类型
> );

说明：如果是最后一个字段，后面就用加逗号，因为逗号的作用是分割每个字段。

```sql
# 创建学生表
create table student
(
    id int,

    # 名字最长不超过20个字符
    name varchar(20)
);
```

6、查看一个表的数据

> select \* from 数据库表名称;

```sql
# 查看学生表的数据
select * from student;
```

7、添加一条记录

> insert into 表名称 values(值列表);

```sql
# 添加两条记录到 student 表中
insert into student values(1,'张三');
insert into student values(2,'李四');
```

报错：

```sh
mysql> insert into student values(1,'张三');
ERROR 1366 (HY000): Incorrect string value: '\xD5\xC5\xC8\xFD' for column 'name' at row 1
mysql> insert into student values(2,'李四');
ERROR 1366 (HY000): Incorrect string value: '\xC0\xEE\xCB\xC4' for column 'name' at row 1
mysql> show create table student;
```

字符集的问题。

8、查看表的创建信息

> show create table 表名称\G

```sql
# 查看 student 表的详细创建信息
show create table student\G
```

```sh
# 结果如下
*************************** 1. row ***************************
       Table: student
Create Table: CREATE TABLE `student`
(
  `id` int(11) DEFAULT NULL,
  `name` varchar(20) DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=latin1
1 row in set (0.00 sec)
```

上面的结果显示 student 的表格的默认字符集是“latin1”不支持中文。

9、查看数据库的创建信息

> show create database 数据库名\G

```sql
# 查看 myxh 数据库的详细创建信息
show create database myxh\G
```

```sh
# 结果如下
*************************** 1. row ***************************
       Database: myxh
Create Database: CREATE DATABASE `myxh` /*!40100 DEFAULT CHARACTER SET latin1 */
1 row in set (0.00 sec)
```

上面的结果显示 myxh 数据库也不支持中文，字符集默认是 latin1。

10、删除表格

> drop table 表名称;

```sql
# 删除学生表
drop table student;
```

11、删除数据库

> drop database 数据库名;

```sql
# 删除 myxh 数据库
drop database myxh;
```

### 4.2 MySQL 的编码设置

#### 4.2.1 MySQL5.7 中

**问题再现：命令行操作 sql 乱码问题**

```sh
mysql> INSERT INTO t_stu VALUES(1,'张三','男');
ERROR 1366 (HY000): Incorrect string value: '\xD5\xC5\xC8\xFD' for column 'sname' at row 1
```

**问题解决**

步骤 1：查看编码命令

```sh
show variables like 'character_%';
show variables like 'collation_%';
```

步骤 2：修改 mysql 的数据目录下的 my.ini 配置文件

```ini
# 大概在 63 行左右，在其下添加
[mysql]
...
default-character-set=utf8  # 默认字符集

# 大概在 76 行左右，在其下添加
[mysqld]
...
character-set-server=utf8
collation-server=utf8_general_ci
```

> 注意：建议修改配置文件使用 notepad++ 等高级文本编辑器，使用记事本等软件打开修改后可能会导致文件编码修改为“含 BOM 头”的编码，从而服务重启失败。

步骤 3：重启服务

步骤 4：查看编码命令

```sh
show variables like 'character_%';
show variables like 'collation_%';
```

- 如果是 utf8 和 utf8_general_ci 的编码配置就说明对了。接着我们就可以新创建数据库、新创建数据表，接着添加包含中文的数据了。

#### 4.2.2 MySQL8.0 中

在 MySQL 8.0 版本之前，默认字符集为 latin1，utf8 字符集指向的是 utf8mb3。网站开发人员在数据库设计的时候往往会将编码修改为 utf8 字符集。如果遗忘修改默认的编码，就会出现乱码的问题。从 MySQL 8.0 开始，数据库的默认编码改为`utf8mb4`，从而避免了上述的乱码问题。

## 5. MySQL 图形化管理工具

MySQL 图形化管理工具极大地方便了数据库的操作与管理，常用的图形化管理工具有：MySQL Workbench、phpMyAdmin、Navicat Preminum、MySQLDumper、SQLyog、dbeaver、MySQL ODBC Connector。

### 5.1 工具 1. MySQL Workbench

MySQL 官方提供的图形化管理工具 MySQL Workbench 完全支持 MySQL 5.0 以上的版本。MySQL Workbench 分为社区版和商业版，社区版完全免费，而商业版则是按年收费。

MySQL Workbench 为数据库管理员、程序开发者和系统规划师提供可视化设计、模型建立、以及数据库管理功能。它包含了用于创建复杂的数据建模 ER 模型，正向和逆向数据库工程，也可以用于执行通常需要花费大量时间的、难以变更和管理的文档任务。

下载地址：http://dev.mysql.com/downloads/workbench/ 。

使用：

首先，我们点击 Windows 左下角的“开始”按钮，如果你是 Win10 系统，可以直接看到所有程序。接着，找到“MySQL”，点开，找到“MySQL Workbench 8.0 CE”。点击打开 Workbench。

左下角有个本地连接，点击，录入 Root 的密码，登录本地 MySQL 数据库服务器。

这是一个图形化的界面，我来给你介绍下这个界面。

- 上方是菜单。左上方是导航栏，这里我们可以看到 MySQL 数据库服务器里面的数据 库，包括数据表、视图、存储过程和函数；左下方是信息栏，可以显示上方选中的数据 库、数据表等对象的信息。

- 中间上方是工作区，你可以在这里写 SQL 语句，点击上方菜单栏左边的第三个运行按 钮，就可以执行工作区的 SQL 语句了。

- 中间下方是输出区，用来显示 SQL 语句的运行情况，包括什么时间开始运行的、运行的 内容、运行的输出，以及所花费的时长等信息。

好了，下面我们就用 Workbench 实际创建一个数据库，并且导入一个 Excel 数据文件， 来生成一个数据表。数据表是存储数据的载体，有了数据表以后，我们就能对数据进行操作了。

### 5.2 工具 2. Navicat

Navicat MySQL 是一个强大的 MySQL 数据库服务器管理和开发工具。它可以与任何 3.21 或以上版本的 MySQL 一起工作，支持触发器、存储过程、函数、事件、视图、管理用户等，对于新手来说易学易用。其精心设计的图形用户界面（GUI）可以让用户用一种安全简便的方式来快速方便地创建、组织、访问和共享信息。Navicat 支持中文，有免费版本提供。
下载地址：http://www.navicat.com/ 。

### 5.3 工具 3. SQLyog

SQLyog 是业界著名的 Webyog 公司出品的一款简洁高效、功能强大的图形化 MySQL 数据库管理工具。这款工具是使用 C++语言开发的。该工具可以方便地创建数据库、表、视图和索引等，还可以方便地进行插入、更新和删除等操作，同时可以方便地进行数据库、数据表的备份和还原。该工具不仅可以通过 SQL 文件进行大量文件的导入和导出，还可以导入和导出 XML、HTML 和 CSV 等多种格式的数据。
下载地址：http://www.webyog.com/ ，读者也可以搜索中文版的下载地址。

### 5.4 工具 4：dbeaver

DBeaver 是一个通用的数据库管理工具和 SQL 客户端，支持所有流行的数据库：MySQL、PostgreSQL、SQLite、Oracle、DB2、SQL Server、 Sybase、MS Access、Teradata、 Firebird、Apache Hive、Phoenix、Presto 等。DBeaver 比大多数的 SQL 管理工具要轻量，而且支持中文界面。DBeaver 社区版作为一个免费开源的产品，和其他类似的软件相比，在功能和易用性上都毫不逊色。

唯一需要注意是 DBeaver 是用 Java 编程语言开发的，所以需要拥有 JDK（Java Development ToolKit）环境。如果电脑上没有 JDK，在选择安装 DBeaver 组件时，勾选“Include Java”即可。

下载地址：https://dbeaver.io/download/

### 5.5 可能出现连接问题：

有些图形界面工具，特别是旧版本的图形界面工具，在连接 MySQL8 时出现“Authentication plugin 'caching_sha2_password' cannot be loaded”错误。

出现这个原因是 MySQL8 之前的版本中加密规则是 mysql_native_password，而在 MySQL8 之后，加密规则是 caching_sha2_password。解决问题方法有两种，第一种是升级图形界面工具版本，第二种是把 MySQL8 用户登录密码加密规则还原成 mysql_native_password。

第二种解决方案如下，用命令行登录 MySQL 数据库之后，执行如下命令修改用户密码加密规则并更新用户密码，这里修改用户名为“root@localhost”的用户密码规则为“mysql_native_password”，密码值为“520.ILY!”，如图所示。

```sql
# 使用 mysql 数据库
USE mysql;

# 修改'root'@'localhost'用户的密码规则和密码
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY '520.ILY!';

# 刷新权限
FLUSH PRIVILEGES;
```

## 6. MySQL 目录结构与源码

### 6.1 主要目录结构

| MySQL 的目录结构                             | 说明                                   |
| -------------------------------------------- | -------------------------------------- |
| bin 目录                                     | 所有 MySQL 的可执行文件。如：mysql.exe |
| MySQLInstanceConfig.exe                      | 数据库的配置向导，在安装时出现的内容。 |
| data 目录                                    | 系统数据库所在的目录。                 |
| my.ini 文件                                  | MySQL 的主要配置文件。                 |
| C:\ProgramData\MySQL\MySQL Server 8.0\data\  | 用户创建的数据库所在的目录。           |

### 6.2 MySQL 源代码获取

首先，你要进入 MySQL 下载界面。 这里你不要选择用默认的“Microsoft Windows”，而是要通过下拉栏，找到“Source Code”，在下面的操作系统版本里面， 选择 Windows（Architecture Independent），然后点击下载。

接下来，把下载下来的压缩文件解压，我们就得到了 MySQL 的源代码。

MySQL 是用 C++ 开发而成的，我简单介绍一下源代码的组成。

mysql-8.0.22 目录下的各个子目录，包含了 MySQL 各部分组件的源代码：

- sql 子目录是 MySQL 核心代码；

- libmysql 子目录是客户端程序 API；

- mysql-test 子目录是测试工具；

- mysys 子目录是操作系统相关函数和辅助函数；

源代码可以用记事本打开查看，如果你有 C++ 的开发环境，也可以在开发环境中打开查看。

如上图所示，源代码并不神秘，就是普通的 C++ 代码，跟你熟悉的一样，而且有很多注释，可以帮助你理解。阅读源代码就像在跟 MySQL 的开发人员对话一样，十分有趣。

## 7. 常见问题的解决(课外内容)

### 7.1 问题 1：root 用户密码忘记，重置的操作

1、通过任务管理器或者服务管理，关掉 mysqld(服务进程)

2、通过命令行+特殊参数开启 mysqld

```sh
mysqld --defaults-file="D:\ProgramFiles\CodePrograms\MySQL\MySQLServer5.7Data\my.ini" --skip-grant-tables
```

3、此时，mysqld 服务进程已经打开。并且不需要权限检查

4、mysql -uroot 无密码登陆服务器。另启动一个客户端进行

5、修改权限表

（1） use mysql;

（2）update user set authentication_string=password('新密码') where user='root' and Host='localhost';

（3）flush privileges;

6、通过任务管理器，关掉 mysqld 服务进程。

7、再次通过服务管理，打开 mysql 服务。

8、即可用修改后的新密码登陆。

### 7.2 问题 2：mysql 命令报“不是内部或外部命令”

如果输入 mysql 命令报“不是内部或外部命令”，把 mysql 安装目录的 bin 目录配置到环境变量 path 中。

### 7.3 问题 3：错误 ERROR ：没有选择数据库就操作表格和数据

| ERROR 1046 (3D000): No database selected                                                |
| --------------------------------------------------------------------------------------- |
| 解决方案一：就是使用“USE 数据库名;”语句，这样接下来的语句就默认针对这个数据库进行操作。 |
| 解决方案二：就是所有的表对象前面都加上“数据库.”。                                       |

### 7.4 问题 4：命令行客户端的字符集问题

```sh
mysql> INSERT INTO t_stu VALUES(1,'张三','男');
ERROR 1366 (HY000): Incorrect string value: '\xD5\xC5\xC8\xFD' for column 'sname' at row 1
```

原因：服务器端认为你的客户端的字符集是 utf-8，而实际上你的客户端的字符集是 GBK。

查看所有字符集：**SHOW VARIABLES LIKE 'character*set*%';**

解决方案，设置当前连接的客户端字符集 **“SET NAMES GBK;”**

### 7.5 问题 5：修改数据库和表的字符编码

修改编码：

（1） 先停止服务

（2）修改 my.ini 文件

（3）重新启动服务

说明：

如果是在修改 my.ini 之前建的库和表，那么库和表的编码还是原来的 Latin1，要么删了重建，要么使用 alter 语句修改编码。

```sh
mysql> create database myxh charset Latin1;
Query OK, 1 row affected (0.00 sec)
```

```sh
mysql> use myxh;
Database changed
```

```sh
mysql> create table student (id int , name varchar(20)) charset Latin1;
Query OK, 0 rows affected (0.02 sec)

mysql> show create table student\G
*************************** 1. row ***************************
       Table: student
Create Table: CREATE TABLE `student`
(
  `id` int(11) NOT NULL,
  `name` varchar(20) DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=latin1
1 row in set (0.00 sec)
```

```sql
# 修改表字符编码为 UTF8
mysql> alter table student charset utf8;
Query OK, 0 rows affected (0.01 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> show create table student\G
*************************** 1. row ***************************
       Table: student
Create Table: CREATE TABLE `student`
(
  `id` int(11) NOT NULL,
   # 字段仍然是 latin1 编码
  `name` varchar(20) CHARACTER SET latin1 DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8
1 row in set (0.00 sec)

# 修改字段字符编码为 UTF8
mysql> alter table student modify name varchar(20) charset utf8;
Query OK, 0 rows affected (0.05 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> show create table student\G
*************************** 1. row ***************************
       Table: student
Create Table: CREATE TABLE `student`
(
  `id` int(11) NOT NULL,
  `name` varchar(20) DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8
1 row in set (0.00 sec)
```

```sql
mysql> show create database myxh;;
+--------+-----------------------------------------------------------------+
|Database| Create Database                                                 |
+------+-------------------------------------------------------------------+
|myxh| CREATE DATABASE `myxh` /*!40100 DEFAULT CHARACTER SET latin1 */ |
+------+-------------------------------------------------------------------+
1 row in set (0.00 sec)

# 修改数据库的字符编码为 utf8
mysql> alter database myxh charset utf8;
Query OK, 1 row affected (0.00 sec)

mysql> show create database myxh;
+--------+-----------------------------------------------------------------+
|Database| Create Database                                                 |
+--------+-----------------------------------------------------------------+
| myxh | CREATE DATABASE `myxh` /*!40100 DEFAULT CHARACTER SET utf8 */ |
+--------+-----------------------------------------------------------------+
1 row in set (0.00 sec)
```

# 第 3 章 基本的 SELECT 语句

## 1. SQL 概述

### 1.1 SQL 背景知识

- 1946 年，世界上第一台电脑诞生，如今，借由这台电脑发展起来的互联网已经自成江湖。在这几十年里，无数的技术、产业在这片江湖里沉浮，有的方兴未艾，有的已经几幕兴衰。但在这片浩荡的波动里，有一门技术从未消失，甚至“老当益壮”，那就是 SQL。

  - 45 年前，也就是 1974 年，IBM 研究员发布了一篇揭开数据库技术的论文《SEQUEL：一门结构化的英语查询语言》，直到今天这门结构化的查询语言并没有太大的变化，相比于其他语言，`SQL 的半衰期可以说是非常长`了。

- 不论是前端工程师，还是后端算法工程师，都一定会和数据打交道，都需要了解如何又快又准确地提取自己想要的数据。更别提数据分析师了，他们的工作就是和数据打交道，整理不同的报告，以便指导业务决策。

- SQL（Structured Query Language，结构化查询语言）是使用关系模型的数据库应用语言，`与数据直接打交道`，由`IBM`上世纪 70 年代开发出来。后由美国国家标准局（ANSI）开始着手制定 SQL 标准，先后有`SQL-86`，`SQL-89`，`SQL-92`，`SQL-99`等标准。

  - SQL 有两个重要的标准，分别是 SQL92 和 SQL99，它们分别代表了 92 年和 99 年颁布的 SQL 标准，我们今天使用的 SQL 语言依然遵循这些标准。

- 不同的数据库生产厂商都支持 SQL 语句，但都有特有内容。

  ![SQL 背景知识](https://img-blog.csdnimg.cn/b20a883e234f4230b3aa9e6e859739fd.png)

### 1.2 SQL 语言排行榜

自从 SQL 加入了 TIOBE 编程语言排行榜，就一直保持在 Top 10。

![SQL 语言排行榜](https://img-blog.csdnimg.cn/4aab097a862d44edb8de8910639f5093.png)

### 1.3 SQL 分类

SQL 语言在功能上主要分为如下 3 大类：

- **DDL（Data Definition Languages、数据定义语言）**，这些语句定义了不同的数据库、表、视图、索引等数据库对象，还可以用来创建、删除、修改数据库和数据表的结构。

  - 主要的语句关键字包括`CREATE`、`DROP`、`ALTER`等。

- **DML（Data Manipulation Language、数据操作语言）**，用于添加、删除、更新和查询数据库记录，并检查数据完整性。

  - 主要的语句关键字包括`INSERT`、`DELETE`、`UPDATE`、`SELECT`等。

  - **SELECT 是 SQL 语言的基础，最为重要。**

- **DCL（Data Control Language、数据控制语言）**，用于定义数据库、表、字段、用户的访问权限和安全级别。

  - 主要的语句关键字包括`GRANT`、`REVOKE`、`COMMIT`、`ROLLBACK`、`SAVEPOINT`等。

> 因为查询语句使用的非常的频繁，所以很多人把查询语句单拎出来一类：DQL（数据查询语言）。
>
> 还有单独将`COMMIT`、`ROLLBACK` 取出来称为 TCL （Transaction Control Language，事务控制语言）。

## 2. SQL 语言的规则与规范

### 2.1 基本规则

- SQL 可以写在一行或者多行。为了提高可读性，各子句分行写，必要时使用缩进。

- 每条命令以 ; 或 \g 或 \G 结束。

- 关键字不能被缩写也不能分行。

- 关于标点符号

  - 必须保证所有的()、单引号、双引号是成对结束的。

  - 必须使用英文状态下的半角输入方式。

  - 字符串型和日期时间类型的数据可以使用单引号（' '）表示。

  - 列的别名，尽量使用双引号（" "），而且不建议省略 as。

### 2.2 SQL 大小写规范 （建议遵守）

- **MySQL 在 Windows 环境下是大小写不敏感的。**

- **MySQL 在 Linux 环境下是大小写敏感的。**

  - 数据库名、表名、表的别名、变量名是严格区分大小写的。

  - 关键字、函数名、列名(或字段名)、列的别名(字段的别名) 是忽略大小写的。

- **推荐采用统一的书写规范：**

  - 数据库名、表名、表别名、字段名、字段别名等都小写。

  - SQL 关键字、函数名、绑定变量等都大写。

### 2.3 注释

可以使用如下格式的注释结构

单行注释：

```sql
# 注释文字(MySQL 特有的方式)
```

单行注释：

```sql
-- 注释文字(-- 后面必须包含一个空格。)
```

多行注释：

```sql
/* 注释文字 */
```

### 2.4 命名规则（暂时了解）

- 数据库、表名不得超过 30 个字符，变量名限制为 29 个。

- 必须只能包含 A–Z, a–z, 0–9, \_共 63 个字符。

- 数据库名、表名、字段名等对象名中间不要包含空格。

- 同一个 MySQL 软件中，数据库不能同名；同一个库中，表不能重名；同一个表中，字段不能重名。

- 必须保证你的字段没有和保留字、数据库系统或常用方法冲突。如果坚持使用，请在 SQL 语句中使用``（着重号）引起来。

- 保持字段名和类型的一致性，在命名字段并为其指定数据类型的时候一定要保证一致性。假如数据类型在一个表里是整数，那在另一个表里可就别变成字符型了。

举例：

```sql
# 以下两句是一样的，不区分大小写
show databases;
SHOW DATABASES;

# 创建表格
# 表名错误，因为表名有空格
# create table student info(...);
create table student_info(...);

# 其中 order 使用``着重号，因为order和系统关键字或系统函数名等预定义标识符重名了
CREATE TABLE `order`
(
    id INT,
    lname VARCHAR(20)
);

# 起别名时，as 都可以省略
select id as "编号", `name` as "姓名" from t_stu;

# 错误，如果字段别名中有空格，那么不能省略""
# select id as 编 号, `name` as 姓 名 from t_stu;
# 如果字段别名中没有空格，那么可以省略""
select id as 编号, `name` as 姓名 from t_stu;
```

### 2.5 数据导入指令

在命令行客户端登录 mysql，使用 source 指令导入。

```sh
mysql> source D:\mysqldb.sql
```

```sh
mysql> desc employees;
+----------------+-------------+------+-----+---------+-------+
| Field          | Type        | Null | Key | Default | Extra |
+----------------+-------------+------+-----+---------+-------+
| employee_id    | int(6)      | NO   | PRI | 0       |       |
| first_name     | varchar(20) | YES  |     | NULL    |       |
| last_name      | varchar(25) | NO   |     | NULL    |       |
| email          | varchar(25) | NO   | UNI | NULL    |       |
| phone_number   | varchar(20) | YES  |     | NULL    |       |
| hire_date      | date        | NO   |     | NULL    |       |
| job_id         | varchar(10) | NO   | MUL | NULL    |       |
| salary         | double(8,2) | YES  |     | NULL    |       |
| commission_pct | double(2,2) | YES  |     | NULL    |       |
| manager_id     | int(6)      | YES  | MUL | NULL    |       |
| department_id  | int(4)      | YES  | MUL | NULL    |       |
+----------------+-------------+------+-----+---------+-------+
11 rows in set (0.00 sec)
```

## 3. 基本的 SELECT 语句

### 3.1 SELECT...

```sql
# 没有任何子句
SELECT 1;

# 没有任何子句
SELECT 9/2;
```

### 3.2 SELECT ... FROM

- 语法：

  > SELECT 标识选择哪些列
  > FROM 标识从哪个表中选择

- 选择全部列：

  ```sql
  SELECT *
  FROM   departments;
  ```

  ![SELECT ... FROM](https://img-blog.csdnimg.cn/ecd040a46d574b20912c523ad82614a6.png)

> 一般情况下，除非需要使用表中所有的字段数据，最好不要使用通配符‘\*’。使用通配符虽然可以节省输入查询语句的时间，但是获取不需要的列数据通常会降低查询和所使用的应用程序的效率。通配符的优势是，当不知道所需要的列的名称时，可以通过它获取它们。
>
> 在生产环境下，不推荐你直接使用`SELECT *`进行查询。

- 选择特定的列：

  ```sql
  SELECT department_id, location_id
  FROM   departments;
  ```

  ![SELECT ... FROM](https://img-blog.csdnimg.cn/f37b887cd19747818e74fa5cfa49e043.png)

> MySQL 中的 SQL 语句是不区分大小写的，因此 SELECT 和 select 的作用是相同的，但是，许多开发人员习惯将关键字大写、数据列和表名小写，读者也应该养成一个良好的编程习惯，这样写出来的代码更容易阅读和维护。

### 3.3 列的别名

- 重命名一个列。

- 便于计算。

- 紧跟列名，也可以**在列名和别名之间加入关键字 AS，别名使用双引号**，以便在别名中包含空格或特殊的字符并区分大小写。

- AS 可以省略。

- 建议别名简短，见名知意。

- 举例

  ```sql
  SELECT last_name AS name, commission_pct comm
  FROM   employees;
  ```

  ![列的别名](https://img-blog.csdnimg.cn/a90ccfa96b194ab385a3003545f78ed7.png)

  ```sql
  SELECT last_name "Name", salary*12 "Annual Salary"
  FROM   employees;
  ```

  ![列的别名](https://img-blog.csdnimg.cn/668690ef2067485fbf6668cf42f147f7.png)

### 3.4 去除重复行

默认情况下，查询会返回全部行，包括重复行。

```sql
SELECT department_id
FROM   employees;
```

![去除重复行](https://img-blog.csdnimg.cn/d6537caccdbf4118a5b4e592184eb3d2.png)

**在 SELECT 语句中使用关键字 DISTINCT 去除重复行**

```sql
SELECT DISTINCT department_id
FROM   employees;
```

![去除重复行](https://img-blog.csdnimg.cn/8bc8a9aed7b34e3d932dad3e9ee6245b.png)

针对于：

```sql
SELECT DISTINCT department_id,salary
FROM employees;
```

这里有两点需要注意：

1. DISTINCT 需要放到所有列名的前面，如果写成`SELECT salary, DISTINCT department_id FROM employees`会报错。

2. DISTINCT 其实是对后面所有列名的组合进行去重，你能看到最后的结果是 74 条，因为这 74 个部门 id 不同，都有 salary 这个属性值。如果你想要看都有哪些不同的部门（department_id），只需要写`DISTINCT department_id`即可，后面不需要再加其他的列名了。

### 3.5 空值参与运算

- 所有运算符或列值遇到 null 值，运算的结果都为 null。

  ```sql
  SELECT employee_id,salary,commission_pct,
  12 * salary * (1 + commission_pct) "annual_sal"
  FROM employees;
  ```

  这里你一定要注意，在 MySQL 里面， 空值不等于空字符串。一个空字符串的长度是 0，而一个空值的长度是空。而且，在 MySQL 里面，空值是占用空间的。

### 3.6 着重号

- 错误的

  ```sh
  mysql> SELECT * FROM ORDER;
  ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'ORDER' at line 1
  ```

- 正确的

  ```sh
  mysql> SELECT * FROM `ORDER`;
  +----------+------------+
  | order_id | order_name |
  +----------+------------+
  |        1 | myxh   |
  |        2 | tomcat     |
  |        3 | dubbo      |
  +----------+------------+
  3 rows in set (0.00 sec)

  mysql> SELECT * FROM `order`;
  +----------+------------+
  | order_id | order_name |
  +----------+------------+
  |        1 | myxh   |
  |        2 | tomcat     |
  |        3 | dubbo      |
  +----------+------------+
  3 rows in set (0.00 sec)
  ```

- 结论

  我们需要保证表中的字段、表名等没有和保留字、数据库系统或常用方法冲突。如果真的相同，请在 SQL 语句中使用一对``（着重号）引起来。

### 3.7 查询常数

SELECT 查询还可以对常数进行查询。对的，就是在 SELECT 查询结果中增加一列固定的常数列。这列的取值是我们指定的，而不是从数据表中动态取出的。

你可能会问为什么我们还要对常数进行查询呢？

SQL 中的 SELECT 语法的确提供了这个功能，一般来说我们只从一个表中查询数据，通常不需要增加一个固定的常数列，但如果我们想整合不同的数据源，用常数列作为这个表的标记，就需要查询常数。

比如说，我们想对 employees 数据表中的员工姓名进行查询，同时增加一列字段`corporation`，这个字段固定值为“myxh”，可以这样写：

```sql
SELECT 'myxh' as corporation, last_name FROM employees;
```

## 4. 显示表结构

使用 DESCRIBE 或 DESC 命令，表示表结构。

```sql
DESCRIBE employees;
```

或

```sql
DESC employees;
```

```sh
mysql> desc employees;
+----------------+-------------+------+-----+---------+-------+
| Field          | Type        | Null | Key | Default | Extra |
+----------------+-------------+------+-----+---------+-------+
| employee_id    | int(6)      | NO   | PRI | 0       |       |
| first_name     | varchar(20) | YES  |     | NULL    |       |
| last_name      | varchar(25) | NO   |     | NULL    |       |
| email          | varchar(25) | NO   | UNI | NULL    |       |
| phone_number   | varchar(20) | YES  |     | NULL    |       |
| hire_date      | date        | NO   |     | NULL    |       |
| job_id         | varchar(10) | NO   | MUL | NULL    |       |
| salary         | double(8,2) | YES  |     | NULL    |       |
| commission_pct | double(2,2) | YES  |     | NULL    |       |
| manager_id     | int(6)      | YES  | MUL | NULL    |       |
| department_id  | int(4)      | YES  | MUL | NULL    |       |
+----------------+-------------+------+-----+---------+-------+
11 rows in set (0.00 sec)
```

其中，各个字段的含义分别解释如下：

- Field：表示字段名称。

- Type：表示字段类型，这里 barcode、goodsname 是文本型的，price 是整数类型的。

- Null：表示该列是否可以存储 NULL 值。

- Key：表示该列是否已编制索引。PRI 表示该列是表主键的一部分；UNI 表示该列是 UNIQUE 索引的一部分；MUL 表示在列中某个给定值允许出现多次。

- Default：表示该列是否有默认值，如果有，那么值是多少。

- Extra：表示可以获取的与给定列有关的附加信息，例如 AUTO_INCREMENT 等。

## 5. 过滤数据

- 背景：

  ![过滤数据](https://img-blog.csdnimg.cn/087cf00e892a4b3298f8821c5c539574.png)

- 语法：

  > SELECT 字段 1,字段 2
  > FROM 表名
  > WHERE 过滤条件

- 使用 WHERE 子句，将不满足条件的行过滤掉。

- **WHERE 子句紧随 FROM 子句。**

- 举例

  ```sql
  SELECT employee_id, last_name, job_id, department_id
  FROM   employees
  WHERE  department_id = 90 ;
  ```

  ![过滤数据](https://img-blog.csdnimg.cn/a4a7e945f6254d889929958181e5de63.png)

# 第 4 章 运算符

## 1. 算术运算符

算术运算符主要用于数学运算，其可以连接运算符前后的两个数值或表达式，对数值或表达式进行加（+）、减（-）、乘（\*）、除（/）和取模（%）运算。

![算术运算符](https://img-blog.csdnimg.cn/eed920a4a9ec4481bfdfec36a71341d3.png)

**1．加法与减法运算符**

```sh
mysql> SELECT 100, 100 + 0, 100 - 0, 100 + 50, 100 + 50 -30, 100 + 35.5, 100 - 35.5 FROM dual;
+-----+---------+---------+----------+--------------+------------+------------+
| 100 | 100 + 0 | 100 - 0 | 100 + 50 | 100 + 50 -30 | 100 + 35.5 | 100 - 35.5 |
+-----+---------+---------+----------+--------------+------------+------------+
| 100 |     100 |     100 |      150 |          120 |      135.5 |       64.5 |
+-----+---------+---------+----------+--------------+------------+------------+
1 row in set (0.00 sec)
```

由运算结果可以得出如下结论：

> - 一个整数类型的值对整数进行加法和减法操作，结果还是一个整数；
>
> - 一个整数类型的值对浮点数进行加法和减法操作，结果是一个浮点数；
>
> - 加法和减法的优先级相同，进行先加后减操作与进行先减后加操作的结果是一样的；
>
> - 在 Java 中，+的左右两边如果有字符串，那么表示字符串的拼接。但是在 MySQL 中+只表示数值相加。如果遇到非数值类型，先尝试转成数值，如果转失败，就按 0 计算。（补充：MySQL 中字符串拼接要使用字符串函数 CONCAT()实现）

**2．乘法与除法运算符**

```sh
mysql> SELECT 100, 100 * 1, 100 * 1.0, 100 / 1.0, 100 / 2,100 + 2 * 5 / 2,100 /3, 100 DIV 0 FROM dual;
+-----+---------+-----------+-----------+---------+-----------------+---------+-----------+
| 100 | 100 * 1 | 100 * 1.0 | 100 / 1.0 | 100 / 2 | 100 + 2 * 5 / 2 | 100 /3  | 100 DIV 0 |
+-----+---------+-----------+-----------+---------+-----------------+---------+-----------+
| 100 |     100 |     100.0 |  100.0000 | 50.0000 |        105.0000 | 33.3333 |      NULL |
+-----+---------+-----------+-----------+---------+-----------------+---------+-----------+
1 row in set (0.00 sec)
```

```sql
# 计算出员工的年基本工资
SELECT employee_id,salary,salary * 12 annual_sal
FROM employees;
```

由运算结果可以得出如下结论：

> - 一个数乘以整数 1 和除以整数 1 后仍得原数；
>
> - 一个数乘以浮点数 1 和除以浮点数 1 后变成浮点数，数值与原数相等；
>
> - 一个数除以整数后，不管是否能除尽，结果都为一个浮点数；
>
> - 一个数除以另一个数，除不尽时，结果为一个浮点数，并保留到小数点后 4 位；
>
> - 乘法和除法的优先级相同，进行先乘后除操作与先除后乘操作，得出的结果相同；
>
> - 在数学运算中，0 不能用作除数，在 MySQL 中，一个数除以 0 为 NULL。

**3．求模（求余）运算符**

将 dual 表中的字段 i 对 3 和 5 进行求模（求余）运算。

```sh
mysql> SELECT 12 % 3, 12 MOD 5 FROM dual;
+--------+----------+
| 12 % 3 | 12 MOD 5 |
+--------+----------+
|      0 |        2 |
+--------+----------+
1 row in set (0.00 sec)
```

```sql
# 筛选出 employee_id 是偶数的员工
SELECT * FROM employees
WHERE employee_id MOD 2 = 0;
```

可以看到，100 对 3 求模后的结果为 3，对 5 求模后的结果为 0。

## 2. 比较运算符

比较运算符用来对表达式左边的操作数和右边的操作数进行比较，比较的结果为真则返回 1，比较的结果为假则返回 0，其他情况则返回 NULL。

比较运算符经常被用来作为 SELECT 查询语句的条件来使用，返回符合条件的结果记录。

![比较运算符](https://img-blog.csdnimg.cn/ac4059970ef74e68a65fd68aebd0ead4.png)

**1．等号运算符**

- 等号运算符（=）判断等号两边的值、字符串或表达式是否相等，如果相等则返回 1，不相等则返回 0。

- 在使用等号运算符时，遵循如下规则：

  - 如果等号两边的值、字符串或表达式都为字符串，则 MySQL 会按照字符串进行比较，其比较的是每个字符串中字符的 ANSI 编码是否相等。

  - 如果等号两边的值都是整数，则 MySQL 会按照整数来比较两个值的大小。

  - 如果等号两边的值一个是整数，另一个是字符串，则 MySQL 会将字符串转化为数字进行比较。

  - 如果等号两边的值、字符串或表达式中有一个为 NULL，则比较结果为 NULL。

- 对比：SQL 中赋值符号使用 :=

  ```sh
  mysql> SELECT 1 = 1, 1 = '1', 1 = 0, 'a' = 'a', (5 + 3) = (2 + 6), '' = NULL , NULL = NULL;
  +-------+---------+-------+-----------+-------------------+-----------+-------------+
  | 1 = 1 | 1 = '1' | 1 = 0 | 'a' = 'a' | (5 + 3) = (2 + 6) | '' = NULL | NULL = NULL |
  +-------+---------+-------+-----------+-------------------+-----------+-------------+
  |    1  |     1   |   0   |      1    |             1     |    NULL   |        NULL  |
  +-------+---------+-------+-----------+-------------------+-----------+-------------+
  1 row in set (0.00 sec)
  ```

  ```sh
  mysql> SELECT 1 = 2, 0 = 'abc', 1 = 'abc' FROM dual;
  +-------+-----------+-----------+
  | 1 = 2 | 0 = 'abc' | 1 = 'abc' |
  +-------+-----------+-----------+
  |     0 |         1 |         0 |
  +-------+-----------+-----------+
  1 row in set, 2 warnings (0.00 sec)
  ```

  ```sql
  # 查询 salary=10000，注意在 Java 中比较是 ==
  SELECT employee_id,salary FROM employees WHERE salary = 10000;
  ```

**2．安全等于运算符**

安全等于运算符（<=>）与等于运算符（=）的作用是相似的，`唯一的区别`是‘<=>’可以用来对 NULL 进行判断。在两个操作数均为 NULL 时，其返回值为 1，而不为 NULL；当一个操作数为 NULL 时，其返回值为 0，而不为 NULL。

```sh
mysql> SELECT 1 <=> '1', 1 <=> 0, 'a' <=> 'a', (5 + 3) <=> (2 + 6), '' <=> NULL,NULL <=> NULL FROM dual;
+-----------+---------+-------------+---------------------+-------------+---------------+
| 1 <=> '1' | 1 <=> 0 | 'a' <=> 'a' | (5 + 3) <=> (2 + 6) | '' <=> NULL | NULL <=> NULL |
+-----------+---------+-------------+---------------------+-------------+---------------+
|         1 |       0 |           1 |                   1 |           0 |             1 |
+-----------+---------+-------------+---------------------+-------------+---------------+
1 row in set (0.00 sec)
```

```sql
# 查询 commission_pct 等于 0.40
SELECT employee_id,commission_pct FROM employees WHERE commission_pct = 0.40;

SELECT employee_id,commission_pct FROM employees WHERE commission_pct <=> 0.40;
```

如果把 0.40 改成 NULL 呢？

可以看到，使用安全等于运算符时，两边的操作数的值都为 NULL 时，返回的结果为 1 而不是 NULL，其他返回结果与等于运算符相同。

**3．不等于运算符**

不等于运算符（<>和!=）用于判断两边的数字、字符串或者表达式的值是否不相等，如果不相等则返回 1，相等则返回 0。不等于运算符不能判断 NULL 值。如果两边的值有任意一个为 NULL，或两边都为 NULL，则结果为 NULL。
SQL 语句示例如下：

```sh
mysql> SELECT 1 <> 1, 1 != 2, 'a' != 'b', (3+4) <> (2+6), 'a' != NULL, NULL <> NULL;
+--------+--------+------------+----------------+-------------+--------------+
| 1 <> 1 | 1 != 2 | 'a' != 'b' | (3+4) <> (2+6) | 'a' != NULL | NULL <> NULL |
+--------+--------+------------+----------------+-------------+--------------+
|      0 |   1    |       1    |            1   |     NULL    |         NULL |
+--------+--------+------------+----------------+-------------+--------------+
1 row in set (0.00 sec)
```

此外，还有非符号类型的运算符：

![比较运算符](https://img-blog.csdnimg.cn/d14d9af0f8db495787c4dea4934981bb.png)

**4. 空运算符**

空运算符（IS NULL 或者 ISNULL）判断一个值是否为 NULL，如果为 NULL 则返回 1，否则返回 0。
SQL 语句示例如下：

```sh
mysql> SELECT NULL IS NULL, ISNULL(NULL), ISNULL('a'), 1 IS NULL;
+--------------+--------------+-------------+-----------+
| NULL IS NULL | ISNULL(NULL) | ISNULL('a') | 1 IS NULL |
+--------------+--------------+-------------+-----------+
|            1 |            1 |           0 |         0 |
+--------------+--------------+-------------+-----------+
1 row in set (0.00 sec)
```

```sql
# 查询 commission_pct 等于 NULL。比较如下的四种写法
SELECT employee_id,commission_pct FROM employees WHERE commission_pct IS NULL;
SELECT employee_id,commission_pct FROM employees WHERE commission_pct <=> NULL;
SELECT employee_id,commission_pct FROM employees WHERE ISNULL(commission_pct);
SELECT employee_id,commission_pct FROM employees WHERE commission_pct = NULL;
```

```sql
SELECT last_name, manager_id
FROM   employees
WHERE  manager_id IS NULL;
```

**5. 非空运算符**

非空运算符（IS NOT NULL）判断一个值是否不为 NULL，如果不为 NULL 则返回 1，否则返回 0。
SQL 语句示例如下：

```sh
mysql> SELECT NULL IS NOT NULL, 'a' IS NOT NULL,  1 IS NOT NULL;
+------------------+-----------------+---------------+
| NULL IS NOT NULL | 'a' IS NOT NULL | 1 IS NOT NULL |
+------------------+-----------------+---------------+
|                0 |               1 |             1 |
+------------------+-----------------+---------------+
1 row in set (0.01 sec)
```

```sql
# 查询 commission_pct 不等于 NULL
SELECT employee_id,commission_pct FROM employees WHERE commission_pct IS NOT NULL;
SELECT employee_id,commission_pct FROM employees WHERE NOT commission_pct <=> NULL;
SELECT employee_id,commission_pct FROM employees WHERE NOT ISNULL(commission_pct);
```

**6. 最小值运算符**

语法格式为：LEAST(值 1，值 2，...，值 n)。其中，“值 n”表示参数列表中有 n 个值。在有两个或多个参数的情况下，返回最小值。

```sh
mysql> SELECT LEAST (1,0,2), LEAST('b','a','c'), LEAST(1,NULL,2);
+---------------+--------------------+-----------------+
| LEAST (1,0,2) | LEAST('b','a','c') | LEAST(1,NULL,2) |
+---------------+--------------------+-----------------+
|       0       |        a           |      NULL       |
+---------------+--------------------+-----------------+
1 row in set (0.00 sec)
```

由结果可以看到，当参数是整数或者浮点数时，LEAST 将返回其中最小的值；当参数为字符串时，返回字母表中顺序最靠前的字符；当比较值列表中有 NULL 时，不能判断大小，返回值为 NULL。

**7. 最大值运算符**

语法格式为：GREATEST(值 1，值 2，...，值 n)。其中，n 表示参数列表中有 n 个值。当有两个或多个参数时，返回值为最大值。假如任意一个自变量为 NULL，则 GREATEST()的返回值为 NULL。

```sh
mysql> SELECT GREATEST(1,0,2), GREATEST('b','a','c'), GREATEST(1,NULL,2);
+-----------------+-----------------------+--------------------+
| GREATEST(1,0,2) | GREATEST('b','a','c') | GREATEST(1,NULL,2) |
+-----------------+-----------------------+--------------------+
|               2 | c                     |               NULL |
+-----------------+-----------------------+--------------------+
1 row in set (0.00 sec)
```

由结果可以看到，当参数中是整数或者浮点数时，GREATEST 将返回其中最大的值；当参数为字符串时，返回字母表中顺序最靠后的字符；当比较值列表中有 NULL 时，不能判断大小，返回值为 NULL。

**8. BETWEEN AND 运算符**

BETWEEN 运算符使用的格式通常为 SELECT D FROM TABLE WHERE C BETWEEN A AND B，此时，当 C 大于或等于 A，并且 C 小于或等于 B 时，结果为 1，否则结果为 0。

```sh
mysql> SELECT 1 BETWEEN 0 AND 1, 10 BETWEEN 11 AND 12, 'b' BETWEEN 'a' AND 'c';
+-------------------+----------------------+-------------------------+
| 1 BETWEEN 0 AND 1 | 10 BETWEEN 11 AND 12 | 'b' BETWEEN 'a' AND 'c' |
+-------------------+----------------------+-------------------------+
|                 1 |                    0 |                       1 |
+-------------------+----------------------+-------------------------+
1 row in set (0.00 sec)
```

```sql
SELECT last_name, salary
FROM   employees
WHERE  salary BETWEEN 2500 AND 3500;
```

**9. IN 运算符**

IN 运算符用于判断给定的值是否是 IN 列表中的一个值，如果是则返回 1，否则返回 0。如果给定的值为 NULL，或者 IN 列表中存在 NULL，则结果为 NULL。

```sh
mysql> SELECT 'a' IN ('a','b','c'), 1 IN (2,3), NULL IN ('a','b'), 'a' IN ('a', NULL);
+----------------------+------------+-------------------+--------------------+
| 'a' IN ('a','b','c') | 1 IN (2,3) | NULL IN ('a','b') | 'a' IN ('a', NULL) |
+----------------------+------------+-------------------+--------------------+
|            1         |        0   |         NULL      |         1          |
+----------------------+------------+-------------------+--------------------+
1 row in set (0.00 sec)
```

```sql
SELECT employee_id, last_name, salary, manager_id
FROM   employees
WHERE  manager_id IN (100, 101, 201);
```

**10. NOT IN 运算符**

NOT IN 运算符用于判断给定的值是否不是 IN 列表中的一个值，如果不是 IN 列表中的一个值，则返回 1，否则返回 0。

```sh
mysql> SELECT 'a' NOT IN ('a','b','c'), 1 NOT IN (2,3);
+--------------------------+----------------+
| 'a' NOT IN ('a','b','c') | 1 NOT IN (2,3) |
+--------------------------+----------------+
|                 0        |            1   |
+--------------------------+----------------+
1 row in set (0.00 sec)
```

**11. LIKE 运算符**

LIKE 运算符主要用来匹配字符串，通常用于模糊匹配，如果满足条件则返回 1，否则返回 0。如果给定的值或者匹配条件为 NULL，则返回结果为 NULL。

LIKE 运算符通常使用如下通配符：

> “%”：匹配 0 个或多个字符。
> “\_”：只能匹配一个字符。

SQL 语句示例如下：

```sh
mysql> SELECT NULL LIKE 'abc', 'abc' LIKE NULL;
+-----------------+-----------------+
| NULL LIKE 'abc' | 'abc' LIKE NULL |
+-----------------+-----------------+
|          NULL   |          NULL   |
+-----------------+-----------------+
1 row in set (0.00 sec)
```

```sql
SELECT first_name
FROM   employees
WHERE  first_name LIKE 'S%';
```

```sql
SELECT last_name
FROM   employees
WHERE  last_name LIKE '_o%';
```

**ESCAPE**

- 回避特殊符号的：**使用转义符**。例如：将[\%]转为[\$%]、[]转为[\$]，然后再加上[\ESCAPE‘$’]即可。

  ```sql
  SELECT job_id
  FROM   jobs
  WHERE  job_id LIKE ‘IT\_%‘;
  ```

- 如果使用\表示转义，要省略 ESCAPE。如果不是\，则要加上 ESCAPE。

  ```sql
  SELECT job_id
  FROM   jobs
  WHERE  job_id LIKE ‘IT$_%‘ escape ‘$‘;
  ```

**12. REGEXP 运算符**

REGEXP 运算符用来匹配字符串，语法格式为：`expr REGEXP 匹配条件`。如果 expr 满足匹配条件，返回 1；如果不满足，则返回 0。若 expr 或匹配条件任意一个为 NULL，则结果为 NULL。

REGEXP 运算符在进行匹配时，常用的有下面几种通配符：

（1）‘^’匹配以该字符后面的字符开头的字符串。

（2）‘$’匹配以该字符前面的字符结尾的字符串。

（3）‘.’匹配任何一个单字符。

（4）“[\...]”匹配在方括号内的任何字符。例如，“[abc]”匹配“a”或“b”或“c”。为了命名字符的范围，使用一个‘-’。“[a-z]”匹配任何字母，而“[0-9]”匹配任何数字。

（5）‘\*’匹配零个或多个在它前面的字符。例如，“x*”匹配任何数量的‘x’字符，“[0-9]*”匹配任何数量的数字，而“\*”匹配任何数量的任何字符。

SQL 语句示例如下：

```sh
mysql> SELECT 'myxh' REGEXP '^s', 'myxh' REGEXP 't$', 'myxh' REGEXP 'hk';
+------------------------+------------------------+-------------------------+
| 'myxh' REGEXP '^s' | 'myxh' REGEXP 't$' | 'myxh' REGEXP 'hk'  |
+------------------------+------------------------+-------------------------+
|                      1 |                      1 |                       1 |
+------------------------+------------------------+-------------------------+
1 row in set (0.01 sec)
```

```sh
mysql> SELECT 'myxh' REGEXP 'gu.gu', 'myxh' REGEXP '[ab]';
+--------------------------+-------------------------+
| 'myxh' REGEXP 'gu.gu' | 'myxh' REGEXP '[ab]' |
+--------------------------+-------------------------+
|                        1 |                       1 |
+--------------------------+-------------------------+
1 row in set (0.00 sec)
```

## 3. 逻辑运算符

逻辑运算符主要用来判断表达式的真假，在 MySQL 中，逻辑运算符的返回结果为 1、0 或者 NULL。

MySQL 中支持 4 种逻辑运算符如下：

![逻辑运算符](https://img-blog.csdnimg.cn/66d3d56b1af84b118fc89f09ba81a99c.png)

**1．逻辑非运算符**

逻辑非（NOT 或!）运算符表示当给定的值为 0 时返回 1；当给定的值为非 0 值时返回 0；当给定的值为 NULL 时，返回 NULL。

```sh
mysql> SELECT NOT 1, NOT 0, NOT(1+1), NOT !1, NOT NULL;
+-------+-------+----------+--------+----------+
| NOT 1 | NOT 0 | NOT(1+1) | NOT !1 | NOT NULL |
+-------+-------+----------+--------+----------+
|     0 |     1 |        0 |      1 |     NULL |
+-------+-------+----------+--------+----------+
1 row in set, 1 warning (0.00 sec)
```

```sql
SELECT last_name, job_id
FROM   employees
WHERE  job_id NOT IN ('IT_PROG', 'ST_CLERK', 'SA_REP');
```

**2．逻辑与运算符**

逻辑与（AND 或&&）运算符是当给定的所有值均为非 0 值，并且都不为 NULL 时，返回 1；当给定的一个值或者多个值为 0 时则返回 0；否则返回 NULL。

```sh
mysql> SELECT 1 AND -1, 0 AND 1, 0 AND NULL, 1 AND NULL;
+----------+---------+------------+------------+
| 1 AND -1 | 0 AND 1 | 0 AND NULL | 1 AND NULL |
+----------+---------+------------+------------+
|        1 |       0 |          0 |       NULL |
+----------+---------+------------+------------+
1 row in set (0.00 sec)
```

```sql
SELECT employee_id, last_name, job_id, salary
FROM   employees
WHERE  salary >=10000
AND    job_id LIKE '%MAN%';
```

**3．逻辑或运算符**

逻辑或（OR 或||）运算符是当给定的值都不为 NULL，并且任何一个值为非 0 值时，则返回 1，否则返回 0；当一个值为 NULL，并且另一个值为非 0 值时，返回 1，否则返回 NULL；当两个值都为 NULL 时，返回 NULL。

```sh
mysql> SELECT 1 OR -1, 1 OR 0, 1 OR NULL, 0 || NULL, NULL || NULL;
+---------+--------+-----------+-----------+--------------+
| 1 OR -1 | 1 OR 0 | 1 OR NULL | 0 || NULL | NULL || NULL |
+---------+--------+-----------+-----------+--------------+
|       1 |      1 |         1 |    NULL   |       NULL   |
+---------+--------+-----------+-----------+--------------+
1 row in set, 2 warnings (0.00 sec)
```

```sql
# 查询基本薪资不在 9000-12000 之间的员工编号和基本薪资
SELECT employee_id,salary FROM employees
WHERE NOT (salary >= 9000 AND salary <= 12000);

SELECT employee_id,salary FROM employees
WHERE salary <9000 OR salary > 12000;

SELECT employee_id,salary FROM employees
WHERE salary NOT BETWEEN 9000 AND 12000;
```

```sql
SELECT employee_id, last_name, job_id, salary
FROM   employees
WHERE  salary >= 10000
OR     job_id LIKE '%MAN%';
```

> 注意：
>
> OR 可以和 AND 一起使用，但是在使用时要注意两者的优先级，由于 AND 的优先级高于 OR，因此先对 AND 两边的操作数进行操作，再与 OR 中的操作数结合。

**4．逻辑异或运算符**

逻辑异或（XOR）运算符是当给定的值中任意一个值为 NULL 时，则返回 NULL；如果两个非 NULL 的值都是 0 或者都不等于 0 时，则返回 0；如果一个值为 0，另一个值不为 0 时，则返回 1。

```sh
mysql> SELECT 1 XOR -1, 1 XOR 0, 0 XOR 0, 1 XOR NULL, 1 XOR 1 XOR 1, 0 XOR 0 XOR 0;
+----------+---------+---------+------------+---------------+---------------+
| 1 XOR -1 | 1 XOR 0 | 0 XOR 0 | 1 XOR NULL | 1 XOR 1 XOR 1 | 0 XOR 0 XOR 0 |
+----------+---------+---------+------------+---------------+---------------+
|        0 |       1 |       0 |       NULL |             1 |             0 |
+----------+---------+---------+------------+---------------+---------------+
1 row in set (0.00 sec)
```

```sql
select last_name,department_id,salary
from employees
where department_id in (10,20) XOR salary > 8000;
```

## 4. 位运算符

位运算符是在二进制数上进行计算的运算符。位运算符会先将操作数变成二进制数，然后进行位运算，最后将计算结果从二进制变回十进制数。

MySQL 支持的位运算符如下：

![位运算符](https://img-blog.csdnimg.cn/1f0855954dac4f92b7a6c97f27471fbc.png)

**1．按位与运算符**

按位与（&）运算符将给定值对应的二进制数逐位进行逻辑与运算。当给定值对应的二进制位的数值都为 1 时，则该位返回 1，否则返回 0。

```sh
mysql> SELECT 1 & 10, 20 & 30;
+--------+---------+
| 1 & 10 | 20 & 30 |
+--------+---------+
|      0 |      20 |
+--------+---------+
1 row in set (0.00 sec)
```

1 的二进制数为 0001，10 的二进制数为 1010，所以 1 & 10 的结果为 0000，对应的十进制数为 0。20 的二进制数为 10100，30 的二进制数为 11110，所以 20 & 30 的结果为 10100，对应的十进制数为 20。

**2. 按位或运算符**

按位或（|）运算符将给定的值对应的二进制数逐位进行逻辑或运算。当给定值对应的二进制位的数值有一个或两个为 1 时，则该位返回 1，否则返回 0。

```sh
mysql> SELECT 1 | 10, 20 | 30;
+--------+---------+
| 1 | 10 | 20 | 30 |
+--------+---------+
|     11 |      30 |
+--------+---------+
1 row in set (0.00 sec)
```

1 的二进制数为 0001，10 的二进制数为 1010，所以 1 | 10 的结果为 1011，对应的十进制数为 11。20 的二进制数为 10100，30 的二进制数为 11110，所以 20 | 30 的结果为 11110，对应的十进制数为 30。

**3. 按位异或运算符**

按位异或（^）运算符将给定的值对应的二进制数逐位进行逻辑异或运算。当给定值对应的二进制位的数值不同时，则该位返回 1，否则返回 0。

```sh
mysql> SELECT 1 ^ 10, 20 ^ 30;
+--------+---------+
| 1 ^ 10 | 20 ^ 30 |
+--------+---------+
|     11 |      10 |
+--------+---------+
1 row in set (0.00 sec)
```

1 的二进制数为 0001，10 的二进制数为 1010，所以 1 ^ 10 的结果为 1011，对应的十进制数为 11。20 的二进制数为 10100，30 的二进制数为 11110，所以 20 ^ 30 的结果为 01010，对应的十进制数为 10。

再举例：

```sh
mysql> SELECT 12 & 5, 12 | 5,12 ^ 5 FROM DUAL;
+--------+--------+--------+
| 12 & 5 | 12 | 5 | 12 ^ 5 |
+--------+--------+--------+
|      4 |     13 |      9 |
+--------+--------+--------+
1 row in set (0.00 sec)
```

![按位异或运算符](https://img-blog.csdnimg.cn/2b982874752849688a8948b14bad59d0.png)

**4. 按位取反运算符**

按位取反（~）运算符将给定的值的二进制数逐位进行取反操作，即将 1 变为 0，将 0 变为 1。

```sh
mysql> SELECT 10 & ~1;
+---------+
| 10 & ~1 |
+---------+
|      10 |
+---------+
1 row in set (0.00 sec)
```

由于按位取反（~）运算符的优先级高于按位与（&）运算符的优先级，所以 10 & ~1，首先，对数字 1 进行按位取反操作，结果除了最低位为 0，其他位都为 1，然后与 10 进行按位与操作，结果为 10。

**5. 按位右移运算符**

按位右移（>>）运算符将给定的值的二进制数的所有位右移指定的位数。右移指定的位数后，右边低位的数值被移出并丢弃，左边高位空出的位置用 0 补齐。

```sh
mysql> SELECT 1 >> 2, 4 >> 2;
+--------+--------+
| 1 >> 2 | 4 >> 2 |
+--------+--------+
|      0 |      1 |
+--------+--------+
1 row in set (0.00 sec)
```

1 的二进制数为 0000 0001，右移 2 位为 0000 0000，对应的十进制数为 0。4 的二进制数为 0000 0100，右移 2 位为 0000 0001，对应的十进制数为 1。

**6. 按位左移运算符**

按位左移（<<）运算符将给定的值的二进制数的所有位左移指定的位数。左移指定的位数后，左边高位的数值被移出并丢弃，右边低位空出的位置用 0 补齐。

```sh
mysql> SELECT 1 << 2, 4 << 2;
+--------+--------+
| 1 << 2 | 4 << 2 |
+--------+--------+
|      4 |     16 |
+--------+--------+
1 row in set (0.00 sec)
```

1 的二进制数为 0000 0001，左移两位为 0000 0100，对应的十进制数为 4。4 的二进制数为 0000 0100，左移两位为 0001 0000，对应的十进制数为 16。

## 5. 运算符的优先级

![运算符的优先级](https://img-blog.csdnimg.cn/d1b805e1ddd04db2a513937ca95c9d9e.png)

数字编号越大，优先级越高，优先级高的运算符先进行计算。可以看到，赋值运算符的优先级最低，使用“()”括起来的表达式的优先级最高。

## 6. 拓展：使用正则表达式查询

正则表达式通常被用来检索或替换那些符合某个模式的文本内容，根据指定的匹配模式匹配文本中符合要求的特殊字符串。例如，从一个文本文件中提取电话号码，查找一篇文章中重复的单词或者替换用户输入的某些敏感词语等，这些地方都可以使用正则表达式。正则表达式强大而且灵活，可以应用于非常复杂的查询。

MySQL 中使用 REGEXP 关键字指定正则表达式的字符匹配模式。下表列出了 REGEXP 操作符中常用字符匹配列表。

![拓展：使用正则表达式查询](https://img-blog.csdnimg.cn/5439cd1f870641f9a3dcb7ebb25440ef.png)

**1. 查询以特定字符或字符串开头的记录**

字符‘^’匹配以特定字符或者字符串开头的文本。

在 fruits 表中，查询 f_name 字段以字母‘b’开头的记录，SQL 语句如下：

```sql
mysql> SELECT * FROM fruits WHERE f_name REGEXP '^b';
```

**2. 查询以特定字符或字符串结尾的记录**
字符‘$’匹配以特定字符或者字符串结尾的文本。

在 fruits 表中，查询 f_name 字段以字母‘y’结尾的记录，SQL 语句如下：

```sh
mysql> SELECT * FROM fruits WHERE f_name REGEXP 'y$';
```

**3. 用符号"."来替代字符串中的任意一个字符**

字符‘.’匹配任意一个字符。
在 fruits 表中，查询 f_name 字段值包含字母‘a’与‘g’且两个字母之间只有一个字母的记录，SQL 语句如下：

```sh
mysql> SELECT * FROM fruits WHERE f_name REGEXP 'a.g';
```

**4. 使用"\*"和"+"来匹配多个字符**

星号‘\*’匹配前面的字符任意多次，包括 0 次。加号‘+’匹配前面的字符至少一次。

在 fruits 表中，查询 f_name 字段值以字母‘b’开头且‘b’后面出现字母‘a’的记录，SQL 语句如下：

```sh
mysql> SELECT * FROM fruits WHERE f_name REGEXP '^ba*';
```

在 fruits 表中，查询 f_name 字段值以字母‘b’开头且‘b’后面出现字母‘a’至少一次的记录，SQL 语句如下：

```sh
mysql> SELECT * FROM fruits WHERE f_name REGEXP '^ba+';
```

**5. 匹配指定字符串**

正则表达式可以匹配指定字符串，只要这个字符串在查询文本中即可，如要匹配多个字符串，多个字符串之间使用分隔符‘|’隔开。

在 fruits 表中，查询 f_name 字段值包含字符串“on”的记录，SQL 语句如下：

```sh
mysql> SELECT * FROM fruits WHERE f_name REGEXP 'on';
```

在 fruits 表中，查询 f_name 字段值包含字符串“on”或者“ap”的记录，SQL 语句如下：

```sh
mysql> SELECT * FROM fruits WHERE f_name REGEXP 'on|ap';
```

之前介绍过，LIKE 运算符也可以匹配指定的字符串，但与 REGEXP 不同，LIKE 匹配的字符串如果在文本中间出现，则找不到它，相应的行也不会返回。REGEXP 在文本内进行匹配，如果被匹配的字符串在文本中出现，REGEXP 将会找到它，相应的行也会被返回。对比结果如下所示。

在 fruits 表中，使用 LIKE 运算符查询 f_name 字段值为“on”的记录，SQL 语句如下：

```sh
mysql> SELECT * FROM fruits WHERE f_name like 'on';
Empty set(0.00 sec)
```

**6. 匹配指定字符中的任意一个**

方括号“[]”指定一个字符集合，只匹配其中任何一个字符，即为所查找的文本。

在 fruits 表中，查找 f_name 字段中包含字母‘o’或者‘t’的记录，SQL 语句如下：

```sh
mysql> SELECT * FROM fruits WHERE f_name REGEXP '[ot]';
```

在 fruits 表中，查询 s_id 字段中包含 4、5 或者 6 的记录，SQL 语句如下：

```sh
mysql> SELECT * FROM fruits WHERE s_id REGEXP '[456]';
```

**7. 匹配指定字符以外的字符**

`“[^字符集合]”`匹配不在指定集合中的任何字符。

在 fruits 表中，查询 f_id 字段中包含字母 a~e 和数字 1~2 以外字符的记录，SQL 语句如下：

```sh
mysql> SELECT * FROM fruits WHERE f_id REGEXP '[^a-e1-2]';
```

**8. 使用{n,}或者{n,m}来指定字符串连续出现的次数**

“字符串{n,}”表示至少匹配 n 次前面的字符；“字符串{n,m}”表示匹配前面的字符串不少于 n 次，不多于 m 次。例如，a{2,}表示字母 a 连续出现至少 2 次，也可以大于 2 次；a{2,4}表示字母 a 连续出现最少 2 次，最多不能超过 4 次。

在 fruits 表中，查询 f_name 字段值出现字母‘x’至少 2 次的记录，SQL 语句如下：

```sh
mysql> SELECT * FROM fruits WHERE f_name REGEXP 'x{2,}';
```

在 fruits 表中，查询 f_name 字段值出现字符串“ba”最少 1 次、最多 3 次的记录，SQL 语句如下：

```sh
mysql> SELECT * FROM fruits WHERE f_name REGEXP 'ba{1,3}';
```

# 第 5 章 排序与分页

## 1. 排序数据

### 1.1 排序规则

- 使用 ORDER BY 子句排序

  - **ASC（ascend）: 升序**

  - **DESC（descend）:降序**

- **ORDER BY 子句在 SELECT 语句的结尾。**

### 1.2 单列排序

```sql
SELECT   last_name, job_id, department_id, hire_date
FROM     employees
ORDER BY hire_date ;
```

![单列排序](https://img-blog.csdnimg.cn/e8a8f71b160045f49fe57fb6b76f2ab5.png)

```sql
SELECT   last_name, job_id, department_id, hire_date
FROM     employees
ORDER BY hire_date DESC ;
```

![单列排序](https://img-blog.csdnimg.cn/c4fbd900adbb4007bc63a47757b5e36f.png)

```sql
SELECT employee_id, last_name, salary*12 annsal
FROM   employees
ORDER BY annsal;
```

![单列排序](https://img-blog.csdnimg.cn/80de34c07c7f4e3196177ac339f210c6.png)

### 1.3 多列排序

```sql
SELECT last_name, department_id, salary
FROM   employees
ORDER BY department_id, salary DESC;
```

![多列排序](https://img-blog.csdnimg.cn/6058c8e3c5b3429eaab89d60f66bb022.png)

- 可以使用不在 SELECT 列表中的列排序。

- 在对多列进行排序的时候，首先排序的第一列必须有相同的列值，才会对第二列进行排序。如果第一列数据中所有值都是唯一的，将不再对第二列进行排序。

## 2. 分页

### 2.1 背景

背景 1：查询返回的记录太多了，查看起来很不方便，怎么样能够实现分页查询呢？

背景 2：表里有 4 条数据，我们只想要显示第 2、3 条数据怎么办呢？

### 2.2 实现规则

- 分页原理

  所谓分页显示，就是将数据库中的结果集，一段一段显示出来需要的条件。

- **MySQL 中使用 LIMIT 实现分页。**

- 格式：

  > LIMIT [位置偏移量,] 行数

第一个“位置偏移量”参数指示 MySQL 从哪一行开始显示，是一个可选参数，如果不指定“位置偏移量”，将会从表中的第一条记录开始（第一条记录的位置偏移量是 0，第二条记录的位置偏移量是 1，以此类推）；第二个参数“行数”指示返回的记录条数。

- 举例

  > \# 前 10 条记录：
  > SELECT \_ FROM 表名 LIMIT 0,10;

  或者

  > SELECT \_ FROM 表名 LIMIT 10;
  >
  > \# 第 11 至 20 条记录：
  > SELECT \* FROM 表名 LIMIT 10,10;
  >
  > \# 第 21 至 30 条记录：
  > SELECT \* FROM 表名 LIMIT 20,10;

  > MySQL 8.0 中可以使用“LIMIT 3 OFFSET 4”，意思是获取从第 5 条记录开始后面的 3 条记录，和“LIMIT 4,3;”返回的结果相同。

- **分页显式公式：（当前页数-1）\*每页条数，每页条数**

  ```sql
  SELECT * FROM table
  LIMIT(PageNo - 1)*PageSize,PageSize;
  ```

- **注意：LIMIT 子句必须放在整个 SELECT 语句的最后！**
- 使用 LIMIT 的好处。

约束返回结果的数量可以`减少数据表的网络传输量`，也可以`提升查询效率`。如果我们知道返回结果只有 1 条，就可以使用`LIMIT 1`，告诉 SELECT 语句只需要返回一条记录即可。这样的好处就是 SELECT 不需要扫描完整的表，只需要检索到一条符合条件的记录即可返回。

### 2.3 拓展

在不同的 DBMS 中使用的关键字可能不同。在 MySQL、PostgreSQL、MariaDB 和 SQLite 中使用 LIMIT 关键字，而且需要放到 SELECT 语句的最后面。

- 如果是 SQL Server 和 Access，需要使用 `TOP` 关键字，比如：

  ```sql
  SELECT TOP 5 name, hp_max FROM heros ORDER BY hp_max DESC
  ```

- 如果是 DB2，使用`FETCH FIRST 5 ROWS ONLY`这样的关键字：

  ```sql
  SELECT name, hp_max FROM heros ORDER BY hp_max DESC FETCH FIRST 5 ROWS ONLY
  ```

- 如果是 Oracle，你需要基于 `ROWNUM` 来统计行数：

  ```sql
  SELECT rownum,last_name,salary FROM employees WHERE rownum < 5 ORDER BY salary DESC;
  ```

  需要说明的是，这条语句是先取出来前 5 条数据行，然后再按照 hp_max 从高到低的顺序进行排序。但这样产生的结果和上述方法的并不一样。我会在后面讲到子查询，你可以使用

  ```sql
  SELECT rownum, last_name,salary
  FROM
  (
      SELECT last_name,salary
      FROM employees
      ORDER BY salary DESC
  )
  WHERE rownum < 10;
  ```

  得到与上述方法一致的结果。

# 第 6 章 多表查询

多表查询，也称为关联查询，指两个或更多个表一起完成查询操作。

前提条件：这些一起查询的表之间是有关系的（一对一、一对多），它们之间一定是有关联字段，这个关联字段可能建立了外键，也可能没有建立外键。比如：员工表和部门表，这两个表依靠“部门编号”进行关联。

## 1. 一个案例引发的多表连接

### 1.1 案例说明

![案例说明](https://img-blog.csdnimg.cn/21a608ba378b4879a43bdc2c5e17a74b.png)

从多个表中获取数据：

![案例说明](https://img-blog.csdnimg.cn/a5027c829ca54ba89534e49a64ffed04.png)

```sql
# 案例：查询员工的姓名及其部门名称
SELECT last_name, department_name
FROM employees, departments;
```

![案例说明](https://img-blog.csdnimg.cn/b2fdd0f2a06247fbb5597098d5c25ade.png)

查询结果：

```sh
+-----------+----------------------+
| last_name | department_name      |
+-----------+----------------------+
| King      | Administration       |
| King      | Marketing            |
| King      | Purchasing           |
| King      | Human Resources      |
| King      | Shipping             |
| King      | IT                   |
| King      | Public Relations     |
| King      | Sales                |
| King      | Executive            |
| King      | Finance              |
| King      | Accounting           |
| King      | Treasury             |
...
| Gietz     | IT Support           |
| Gietz     | NOC                  |
| Gietz     | IT Helpdesk          |
| Gietz     | Government Sales     |
| Gietz     | Retail Sales         |
| Gietz     | Recruiting           |
| Gietz     | Payroll              |
+-----------+----------------------+
2889 rows in set (0.01 sec)
```

**分析错误情况：**

```sql
# 输出 107 行
SELECT COUNT(employee_id) FROM employees;

# 输出 27 行
SELECT COUNT(department_id)FROM departments;

SELECT 107*27 FROM dual;
```

我们把上述多表查询中出现的问题称为：笛卡尔积的错误。

### 1.2 笛卡尔积（或交叉连接）的理解

笛卡尔乘积是一个数学运算。假设我有两个集合 X 和 Y，那么 X 和 Y 的笛卡尔积就是 X 和 Y 的所有可能组合，也就是第一个对象来自于 X，第二个对象来自于 Y 的所有可能。组合的个数即为两个集合中元素个数的乘积数。

![笛卡尔积（或交叉连接）的理解](https://img-blog.csdnimg.cn/a98f9393546444f797b40575735a506d.png)

SQL92 中，笛卡尔积也称为`交叉连接`，英文是 `CROSS JOIN`。在 SQL99 中也是使用 CROSS JOIN 表示交叉连接。它的作用就是可以把任意表进行连接，即使这两张表不相关。在 MySQL 中如下情况会出现笛卡尔积：

```sql
# 查询员工姓名和所在部门名称
SELECT last_name,department_name FROM employees,departments;
SELECT last_name,department_name FROM employees CROSS JOIN departments;
SELECT last_name,department_name FROM employees INNER JOIN departments;
SELECT last_name,department_name FROM employees JOIN departments;
```

### 1.3 案例分析与问题解决

- **笛卡尔积的错误会在下面条件下产生**：

  - 省略多个表的连接条件（或关联条件）。

  - 连接条件（或关联条件）无效。

  - 所有表中的所有行互相连接。

- 为了避免笛卡尔积， 可以**在 WHERE 加入有效的连接条件。**

- 加入连接条件后，查询语法：

  ```sql
  SELECT	table1.column, table2.column
  FROM	table1, table2
  #连接条件
  WHERE	table1.column1 = table2.column2;
  ```

  - **在 WHERE 子句中写入连接条件。**

- 正确写法：

  ```sql
  # 案例：查询员工的姓名及其部门名称
  SELECT last_name, department_name
  FROM employees, departments
  WHERE employees.department_id = departments.department_id;
  ```

- **在表中有相同列时，在列名之前加上表名前缀。**

## 2. 多表查询分类讲解

### 2.1 分类 1：等值连接 vs 非等值连接

#### 2.1.1 等值连接

![等值连接](https://img-blog.csdnimg.cn/7f466768620a4a26af73a3692c5b3d3e.png)

```sql
SELECT employees.employee_id, employees.last_name,
       employees.department_id, departments.department_id,
       departments.location_id
FROM   employees, departments
WHERE  employees.department_id = departments.department_id;
```

![等值连接](https://img-blog.csdnimg.cn/fefcf83e02c64a5891524dc025196831.png)

**拓展 1：多个连接条件与 AND 操作符**

![拓展 1：多个连接条件与 AND 操作符](https://img-blog.csdnimg.cn/c95b803e39cf4959a2a8d923e063e525.png)

**拓展 2：区分重复的列名**

- **多个表中有相同列时，必须在列名之前加上表名前缀。**

- 在不同表中具有相同列名的列可以用`表名`加以区分。

  ```sql
  SELECT employees.last_name, departments.department_name,employees.department_id
  FROM employees, departments
  WHERE employees.department_id = departments.department_id;
  ```

**拓展 3：表的别名**

- 使用别名可以简化查询。

- 列名前使用表名前缀可以提高查询效率。

  ```sql
  SELECT e.employee_id, e.last_name, e.department_id,
        d.department_id, d.location_id
  FROM   employees e , departments d
  WHERE  e.department_id = d.department_id;
  ```

  > 需要注意的是，如果我们使用了表的别名，在查询字段中、过滤条件中就只能使用别名进行代替，不能使用原有的表名，否则就会报错。

  > `阿里开发规范`：
  >
  > 【`强制`】对于数据库中表记录的查询和变更，只要涉及多个表，都需要在列名前加表的别名（或 表名）进行限定。
  >
  > 【`说明`】：对多表进行查询记录、更新记录、删除记录时，如果对操作列没有限定表的别名（或表名），并且操作列在多个表中存在时，就会抛异常。
  >
  > 【`正例`】：select t1.name from table_first as t1 , table_second as t2 where t1.id=t2.id;
  >
  > 【`反例`】：在某业务中，由于多表关联查询语句没有加表的别名（或表名）的限制，正常运行两年后，最近在 某个表中增加一个同名字段，在预发布环境做数据库变更后，线上查询语句出现出 1052 异常：Column 'name' in field list is ambiguous。

**拓展 4：连接多个表**

![拓展 4：连接多个表](https://img-blog.csdnimg.cn/9391cbbd82b74199bfcce5e87be08461.png)

**总结：连接 n 个表,至少需要 n-1 个连接条件。** 比如，连接三个表，至少需要两个连接条件。

练习：查询出公司员工的 last_name,department_name, city

#### 2.1.2 非等值连接

![非等值连接](https://img-blog.csdnimg.cn/45494f1e84244b7f8017efcbc958153f.png)

```sql
SELECT e.last_name, e.salary, j.grade_level
FROM   employees e, job_grades j
WHERE  e.salary BETWEEN j.lowest_sal AND j.highest_sal;
```

![非等值连接](https://img-blog.csdnimg.cn/72026e5a32d24ddc9c8693b9e50e140f.png)

### 2.2 分类 2：自连接 vs 非自连接

![分类 2：自连接 vs 非自连接](https://img-blog.csdnimg.cn/3f058bf95e7d40bab5b2ffa1b92effde.png)

- 当 table1 和 table2 本质上是同一张表，只是用取别名的方式虚拟成两张表以代表不同的意义。然后两个表再进行内连接，外连接等查询。

**题目：查询 employees 表，返回“Xxx works for Xxx”**

```sql
SELECT CONCAT(worker.last_name ,' works for '
       , manager.last_name)
FROM   employees worker, employees manager
WHERE  worker.manager_id = manager.employee_id ;
```

![分类 2：自连接 vs 非自连接](https://img-blog.csdnimg.cn/1cfb22f3cbe142b4b607c56e81af4cc1.png)

练习：查询出 last_name 为 ‘Chen’ 的员工的 manager 的信息。

### 2.3 分类 3：内连接 vs 外连接

除了查询满足条件的记录以外，外连接还可以查询某一方不满足条件的记录。

![分类 3：内连接 vs 外连接](https://img-blog.csdnimg.cn/2cbd9d3bf34c4e61a276561998019a38.png)

- 内连接: 合并具有同一列的两个以上的表的行, **结果集中不包含一个表与另一个表不匹配的行**

- 外连接: 两个表在连接过程中除了返回满足连接条件的行以外**还返回左（或右）表中不满足条件的行** **，这种连接称为左（或右） 外连接**。没有匹配的行时, 结果表中相应的列为空(NULL)。

- 如果是左外连接，则连接条件中左边的表也称为`主表`，右边的表称为`从表`。

  如果是右外连接，则连接条件中右边的表也称为`主表`，左边的表称为`从表`。

#### 2.3.1 SQL92：使用(+)创建连接

- 在 SQL92 中采用（+）代表从表所在的位置。即左或右外连接中，(+) 表示哪个是从表。

- Oracle 对 SQL92 支持较好，而 MySQL 则不支持 SQL92 的外连接。

  ```sql
  # 左外连接
  SELECT last_name,department_name
  FROM employees ,departments
  WHERE employees.department_id = departments.department_id(+);

  # 右外连接
  SELECT last_name,department_name
  FROM employees ,departments
  WHERE employees.department_id(+) = departments.department_id;
  ```

- 而且在 SQL92 中，只有左外连接和右外连接，没有满（或全）外连接。

## 3. SQL99 语法实现多表查询

### 3.1 基本语法

- 使用 JOIN...ON 子句创建连接的语法结构：

  ```sql
  SELECT table1.column, table2.column,table3.column
  FROM table1
      JOIN table2 ON table1 和 table2 的连接条件
          JOIN table3 ON table2 和 table3 的连接条件
  ```

  它的嵌套逻辑类似我们使用的 FOR 循环：

  ```sql
  for t1 in table1:
      for t2 in table2:
         if condition1:
             for t3 in table3:
                if condition2:
                    output t1 + t2 + t3
  ```

  SQL99 采用的这种嵌套结构非常清爽、层次性更强、可读性更强，即使再多的表进行连接也都清晰可见。如果你采用 SQL92，可读性就会大打折扣。

- 语法说明：

  - **可以使用** **ON** **子句指定额外的连接条件**。

  - 这个连接条件是与其它条件分开的。

  - **ON** **子句使语句具有更高的易读性**。

  - 关键字 JOIN、INNER JOIN、CROSS JOIN 的含义是一样的，都表示内连接。

### 3.2 内连接(INNER JOIN)的实现

- 语法：

  > SELECT 字段列表
  > FROM A 表 INNER JOIN B 表
  > ON 关联条件
  > WHERE 等其他子句;

题目 1：

```sql
SELECT e.employee_id, e.last_name, e.department_id,
       d.department_id, d.location_id
FROM   employees e JOIN departments d
ON     (e.department_id = d.department_id);
```

![内连接(INNER JOIN)的实现](https://img-blog.csdnimg.cn/a3e46517f38b4400b33ce0e042e9d9f0.png)

题目 2：

```sql
SELECT employee_id, city, department_name
FROM   employees e
JOIN   departments d
ON     d.department_id = e.department_id
JOIN   locations l
ON     d.location_id = l.location_id;
```

![内连接(INNER JOIN)的实现](https://img-blog.csdnimg.cn/141118cea31649bcaac6ef9b1d2083f2.png)

### 3.3 外连接(OUTER JOIN)的实现

#### 3.3.1 左外连接(LEFT OUTER JOIN)

- 语法：

  > \# 实现查询结果是 A
  > SELECT 字段列表
  > FROM A 表 LEFT JOIN B 表
  > ON 关联条件
  > WHERE 等其他子句;

- 举例：

  ```sql
  SELECT e.last_name, e.department_id, d.department_name
  FROM   employees e
  LEFT OUTER JOIN departments d
  ON   (e.department_id = d.department_id) ;
  ```

  ![左外连接(LEFT OUTER JOIN)](https://img-blog.csdnimg.cn/9457baba84c6479cbba76cfda6b3ccf1.png)

#### 3.3.2 右外连接(RIGHT OUTER JOIN)

- 语法：

  > \# 实现查询结果是 B
  > SELECT 字段列表
  > FROM A 表 RIGHT JOIN B 表
  > ON 关联条件
  > WHERE 等其他子句;

- 举例：

  ```sql
  SELECT e.last_name, e.department_id, d.department_name
  FROM   employees e
  RIGHT OUTER JOIN departments d
  ON    (e.department_id = d.department_id) ;
  ```

  ![右外连接(RIGHT OUTER JOIN)](https://img-blog.csdnimg.cn/90e07bffe8c34a08a6a100051940833f.png)

> 需要注意的是，LEFT JOIN 和 RIGHT JOIN 只存在于 SQL99 及以后的标准中，在 SQL92 中不存在，只能用 (+) 表示。

#### 3.3.3 满外连接(FULL OUTER JOIN)

- 满外连接的结果 = 左右表匹配的数据 + 左表没有匹配到的数据 + 右表没有匹配到的数据。

- SQL99 是支持满外连接的。使用 FULL JOIN 或 FULL OUTER JOIN 来实现。

- 需要注意的是，MySQL 不支持 FULL JOIN，但是可以用 LEFT JOIN **UNION** RIGHT join 代替。

## 4. UNION 的使用

**合并查询结果**

利用 UNION 关键字，可以给出多条 SELECT 语句，并将它们的结果组合成单个结果集。合并时，两个表对应的列数和数据类型必须相同，并且相互对应。各个 SELECT 语句之间使用 UNION 或 UNION ALL 关键字分隔。

语法格式：

> SELECT column,... FROM table1
> UNION [ALL]
> SELECT column,... FROM table2

**UNION 操作符**

![UNION 操作符](https://img-blog.csdnimg.cn/638a55d103854e39b75873e65adfc0eb.png)

UNION 操作符返回两个查询的结果集的并集，去除重复记录。

**UNION ALL 操作符**

![UNION ALL 操作符](https://img-blog.csdnimg.cn/3c48386366f444b9bd85ae2bd25b9545.png)

UNION ALL 操作符返回两个查询的结果集的并集。对于两个结果集的重复部分，不去重。

> 注意：执行 UNION ALL 语句时所需要的资源比 UNION 语句少。如果明确知道合并数据后的结果数据不存在重复数据，或者不需要去除重复的数据，则尽量使用 UNION ALL 语句，以提高数据查询的效率。

举例：查询部门编号>90 或邮箱包含 a 的员工信息

```sql
# 方式 1
SELECT * FROM employees WHERE email LIKE '%a%' OR department_id>90;
```

```sql
# 方式 2
SELECT * FROM employees  WHERE email LIKE '%a%'
UNION
SELECT * FROM employees  WHERE department_id>90;
```

举例：查询中国用户中男性的信息以及美国用户中年男性的用户信息

```sql
SELECT id,cname FROM t_chinamale WHERE csex='男'
UNION ALL
SELECT id,tname FROM t_usmale WHERE tGender='male';
```

## 5. 7 种 SQL JOINS 的实现

![7 种 SQL JOINS 的实现](https://img-blog.csdnimg.cn/1efd3ef2fc4d4a6f9e9bc01c00862ddc.png)

### 5.7.1 代码实现

```sql
# 中图：内连接 A ∩ B
SELECT employee_id,last_name,department_name
FROM employees e JOIN departments d
ON e.`department_id` = d.`department_id`;
```

```sql
# 左上图：左外连接
SELECT employee_id,last_name,department_name
FROM employees e LEFT JOIN departments d
ON e.`department_id` = d.`department_id`;
```

```sql
# 右上图：右外连接
SELECT employee_id,last_name,department_name
FROM employees e RIGHT JOIN departments d
ON e.`department_id` = d.`department_id`;
```

```sql
# 左中图：A - A ∩ B
SELECT employee_id,last_name,department_name
FROM employees e LEFT JOIN departments d
ON e.`department_id` = d.`department_id`
WHERE d.`department_id` IS NULL
```

```sql
# 右中图：B - A ∩ B
SELECT employee_id,last_name,department_name
FROM employees e RIGHT JOIN departments d
ON e.`department_id` = d.`department_id`
WHERE e.`department_id` IS NULL
```

```sql
# 左下图：满外连接
# 左中图 + 右上图：A ∪ B
SELECT employee_id,last_name,department_name
FROM employees e LEFT JOIN departments d
ON e.`department_id` = d.`department_id`
WHERE d.`department_id` IS NULL
#没有去重操作，效率高
UNION ALL
SELECT employee_id,last_name,department_name
FROM employees e RIGHT JOIN departments d
ON e.`department_id` = d.`department_id`;
```

```sql
# 右下图
# 左中图 + 右中图：A ∪ B - A ∩ B 或者 (A - A ∩ B) ∪ （B - A ∩ B）
SELECT employee_id,last_name,department_name
FROM employees e LEFT JOIN departments d
ON e.`department_id` = d.`department_id`
WHERE d.`department_id` IS NULL
UNION ALL
SELECT employee_id,last_name,department_name
FROM employees e RIGHT JOIN departments d
ON e.`department_id` = d.`department_id`
WHERE e.`department_id` IS NULL
```

### 5.7.2 语法格式小结

- 左中图

  > \# 实现 A - A ∩ B
  > select 字段列表
  > from A 表 left join B 表
  > on 关联条件
  > where 从表关联字段 is null and 等其他子句;

- 右中图

  > \# 实现 B - A ∩ B
  > select 字段列表
  > from A 表 right join B 表
  > on 关联条件
  > where 从表关联字段 is null and 等其他子句;

- 左下图

  > \# 实现查询结果是 A ∪ B
  > \# 用左外的 A，union 右外的 B
  > select 字段列表
  > from A 表 left join B 表
  > on 关联条件
  > where 等其他子句
  >
  > union
  >
  > select 字段列表
  > from A 表 right join B 表
  > on 关联条件
  > where 等其他子句;

- 右下图

  > \# 实现 A ∪ B - A ∩ B 或 (A - A ∩ B) ∪ (B - A ∩ B)
  > \# 使用左外的 (A - A ∩ B) union 右外的（B - A ∩ B）
  > select 字段列表
  > from A 表 left join B 表
  > on 关联条件
  > where 从表关联字段 is null and 等其他子句
  >
  > union
  >
  > select 字段列表
  > from A 表 right join B 表
  > on 关联条件
  > where 从表关联字段 is null and 等其他子句

## 6. SQL99 语法新特性

### 6.1 自然连接

SQL99 在 SQL92 的基础上提供了一些特殊语法，比如 `NATURAL JOIN` 用来表示自然连接。我们可以把自然连接理解为 SQL92 中的等值连接。它会帮你自动查询两张连接表中`所有相同的字段`，然后进行`等值连接`。

在 SQL92 标准中：

```sql
SELECT employee_id,last_name,department_name
FROM employees e JOIN departments d
ON e.`department_id` = d.`department_id`
AND e.`manager_id` = d.`manager_id`;
```

在 SQL99 中你可以写成：

```sql
SELECT employee_id,last_name,department_name
FROM employees e NATURAL JOIN departments d;
```

### 6.2 USING 连接

当我们进行连接的时候，SQL99 还支持使用 USING 指定数据表里的`同名字段`进行等值连接。但是只能配合 JOIN 一起使用。比如：

```sql
SELECT employee_id,last_name,department_name
FROM employees e JOIN departments d
USING (department_id);
```

你能看出与自然连接 NATURAL JOIN 不同的是，USING 指定了具体的相同的字段名称，你需要在 USING 的括号 () 中填入要指定的同名字段。同时使用 `JOIN...USING` 可以简化 JOIN ON 的等值连接。它与下面的 SQL 查询结果是相同的：

```sql
SELECT employee_id,last_name,department_name
FROM employees e ,departments d
WHERE e.department_id = d.department_id;
```

## 7. 章节小结

表连接的约束条件可以有三种方式：WHERE, ON, USING

- WHERE：适用于所有关联查询。

- `ON`：只能和 JOIN 一起使用，只能写关联条件。虽然关联条件可以并到 WHERE 中和其他条件一起写，但分开写可读性更好。

- USING：只能和 JOIN 一起使用，而且要求**两个**关联字段在关联表中名称一致，而且只能表示关联字段值相等。

```sql
# 关联条件
# 把关联条件写在 WHERE 后面
SELECT last_name,department_name
FROM employees,departments
WHERE employees.department_id = departments.department_id;

# 把关联条件写在 ON 后面，只能和 JOIN 一起使用
SELECT last_name,department_name
FROM employees INNER JOIN departments
ON employees.department_id = departments.department_id;

SELECT last_name,department_name
FROM employees CROSS JOIN departments
ON employees.department_id = departments.department_id;

SELECT last_name,department_name
FROM employees JOIN departments
ON employees.department_id = departments.department_id;

# 把关联字段写在 USING() 中，只能和 JOIN 一起使用
# 而且两个表中的关联字段必须名称相同，而且只能表示 =
# 查询员工姓名与基本工资
SELECT last_name,job_title
FROM employees INNER JOIN jobs USING(job_id);

# n 张表关联，需要 n - 1 个关联条件
# 查询员工姓名，基本工资，部门名称
SELECT last_name,job_title,department_name FROM employees,departments,jobs
WHERE employees.department_id = departments.department_id
AND employees.job_id = jobs.job_id;

SELECT last_name,job_title,department_name
FROM employees INNER JOIN departments INNER JOIN jobs
ON employees.department_id = departments.department_id
AND employees.job_id = jobs.job_id;
```

**注意：**

我们要`控制连接表的数量`。多表连接就相当于嵌套 for 循环一样，非常消耗资源，会让 SQL 查询性能下降得很严重，因此不要连接不必要的表。在许多 DBMS 中，也都会有最大连接表的限制。

> 【强制】超过三个表禁止 join。需要 join 的字段，数据类型保持绝对一致；多表关联查询时， 保证被关联的字段需要有索引。
>
> 【说明】即使双表 join 也要注意表索引、SQL 性能。
>
> 【来源】阿里巴巴《Java 开发手册》

## 8. 附录：常用的 SQL 标准有哪些

在正式开始讲连接表的种类时，我们首先需要知道 SQL 存在不同版本的标准规范，因为不同规范下的表连接操作是有区别的。

SQL 有两个主要的标准，分别是 `SQL92` 和 `SQL99`。92 和 99 代表了标准提出的时间，SQL92 就是 92 年提出的标准规范。当然除了 SQL92 和 SQL99 以外，还存在 SQL-86、SQL-89、SQL:2003、SQL:2008、SQL:2011 和 SQL:2016 等其他的标准。

这么多标准，到底该学习哪个呢？**实际上最重要的 SQL 标准就是 SQL92 和 SQL99**。一般来说 SQL92 的形式更简单，但是写的 SQL 语句会比较长，可读性较差。而 SQL99 相比于 SQL92 来说，语法更加复杂，但可读性更强。我们从这两个标准发布的页数也能看出，SQL92 的标准有 500 页，而 SQL99 标准超过了 1000 页。实际上从 SQL99 之后，很少有人能掌握所有内容，因为确实太多了。就好比我们使用 Windows、Linux 和 Office 的时候，很少有人能掌握全部内容一样。我们只需要掌握一些核心的功能，满足日常工作的需求即可。

**SQL92 和 SQL99 是经典的 SQL 标准，也分别叫做 SQL-2 和 SQL-3 标准。** 也正是在这两个标准发布之后，SQL 影响力越来越大，甚至超越了数据库领域。现如今 SQL 已经不仅仅是数据库领域的主流语言，还是信息领域中信息处理的主流语言。在图形检索、图像检索以及语音检索中都能看到 SQL 语言的使用。

# 第 7 章 单行函数

## 1. 函数的理解

### 1.1 什么是函数

函数在计算机语言的使用中贯穿始终，函数的作用是什么呢？它可以把我们经常使用的代码封装起来，需要的时候直接调用即可。这样既`提高了代码效率`，又`提高了可维护性`。在 SQL 中我们也可以使用函数对检索出来的数据进行函数操作。使用这些函数，可以极大地`提高用户对数据库的管理效率`。

![什么是函数](https://img-blog.csdnimg.cn/5c41352ca33042898c37da33da01ad32.png)

从函数定义的角度出发，我们可以将函数分成`内置函数`和`自定义函数`。在 SQL 语言中，同样也包括了内置函数和自定义函数。内置函数是系统内置的通用函数，而自定义函数是我们根据自己的需要编写的，本章及下一章讲解的是 SQL 的内置函数。

### 1.2 不同 DBMS 函数的差异

我们在使用 SQL 语言的时候，不是直接和这门语言打交道，而是通过它使用不同的数据库软件，即 DBMS。**DBMS 之间的差异性很大，远大于同一个语言不同版本之间的差异。**实际上，只有很少的函数是被 DBMS 同时支持的。比如，大多数 DBMS 使用（||）或者（+）来做拼接符，而在 MySQL 中的字符串拼接函数为 concat()。大部分 DBMS 会有自己特定的函数，这就意味着**采用 SQL 函数的代码可移植性是很差的**，因此在使用函数的时候需要特别注意。

### 1.3 MySQL 的内置函数及分类

MySQL 提供了丰富的内置函数，这些函数使得数据的维护与管理更加方便，能够更好地提供数据的分析与统计功能，在一定程度上提高了开发人员进行数据分析与统计的效率。

MySQL 提供的内置函数从`实现的功能角度`可以分为数值函数、字符串函数、日期和时间函数、流程控制函数、加密与解密函数、获取 MySQL 信息函数、聚合函数等。这里，我将这些丰富的内置函数再分为两类：`单行函数`、`聚合函数（或分组函数）`。

**两种 SQL 函数**

![两种 SQL 函数](https://img-blog.csdnimg.cn/eabeb60e61fa47439ff9e26cf9a1c1f5.png)

**单行函数**

- 操作数据对象。

- 接受参数返回一个结果。

- **只对一行进行变换。**

- **每行返回一个结果。**

- 可以嵌套。

- 参数可以是一列或一个值。

## 2. 数值函数

### 2.1 基本函数

| 函数                   | 用法                                                                      |
| ---------------------- | ------------------------------------------------------------------------- |
| ABS(x)                 | 返回 x 的绝对值。                                                         |
| SIGN(X)                | 返回 X 的符号。正数返回 1，负数返回-1，0 返回 0。                         |
| PI()                   | 返回圆周率的值。                                                          |
| CEIL(x)，CEILING(x)    | 返回大于或等于某个值的最小整数。                                          |
| FLOOR(x)               | 返回小于或等于某个值的最大整数。                                          |
| LEAST(e1,e2,e3 ...)    | 返回列表中的最小值。                                                      |
| GREATEST(e1,e2,e3 ...) | 返回列表中的最大值。                                                      |
| MOD(x,y)               | 返回 X 除以 Y 后的余数。                                                  |
| RAND()                 | 返回 0~1 的随机值。                                                       |
| RAND(x)                | 返回 0~1 的随机值，其中 x 的值用作种子值，相同的 X 值会产生相同的随机数。 |
| ROUND(x)               | 返回一个对 x 的值进行四舍五入后，最接近于 X 的整数。                      |
| ROUND(x,y)             | 返回一个对 x 的值进行四舍五入后最接近 X 的值，并保留到小数点后面 Y 位。   |
| TRUNCATE(x,y)          | 返回数字 x 截断为 y 位小数的结果。                                        |
| SQRT(x)                | 返回 x 的平方根。当 X 的值为负数时，返回 NULL。                           |

举例：

```sql
SELECT ABS(-123),ABS(32),SIGN(-23),SIGN(43),PI(),CEIL(32.32),CEILING(-43.23),FLOOR(32.32),
FLOOR(-43.23),MOD(12,5)
FROM DUAL;
```

![基本函数](https://img-blog.csdnimg.cn/3c77793bcff24002b8182225a7d53059.png)

```sql
SELECT RAND(),RAND(),RAND(10),RAND(10),RAND(-1),RAND(-1)
FROM DUAL;
```

![基本函数](https://img-blog.csdnimg.cn/03386225bf4748639a01954ed833fe12.png)

```sql
SELECT ROUND(12.33),ROUND(12.343,2),ROUND(12.324,-1),TRUNCATE(12.66,1),TRUNCATE(12.66,-1)
FROM DUAL;
```

![基本函数](https://img-blog.csdnimg.cn/9fb565db0d394299a696caeb526f5b0e.png)

### 2.2 角度与弧度互换函数

| 函数       | 用法                                      |
| ---------- | ----------------------------------------- |
| RADIANS(x) | 将角度转化为弧度，其中，参数 x 为角度值。 |
| DEGREES(x) | 将弧度转化为角度，其中，参数 x 为弧度值。 |

```sql
SELECT RADIANS(30),RADIANS(60),RADIANS(90),DEGREES(2*PI()),DEGREES(RADIANS(90))
FROM DUAL;
```

### 2.3 三角函数

| 函数       | 用法                                                                               |
| ---------- | ---------------------------------------------------------------------------------- |
| SIN(x)     | 返回 x 的正弦值，其中，参数 x 为弧度值。                                           |
| ASIN(x)    | 返回 x 的反正弦值，即获取正弦为 x 的值。如果 x 的值不在-1 到 1 之间，则返回 NULL。 |
| COS(x)     | 返回 x 的余弦值，其中，参数 x 为弧度值。                                           |
| ACOS(x)    | 返回 x 的反余弦值，即获取余弦为 x 的值。如果 x 的值不在-1 到 1 之间，则返回 NULL。 |
| TAN(x)     | 返回 x 的正切值，其中，参数 x 为弧度值。                                           |
| ATAN(x)    | 返回 x 的反正切值，即返回正切值为 x 的值。                                         |
| ATAN2(m,n) | 返回两个参数的反正切值。                                                           |
| COT(x)     | 返回 x 的余切值，其中，X 为弧度值。                                                |

举例：

ATAN2(M,N)函数返回两个参数的反正切值。
与 ATAN(X)函数相比，ATAN2(M,N)需要两个参数，例如有两个点 point(x1,y1)和 point(x2,y2)，使用 ATAN(X)函数计算反正切值为 ATAN((y2-y1)/(x2-x1))，使用 ATAN2(M,N)计算反正切值则为 ATAN2(y2-y1,x2-x1)。由使用方式可以看出，当 x2-x1 等于 0 时，ATAN(X)函数会报错，而 ATAN2(M,N)函数则仍然可以计算。

ATAN2(M,N)函数的使用示例如下：

```sql
SELECT SIN(RADIANS(30)),DEGREES(ASIN(1)),TAN(RADIANS(45)),DEGREES(ATAN(1)),DEGREES(ATAN2(1,1))
FROM DUAL;
```

![三角函数](https://img-blog.csdnimg.cn/97f79c73fe70476d931cfab0025321e8.png)

### 2.4 指数与对数

| 函数                 | 用法                                                         |
| -------------------- | ------------------------------------------------------------ |
| POW(x,y)，POWER(X,Y) | 返回 x 的 y 次方。                                           |
| EXP(X)               | 返回 e 的 X 次方，其中 e 是一个常数，2.718281828459045。     |
| LN(X)，LOG(X)        | 返回以 e 为底的 X 的对数，当 X <= 0 时，返回的结果为 NULL。  |
| LOG10(X)             | 返回以 10 为底的 X 的对数，当 X <= 0 时，返回的结果为 NULL。 |
| LOG2(X)              | 返回以 2 为底的 X 的对数，当 X <= 0 时，返回 NULL。          |

```sh
mysql> SELECT POW(2,5),POWER(2,4),EXP(2),LN(10),LOG10(10),LOG2(4)
    -> FROM DUAL;
+----------+------------+------------------+-------------------+-----------+---------+
| POW(2,5) | POWER(2,4) | EXP(2)           | LN(10)            | LOG10(10) | LOG2(4) |
+----------+------------+------------------+-------------------+-----------+---------+
|       32 |         16 | 7.38905609893065 | 2.302585092994046 |         1 |       2 |
+----------+------------+------------------+-------------------+-----------+---------+
1 row in set (0.00 sec)
```

### 2.5 进制间的转换

| 函数          | 用法                           |
| ------------- | ------------------------------ |
| BIN(x)        | 返回 x 的二进制编码。          |
| HEX(x)        | 返回 x 的十六进制编码。        |
| OCT(x)        | 返回 x 的八进制编码。          |
| CONV(x,f1,f2) | 返回 f1 进制数变成 f2 进制数。 |

```sh
mysql> SELECT BIN(10),HEX(10),OCT(10),CONV(10,2,8)
    -> FROM DUAL;
+---------+---------+---------+--------------+
| BIN(10) | HEX(10) | OCT(10) | CONV(10,2,8) |
+---------+---------+---------+--------------+
| 1010    | A       | 12      | 2            |
+---------+---------+---------+--------------+
1 row in set (0.00 sec)
```

## 3. 字符串函数

| 函数                              | 用法                                                                                                                     |
| --------------------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| ASCII(S)                          | 返回字符串 S 中的第一个字符的 ASCII 码值。                                                                               |
| CHAR_LENGTH(s)                    | 返回字符串 s 的字符数。作用与 CHARACTER_LENGTH(s)相同。                                                                  |
| LENGTH(s)                         | 返回字符串 s 的字节数，和字符集有关。                                                                                    |
| CONCAT(s1,s2,......,sn)           | 连接 s1,s2,......,sn 为一个字符串。                                                                                      |
| CONCAT_WS(x, s1,s2,......,sn)     | 同 CONCAT(s1,s2,...)函数，但是每个字符串之间要加上 x。                                                                   |
| INSERT(str, idx, len, replacestr) | 将字符串 str 从第 idx 位置开始，len 个字符长的子串替换为字符串 replacestr。                                              |
| REPLACE(str, a, b)                | 用字符串 b 替换字符串 str 中所有出现的字符串 a。                                                                         |
| UPPER(s) 或 UCASE(s)              | 将字符串 s 的所有字母转成大写字母。                                                                                      |
| LOWER(s) 或 LCASE(s)              | 将字符串 s 的所有字母转成小写字母。                                                                                      |
| LEFT(str,n)                       | 返回字符串 str 最左边的 n 个字符。                                                                                       |
| RIGHT(str,n)                      | 返回字符串 str 最右边的 n 个字符。                                                                                       |
| LPAD(str, len, pad)               | 用字符串 pad 对 str 最左边进行填充，直到 str 的长度为 len 个字符。                                                       |
| RPAD(str ,len, pad)               | 用字符串 pad 对 str 最右边进行填充，直到 str 的长度为 len 个字符。                                                       |
| LTRIM(s)                          | 去掉字符串 s 左侧的空格。                                                                                                |
| RTRIM(s)                          | 去掉字符串 s 右侧的空格。                                                                                                |
| TRIM(s)                           | 去掉字符串 s 开始与结尾的空格。                                                                                          |
| TRIM(s1 FROM s)                   | 去掉字符串 s 开始与结尾的 s1。                                                                                           |
| TRIM(LEADING s1 FROM s)           | 去掉字符串 s 开始处的 s1。                                                                                               |
| TRIM(TRAILING s1 FROM s)          | 去掉字符串 s 结尾处的 s1。                                                                                               |
| REPEAT(str, n)                    | 返回 str 重复 n 次的结果。                                                                                               |
| SPACE(n)                          | 返回 n 个空格。                                                                                                          |
| STRCMP(s1,s2)                     | 比较字符串 s1,s2 的 ASCII 码值的大小。                                                                                   |
| SUBSTR(s,index,len)               | 返回从字符串 s 的 index 位置其 len 个字符，作用与 SUBSTRING(s,n,len)、MID(s,n,len)相同。                                 |
| LOCATE(substr,str)                | 返回字符串 substr 在字符串 str 中首次出现的位置，作用于 POSITION(substr IN str)、INSTR(str,substr)相同。未找到，返回 0。 |
| ELT(m,s1,s2, ... ,sn)             | 返回指定位置的字符串，如果 m=1，则返回 s1，如果 m=2，则返回 s2，如果 m=n，则返回 sn。                                    |
| FIELD(s,s1,s2, ... ,sn)           | 返回字符串 s 在字符串列表中第一次出现的位置。                                                                            |
| FIND_IN_SET(s1,s2)                | 返回字符串 s1 在字符串 s2 中出现的位置。其中，字符串 s2 是一个以逗号分隔的字符串。                                       |
| REVERSE(s)                        | 返回 s 反转后的字符串。                                                                                                  |
| NULLIF(value1,value2)             | 比较两个字符串，如果 value1 与 value2 相等，则返回 NULL，否则返回 value1。                                               |

> 注意：MySQL 中，字符串的位置是从 1 开始的。

举例：

```sh
mysql> SELECT FIELD('mm','hello','msm','amma'),FIND_IN_SET('mm','hello,mm,amma')
    -> FROM DUAL;
+----------------------------------+-----------------------------------+
| FIELD('mm','hello','msm','amma') | FIND_IN_SET('mm','hello,mm,amma') |
+----------------------------------+-----------------------------------+
|                                0 |                                 2 |
+----------------------------------+-----------------------------------+
1 row in set (0.00 sec)
```

```sh
mysql> SELECT NULLIF('mysql','mysql'),NULLIF('mysql', '');
+-------------------------+---------------------+
| NULLIF('mysql','mysql') | NULLIF('mysql', '') |
+-------------------------+---------------------+
| NULL                    | mysql               |
+-------------------------+---------------------+
1 row in set (0.00 sec)
```

## 4. 日期和时间函数

### 4.1 获取日期、时间

| 函数                                                                         | 用法                             |
| ---------------------------------------------------------------------------- | -------------------------------- |
| **CURDATE()** ，CURRENT_DATE()                                               | 返回当前日期，只包含年、月、日。 |
| **CURTIME()** ， CURRENT_TIME()                                              | 返回当前时间，只包含时、分、秒。 |
| **NOW()** / SYSDATE() / CURRENT_TIMESTAMP() / LOCALTIME() / LOCALTIMESTAMP() | 返回当前系统日期和时间。         |
| UTC_DATE()                                                                   | 返回 UTC（世界标准时间）日期。   |
| UTC_TIME()                                                                   | 返回 UTC（世界标准时间）时间。   |

举例：

```sql
SELECT CURDATE(),CURTIME(),NOW(),SYSDATE()+0,UTC_DATE(),UTC_DATE()+0,UTC_TIME(),UTC_TIME()+0
FROM DUAL;
```

![获取日期、时间](https://img-blog.csdnimg.cn/7fc4c24ce6fb4a2bab00a1fab89b3a6a.png)

### 4.2 日期与时间戳的转换

| 函数                     | 用法                                                                     |
| ------------------------ | ------------------------------------------------------------------------ |
| UNIX_TIMESTAMP()         | 以 UNIX 时间戳的形式返回当前时间。SELECT UNIX_TIMESTAMP() ->1634348884。 |
| UNIX_TIMESTAMP(date)     | 将时间 date 以 UNIX 时间戳的形式返回。                                   |
| FROM_UNIXTIME(timestamp) | 将 UNIX 时间戳的时间转换为普通格式的时间。                               |

举例：

```sh
mysql> SELECT UNIX_TIMESTAMP(now());
+-----------------------+
| UNIX_TIMESTAMP(now()) |
+-----------------------+
|            1576380910 |
+-----------------------+
1 row in set (0.01 sec)

mysql> SELECT UNIX_TIMESTAMP(CURDATE());
+---------------------------+
| UNIX_TIMESTAMP(CURDATE()) |
+---------------------------+
|                1576339200 |
+---------------------------+
1 row in set (0.00 sec)

mysql> SELECT UNIX_TIMESTAMP(CURTIME());
+---------------------------+
| UNIX_TIMESTAMP(CURTIME()) |
+---------------------------+
|                1576380969 |
+---------------------------+
1 row in set (0.00 sec)

mysql> SELECT UNIX_TIMESTAMP('2011-11-11 11:11:11')
+---------------------------------------+
| UNIX_TIMESTAMP('2011-11-11 11:11:11') |
+---------------------------------------+
|                            1320981071 |
+---------------------------------------+
1 row in set (0.00 sec)
```

```sh
mysql> SELECT FROM_UNIXTIME(1576380910);
+---------------------------+
| FROM_UNIXTIME(1576380910) |
+---------------------------+
| 2019-12-15 11:35:10       |
+---------------------------+
1 row in set (0.00 sec)
```

### 4.3 获取月份、星期、星期数、天数等函数

| 函数                                     | 用法                                                  |
| ---------------------------------------- | ----------------------------------------------------- |
| YEAR(date) / MONTH(date) / DAY(date)     | 返回具体的日期值。                                    |
| HOUR(time) / MINUTE(time) / SECOND(time) | 返回具体的时间值。                                    |
| MONTHNAME(date)                          | 返回月份：January，...                                |
| DAYNAME(date)                            | 返回星期几：MONDAY，TUESDAY.....SUNDAY。              |
| WEEKDAY(date)                            | 返回周几，注意，周 1 是 0，周 2 是 1， ... 周日是 6。 |
| QUARTER(date)                            | 返回日期对应的季度，范围为 1 ～ 4。                   |
| WEEK(date) ， WEEKOFYEAR(date)           | 返回一年中的第几周。                                  |
| DAYOFYEAR(date)                          | 返回日期是一年中的第几天。                            |
| DAYOFMONTH(date)                         | 返回日期位于所在月份的第几天。                        |
| DAYOFWEEK(date)                          | 返回周几，注意：周日是 1，周一是 2， ... 周六是 7。   |

举例：

```sql
SELECT YEAR(CURDATE()),MONTH(CURDATE()),DAY(CURDATE()),
HOUR(CURTIME()),MINUTE(NOW()),SECOND(SYSDATE())
FROM DUAL;
```

![获取月份、星期、星期数、天数等函数](https://img-blog.csdnimg.cn/1d864081fcac45699318d11246220fd7.png)

```sql
SELECT MONTHNAME('2021-10-26'),DAYNAME('2021-10-26'),WEEKDAY('2021-10-26'),
QUARTER(CURDATE()),WEEK(CURDATE()),DAYOFYEAR(NOW()),
DAYOFMONTH(NOW()),DAYOFWEEK(NOW())
FROM DUAL;
```

![获取月份、星期、星期数、天数等函数](https://img-blog.csdnimg.cn/2a259f5c74434001a55ae3eba53cf7de.png)

### 4.4 日期的操作函数

| 函数                    | 用法                                          |
| ----------------------- | --------------------------------------------- |
| EXTRACT(type FROM date) | 返回指定日期中特定的部分，type 指定返回的值。 |

EXTRACT(type FROM date)函数中 type 的取值与含义：

![日期的操作函数](https://img-blog.csdnimg.cn/3f38f4efce824bc68d1a9c8fff5c134c.png)

```sql
SELECT EXTRACT(MINUTE FROM NOW()),EXTRACT( WEEK FROM NOW()),
EXTRACT( QUARTER FROM NOW()),EXTRACT( MINUTE_SECOND FROM NOW())
FROM DUAL;
```

### 4.5 时间和秒钟转换的函数

| 函数                 | 用法                                                                 |
| -------------------- | -------------------------------------------------------------------- |
| TIME_TO_SEC(time)    | 将 time 转化为秒并返回结果值。转化的公式为：`小时*3600+分钟*60+秒`。 |
| SEC_TO_TIME(seconds) | 将 seconds 描述转化为包含小时、分钟和秒的时间。                      |

举例：

```sh
mysql> SELECT TIME_TO_SEC(NOW());
+--------------------+
| TIME_TO_SEC(NOW()) |
+--------------------+
|               78774 |
+--------------------+
1 row in set (0.00 sec)
```

```sh
mysql> SELECT SEC_TO_TIME(78774);
+--------------------+
| SEC_TO_TIME(78774) |
+--------------------+
| 21:52:54            |
+--------------------+
1 row in set (0.12 sec)
```

### 4.6 计算日期和时间的函数

**第 1 组：**

| 函数                                                                     | 用法                                               |
| ------------------------------------------------------------------------ | -------------------------------------------------- |
| DATE_ADD(datetime, INTERVAL expr type)，ADDDATE(date,INTERVAL expr type) | 返回与给定日期时间相差 INTERVAL 时间段的日期时间。 |
| DATE_SUB(date,INTERVAL expr type)，SUBDATE(date,INTERVAL expr type)      | 返回与 date 相差 INTERVAL 时间间隔的日期。         |

上述函数中 type 的取值：

![计算日期和时间的函数](https://img-blog.csdnimg.cn/3b11cd7f26104c6a93554832567971ee.png)

举例：

```sql
SELECT DATE_ADD(NOW(), INTERVAL 1 DAY) AS col1,DATE_ADD('2021-10-21 23:32:12',INTERVAL 1 SECOND) AS col2,
ADDDATE('2021-10-21 23:32:12',INTERVAL 1 SECOND) AS col3,
DATE_ADD('2021-10-21 23:32:12',INTERVAL '1_1' MINUTE_SECOND) AS col4,
DATE_ADD(NOW(), INTERVAL -1 YEAR) AS col5, #可以是负数
DATE_ADD(NOW(), INTERVAL '1_1' YEAR_MONTH) AS col6 #需要单引号
FROM DUAL;
```

```sql
SELECT DATE_SUB('2021-01-21',INTERVAL 31 DAY) AS col1,
SUBDATE('2021-01-21',INTERVAL 31 DAY) AS col2,
DATE_SUB('2021-01-21 02:01:01',INTERVAL '1 1' DAY_HOUR) AS col3
FROM DUAL;
```

**第 2 组：**

| 函数                         | 用法                                                                              |
| ---------------------------- | --------------------------------------------------------------------------------- |
| ADDTIME(time1,time2)         | 返回 time1 加上 time2 的时间。当 time2 为一个数字时，代表的是`秒`，可以为负数。   |
| SUBTIME(time1,time2)         | 返回 time1 减去 time2 后的时间。当 time2 为一个数字时，代表的是`秒`，可以为负数。 |
| DATEDIFF(date1,date2)        | 返回 date1 - date2 的日期间隔天数。                                               |
| TIMEDIFF(time1, time2)       | 返回 time1 - time2 的时间间隔。                                                   |
| FROM_DAYS(N)                 | 返回从 0000 年 1 月 1 日起，N 天以后的日期。                                      |
| TO_DAYS(date)                | 返回日期 date 距离 0000 年 1 月 1 日的天数。                                      |
| LAST_DAY(date)               | 返回 date 所在月份的最后一天的日期。                                              |
| MAKEDATE(year,n)             | 针对给定年份与所在年份中的天数返回一个日期。                                      |
| MAKETIME(hour,minute,second) | 将给定的小时、分钟和秒组合成时间并返回。                                          |
| PERIOD_ADD(time,n)           | 返回 time 加上 n 后的时间。                                                       |

举例：

```sql
SELECT ADDTIME(NOW(),20),SUBTIME(NOW(),30),SUBTIME(NOW(),'1:1:3'),DATEDIFF(NOW(),'2021-10-01'),
TIMEDIFF(NOW(),'2021-10-25 22:10:10'),FROM_DAYS(366),TO_DAYS('0000-12-25'),
LAST_DAY(NOW()),MAKEDATE(YEAR(NOW()),12),MAKETIME(10,21,23),PERIOD_ADD(20200101010101,10)
FROM DUAL;
```

```sh
mysql> SELECT ADDTIME(NOW(), 50);
+---------------------+
| ADDTIME(NOW(), 50)  |
+---------------------+
| 2019-12-15 22:17:47 |
+---------------------+
1 row in set (0.00 sec)

mysql> SELECT ADDTIME(NOW(), '1:1:1');
+-------------------------+
| ADDTIME(NOW(), '1:1:1') |
+-------------------------+
| 2019-12-15 23:18:46     |
+-------------------------+
1 row in set (0.00 sec)
```

```sh
mysql> SELECT SUBTIME(NOW(), '1:1:1');
+-------------------------+
| SUBTIME(NOW(), '1:1:1') |
+-------------------------+
| 2019-12-15 21:23:50     |
+-------------------------+
1 row in set (0.00 sec)

mysql> SELECT SUBTIME(NOW(), '-1:-1:-1');
+----------------------------+
| SUBTIME(NOW(), '-1:-1:-1') |
+----------------------------+
| 2019-12-15 22:25:11        |
+----------------------------+
1 row in set, 1 warning (0.00 sec)
```

```sh
mysql> SELECT FROM_DAYS(366);
+----------------+
| FROM_DAYS(366) |
+----------------+
| 0001-01-01     |
+----------------+
1 row in set (0.00 sec)
```

```sh
mysql> SELECT MAKEDATE(2020,1);
+------------------+
| MAKEDATE(2020,1) |
+------------------+
| 2020-01-01       |
+------------------+
1 row in set (0.00 sec)

mysql> SELECT MAKEDATE(2020,32);
+-------------------+
| MAKEDATE(2020,32) |
+-------------------+
| 2020-02-01        |
+-------------------+
1 row in set (0.00 sec)
```

```sh
mysql> SELECT MAKETIME(1,1,1);
+-----------------+
| MAKETIME(1,1,1) |
+-----------------+
| 01:01:01        |
+-----------------+
1 row in set (0.00 sec)
```

```sh
mysql> SELECT PERIOD_ADD(20200101010101,1);
+------------------------------+
| PERIOD_ADD(20200101010101,1) |
+------------------------------+
|               20200101010102 |
+------------------------------+
1 row in set (0.00 sec)
```

```sh
mysql> SELECT TO_DAYS(NOW());
+----------------+
| TO_DAYS(NOW()) |
+----------------+
|          737773 |
+----------------+
1 row in set (0.00 sec)
```

举例：查询 7 天内的新增用户数有多少？

```sql
SELECT COUNT(*) as num FROM new_user WHERE TO_DAYS(NOW())-TO_DAYS(regist_time)<=7
```

### 4.7 日期的格式化与解析

| 函数                              | 用法                                             |
| --------------------------------- | ------------------------------------------------ |
| DATE_FORMAT(date,fmt)             | 按照字符串 fmt 格式化日期 date 值。              |
| TIME_FORMAT(time,fmt)             | 按照字符串 fmt 格式化时间 time 值。              |
| GET_FORMAT(date_type,format_type) | 返回日期字符串的显示格式。                       |
| STR_TO_DATE(str, fmt)             | 按照字符串 fmt 对 str 进行解析，解析为一个日期。 |

上述`非GET_FORMAT`函数中 fmt 参数常用的格式符：

| 格式符 | 说明                                                            | 格式符  | 说明                                                            |
| ------ | --------------------------------------------------------------- | ------- | --------------------------------------------------------------- |
| %Y     | 4 位数字表示年份。                                              | %y      | 表示两位数字表示年份。                                          |
| %M     | 月名表示月份（January,....）。                                  | %m      | 两位数字表示月份（01,02,03 ...）。                              |
| %b     | 缩写的月名（Jan.，Feb.，....）。                                | %c      | 数字表示月份（1,2,3,...）。                                     |
| %D     | 英文后缀表示月中的天数（1st,2nd,3rd,...）。                     | %d      | 两位数字表示月中的天数(01,02...)。                              |
| %e     | 数字形式表示月中的天数（1,2,3,4,5.....）。                      |         |                                                                 |
| %H     | 两位数字表示小数，24 小时制（01,02..）。                        | %h 和%I | 两位数字表示小时，12 小时制（01,02..）。                        |
| %k     | 数字形式的小时，24 小时制(1,2,3)。                              | %l      | 数字形式表示小时，12 小时制（1,2,3,4....）。                    |
| %i     | 两位数字表示分钟（00,01,02）。                                  | %S 和%s | 两位数字表示秒(00,01,02...)。                                   |
| %W     | 一周中的星期名称（Sunday...）。                                 | %a      | 一周中的星期缩写（Sun，Mon,Tues...）。                          |
| %w     | 以数字表示周中的天数(0=Sunday,1=Monday....)。                   |         |                                                                 |
| %j     | 以 3 位数字表示年中的天数(001,002...)。                         | %U      | 以数字表示年中的第几周，（1,2,3。。）其中 Sunday 为周中第一天。 |
| %u     | 以数字表示年中的第几周，（1,2,3。。）其中 Monday 为周中第一天。 |         |                                                                 |
| %T     | 24 小时制。                                                     | %r      | 12 小时制。                                                     |
| %p     | AM 或 PM。                                                      | %%      | 表示%。                                                         |

GET_FORMAT 函数中 date_type 和 format_type 参数取值如下：

![日期的格式化与解析](https://img-blog.csdnimg.cn/0f18fddaa00e462f885add7eb9bb9654.png)

举例：

```sh
mysql> SELECT DATE_FORMAT(NOW(), '%H:%i:%s');
+--------------------------------+
| DATE_FORMAT(NOW(), '%H:%i:%s') |
+--------------------------------+
| 22:57:34                        |
+--------------------------------+
1 row in set (0.00 sec)
```

```sql
SELECT STR_TO_DATE('09/01/2009','%m/%d/%Y')
FROM DUAL;

SELECT STR_TO_DATE('20140422154706','%Y%m%d%H%i%s')
FROM DUAL;

SELECT STR_TO_DATE('2014-04-22 15:47:06','%Y-%m-%d %H:%i:%s')
FROM DUAL;
```

```sh
mysql> SELECT GET_FORMAT(DATE, 'USA');
+-------------------------+
| GET_FORMAT(DATE, 'USA') |
+-------------------------+
| %m.%d.%Y                |
+-------------------------+
1 row in set (0.00 sec)

SELECT DATE_FORMAT(NOW(),GET_FORMAT(DATE,'USA')),
FROM DUAL;
```

```sh
mysql> SELECT STR_TO_DATE('2020-01-01 00:00:00','%Y-%m-%d');
+-----------------------------------------------+
| STR_TO_DATE('2020-01-01 00:00:00','%Y-%m-%d') |
+-----------------------------------------------+
| 2020-01-01                                    |
+-----------------------------------------------+
1 row in set, 1 warning (0.00 sec)
```

## 5. 流程控制函数

流程处理函数可以根据不同的条件，执行不同的处理流程，可以在 SQL 语句中实现不同的条件选择。MySQL 中的流程处理函数主要包括 IF()、IFNULL()和 CASE()函数。

| 函数                                                                           | 用法                                                   |
| ------------------------------------------------------------------------------ | ------------------------------------------------------ |
| IF(value,value1,value2)                                                        | 如果 value 的值为 TRUE，返回 value1，否则返回 value2。 |
| IFNULL(value1, value2)                                                         | 如果 value1 不为 NULL，返回 value1，否则返回 value2。  |
| CASE WHEN 条件 1 THEN 结果 1 WHEN 条件 2 THEN 结果 2 .... [ELSE resultn] END   | 相当于 Java 的 if...else if...else...                  |
| CASE expr WHEN 常量值 1 THEN 值 1 WHEN 常量值 1 THEN 值 1 .... [ELSE 值 n] END | 相当于 Java 的 switch...case...                        |

```sh
SELECT IF(1 > 0,'正确','错误')
->正确
```

```sh
SELECT IFNULL(null,'Hello Word')
->Hello Word
```

```sh
SELECT CASE
　　WHEN 1 > 0
　　THEN '1 > 0'
　　WHEN 2 > 0
　　THEN '2 > 0'
　　ELSE '3 > 0'
　　END
->1 > 0
```

```sql
SELECT CASE 1
　　WHEN 1 THEN '我是1'
　　WHEN 2 THEN '我是2'
ELSE '你是谁'
```

```sql
SELECT employee_id,salary, CASE WHEN salary>=15000 THEN '高薪'
  WHEN salary>=10000 THEN '潜力股'
  WHEN salary>=8000 THEN '一般'
  ELSE '菜鸟' END  "描述"
FROM employees;
```

```sql
SELECT oid,`status`, CASE `status` WHEN 1 THEN '未付款'
  WHEN 2 THEN '已付款'
  WHEN 3 THEN '已发货'
  WHEN 4 THEN '确认收货'
  ELSE '无效订单' END
FROM t_order;
```

```sh
mysql> SELECT CASE WHEN 1 > 0 THEN 'yes' WHEN 1 <= 0 THEN 'no' ELSE 'unknown' END;
+---------------------------------------------------------------------+
| CASE WHEN 1 > 0 THEN 'yes' WHEN 1 <= 0 THEN 'no' ELSE 'unknown' END |
+---------------------------------------------------------------------+
| yes                                                                  |
+---------------------------------------------------------------------+
1 row in set (0.00 sec)

mysql> SELECT CASE WHEN 1 < 0 THEN 'yes' WHEN 1 = 0 THEN 'no' ELSE 'unknown' END;
+--------------------------------------------------------------------+
| CASE WHEN 1 < 0 THEN 'yes' WHEN 1 = 0 THEN 'no' ELSE 'unknown' END |
+--------------------------------------------------------------------+
| unknown                                                             |
+--------------------------------------------------------------------+
1 row in set (0.00 sec)
```

```sh
mysql> SELECT CASE 1 WHEN 0 THEN 0 WHEN 1 THEN 1 ELSE -1 END;
+------------------------------------------------+
| CASE 1 WHEN 0 THEN 0 WHEN 1 THEN 1 ELSE -1 END |
+------------------------------------------------+
|                                               1 |
+------------------------------------------------+
1 row in set (0.00 sec)

mysql> SELECT CASE -1 WHEN 0 THEN 0 WHEN 1 THEN 1 ELSE -1 END;
+-------------------------------------------------+
| CASE -1 WHEN 0 THEN 0 WHEN 1 THEN 1 ELSE -1 END |
+-------------------------------------------------+
|                                               -1 |
+-------------------------------------------------+
1 row in set (0.00 sec)
```

```sql
SELECT employee_id,12 * salary * (1 + IFNULL(commission_pct,0))
FROM employees;
```

```sql
SELECT last_name, job_id, salary,
       CASE job_id WHEN 'IT_PROG'  THEN  1.10*salary
                   WHEN 'ST_CLERK' THEN  1.15*salary
                   WHEN 'SA_REP'   THEN  1.20*salary
                ELSE      salary END     "REVISED_SALARY"
FROM   employees;
```

![流程控制函数](https://img-blog.csdnimg.cn/c30861f31922424f8f198e0260919702.png)

**练习：查询部门号为 10,20, 30 的员工信息, 若部门号为 10, 则打印其工资的 1.1 倍, 20 号部门, 则打印其工资的 1.2 倍, 30 号部门打印其工资的 1.3 倍数。**

## 6. 加密与解密函数

加密与解密函数主要用于对数据库中的数据进行加密和解密处理，以防止数据被他人窃取。这些函数在保证数据库安全时非常有用。

| 函数                        | 用法                                                                                                     |
| --------------------------- | -------------------------------------------------------------------------------------------------------- |
| PASSWORD(str)               | 返回字符串 str 的加密版本，41 位长的字符串。加密结果`不可逆`，常用于用户的密码加密。                     |
| MD5(str)                    | 返回字符串 str 的 md5 加密后的值，也是一种加密方式。若参数为 NULL，则会返回 NULL。                       |
| SHA(str)                    | 从原明文密码 str 计算并返回加密后的密码字符串，当参数为 NULL 时，返回 NULL。`SHA加密算法比MD5更加安全`。 |
| ENCODE(value,password_seed) | 返回使用 password_seed 作为加密密码加密 value。                                                          |
| DECODE(value,password_seed) | 返回使用 password_seed 作为加密密码解密 value。                                                          |

可以看到，ENCODE(value,password_seed)函数与 DECODE(value,password_seed)函数互为反函数。

举例：

```sh
mysql> SELECT PASSWORD('mysql'), PASSWORD(NULL);
+-------------------------------------------+----------------+
| PASSWORD('mysql')                         | PASSWORD(NULL) |
+-------------------------------------------+----------------+
| *E74858DB86EBA20BC33D0AECAE8A8108C56B17FA |                |
+-------------------------------------------+----------------+
1 row in set, 1 warning (0.00 sec)
```

```sh
SELECT md5('123')
->202cb962ac59075b964b07152d234b70
```

```sh
SELECT SHA('Tom123')
->c7c506980abc31cc390a2438c90861d0f1216d50
```

```sh
mysql> SELECT ENCODE('mysql', 'mysql');
+--------------------------+
| ENCODE('mysql', 'mysql') |
+--------------------------+
| íg　¼　ìÉ                  |
+--------------------------+
1 row in set, 1 warning (0.01 sec)
```

```sh
mysql> SELECT DECODE(ENCODE('mysql','mysql'),'mysql');
+-----------------------------------------+
| DECODE(ENCODE('mysql','mysql'),'mysql') |
+-----------------------------------------+
| mysql                                   |
+-----------------------------------------+
1 row in set, 2 warnings (0.00 sec)
```

## 7. MySQL 信息函数

MySQL 中内置了一些可以查询 MySQL 信息的函数，这些函数主要用于帮助数据库开发或运维人员更好地对数据库进行维护工作。

| 函数                                                  | 用法                                                         |
| ----------------------------------------------------- | ------------------------------------------------------------ |
| VERSION()                                             | 返回当前 MySQL 的版本号。                                    |
| CONNECTION_ID()                                       | 返回当前 MySQL 服务器的连接数。                              |
| DATABASE()，SCHEMA()                                  | 返回 MySQL 命令行当前所在的数据库。                          |
| USER()，CURRENT_USER()、SYSTEM_USER()，SESSION_USER() | 返回当前连接 MySQL 的用户名，返回结果格式为“主机名@用户名”。 |
| CHARSET(value)                                        | 返回字符串 value 自变量的字符集。                            |
| COLLATION(value)                                      | 返回字符串 value 的比较规则。                                |

举例：

```sh
mysql> SELECT DATABASE();
+------------+
| DATABASE() |
+------------+
| test       |
+------------+
1 row in set (0.00 sec)

mysql> SELECT DATABASE();
+------------+
| DATABASE() |
+------------+
| test       |
+------------+
1 row in set (0.00 sec)
```

```sh
mysql> SELECT USER(), CURRENT_USER(), SYSTEM_USER(),SESSION_USER();
+----------------+----------------+----------------+----------------+
| USER()         | CURRENT_USER() | SYSTEM_USER()  | SESSION_USER() |
+----------------+----------------+----------------+----------------+
| root@localhost | root@localhost | root@localhost | root@localhost |
+----------------+----------------+----------------+----------------+

```

```sh
mysql> SELECT CHARSET('ABC');
+----------------+
| CHARSET('ABC') |
+----------------+
| utf8mb4        |
+----------------+
1 row in set (0.00 sec)
```

```sh
mysql> SELECT COLLATION('ABC');
+--------------------+
| COLLATION('ABC')   |
+--------------------+
| utf8mb4_general_ci |
+--------------------+
1 row in set (0.00 sec)
```

## 8. 其他函数

MySQL 中有些函数无法对其进行具体的分类，但是这些函数在 MySQL 的开发和运维过程中也是不容忽视的。

| 函数                           | 用法                                                                             |
| ------------------------------ | -------------------------------------------------------------------------------- |
| FORMAT(value,n)                | 返回对数字 value 进行格式化后的结果数据。n 表示`四舍五入`后保留到小数点后 n 位。 |
| CONV(value,from,to)            | 将 value 的值进行不同进制之间的转换。                                            |
| INET_ATON(ipvalue)             | 将以点分隔的 IP 地址转化为一个数字。                                             |
| INET_NTOA(value)               | 将数字形式的 IP 地址转化为以点分隔的 IP 地址。                                   |
| BENCHMARK(n,expr)              | 将表达式 expr 重复执行 n 次。用于测试 MySQL 处理 expr 表达式所耗费的时间。       |
| CONVERT(value USING char_code) | 将 value 所使用的字符编码修改为 char_code。                                      |

举例：

```sql
# 如果 n 的值小于或者等于 0，则只保留整数部分
mysql> SELECT FORMAT(123.123, 2), FORMAT(123.523, 0), FORMAT(123.123, -2);
+--------------------+--------------------+---------------------+
| FORMAT(123.123, 2) | FORMAT(123.523, 0) | FORMAT(123.123, -2) |
+--------------------+--------------------+---------------------+
| 123.12             | 124                | 123                 |
+--------------------+--------------------+---------------------+
1 row in set (0.00 sec)
```

```sh
mysql> SELECT CONV(16, 10, 2), CONV(8888,10,16), CONV(NULL, 10, 2);
+-----------------+------------------+-------------------+
| CONV(16, 10, 2) | CONV(8888,10,16) | CONV(NULL, 10, 2) |
+-----------------+------------------+-------------------+
| 10000           | 22B8             | NULL              |
+-----------------+------------------+-------------------+
1 row in set (0.00 sec)
```

```sql
# 以“192.168.1.100”为例，计算方式为 192 乘以 256 的 3 次方，加上 168 乘以 256 的 2 次方，加上 1 乘以 256，再加上 100。
mysql> SELECT INET_ATON('192.168.1.100');
+----------------------------+
| INET_ATON('192.168.1.100') |
+----------------------------+
|                 3232235876 |
+----------------------------+
1 row in set (0.00 sec)
```

```sh
mysql> SELECT INET_NTOA(3232235876);
+-----------------------+
| INET_NTOA(3232235876) |
+-----------------------+
| 192.168.1.100         |
+-----------------------+
1 row in set (0.00 sec)
```

```sh
mysql> SELECT BENCHMARK(1, MD5('mysql'));
+----------------------------+
| BENCHMARK(1, MD5('mysql')) |
+----------------------------+
|                          0 |
+----------------------------+
1 row in set (0.00 sec)

mysql> SELECT BENCHMARK(1000000, MD5('mysql'));
+----------------------------------+
| BENCHMARK(1000000, MD5('mysql')) |
+----------------------------------+
|                                0 |
+----------------------------------+
1 row in set (0.20 sec)
```

```sh
mysql> SELECT CHARSET('mysql'), CHARSET(CONVERT('mysql' USING 'utf8'));
+------------------+----------------------------------------+
| CHARSET('mysql') | CHARSET(CONVERT('mysql' USING 'utf8')) |
+------------------+----------------------------------------+
| utf8mb4          | utf8                                   |
+------------------+----------------------------------------+
1 row in set, 1 warning (0.00 sec)
```

# 第 8 章 聚合函数

我们上一章讲到了 SQL 单行函数。实际上 SQL 函数还有一类，叫做聚合（或聚集、分组）函数，它是对一组数据进行汇总的函数，输入的是一组数据的集合，输出的是单个值。

## 1. 聚合函数介绍

- **什么是聚合函数**

  聚合函数作用于一组数据，并对一组数据返回一个值。

  ![聚合函数介绍](https://img-blog.csdnimg.cn/66b540d8392b4b799e501fc3667ccc3b.png)

- **聚合函数类型**

  - **AVG()**

  - **SUM()**

  - **MAX()**

  - **MIN()**

  - **COUNT()**

- 聚合函数语法

  ![聚合函数介绍](https://img-blog.csdnimg.cn/24973d2ba40b4bbf9240d559cd41b0e8.png)

- 聚合函数不能嵌套调用。比如不能出现类似“AVG(SUM(字段名称))”形式的调用。

### 1.1 AVG 和 SUM 函数

可以对**数值型数据**使用 AVG 和 SUM 函数。

```sql
SELECT AVG(salary), MAX(salary),MIN(salary), SUM(salary)
FROM   employees
WHERE  job_id LIKE '%REP%';
```

![AVG 和 SUM 函数](https://img-blog.csdnimg.cn/137b7f9ea590477280feba5c15ce97c4.png)

### 1.2 MIN 和 MAX 函数

可以对**任意数据类型**的数据使用 MIN 和 MAX 函数。

```sql
SELECT MIN(hire_date), MAX(hire_date)
FROM   employees;
```

![MIN 和 MAX 函数](https://img-blog.csdnimg.cn/3bc8ef62a54942b080c83d34ca347922.png)

### 1.3 COUNT 函数

- COUNT(\*)返回表中记录总数，适用于**任意数据类型**。

  ```sql
  SELECT COUNT(*)
  FROM   employees
  WHERE  department_id = 50;
  ```

  ![COUNT 函数](https://img-blog.csdnimg.cn/4ab146baab5444009945311ee5adab8a.png)

- COUNT(expr) 返回**expr 不为空**的记录总数。

  ```sql
  SELECT COUNT(commission_pct)
  FROM   employees
  WHERE  department_id = 50;
  ```

  ![COUNT 函数](https://img-blog.csdnimg.cn/6b3f24aebeed4c049251f85da543d39a.png)

- **问题：用 count(\*)，count(1)，count(列名)谁好呢?**

  其实，对于 MyISAM 引擎的表是没有区别的。这种引擎内部有一计数器在维护着行数。

  Innodb 引擎的表用 count(\*),count(1)直接读行数，复杂度是 O(n)，因为 innodb 真的要去数一遍。但好于具体的 count(列名)。

- **问题：能不能使用 count(列名)替换 count(\*)?**

  不要使用 count(列名)来替代 `count(*)`，`count(*)`是 SQL92 定义的标准统计行数的语法，跟数据库无关，跟 NULL 和非 NULL 无关。

  说明：count(\*)会统计值为 NULL 的行，而 count(列名)不会统计此列为 NULL 值的行。

## 2. GROUP BY

### 2.1 基本使用

![基本使用](https://img-blog.csdnimg.cn/1e6d30b26aa147dd9639d04822435002.png)

**可以使用 GROUP BY 子句将表中的数据分成若干组**

> SELECT column, group_function(column)
> FROM table
> [WHERE condition] > [GROUP BY group_by_expression] > [ORDER BY column];

> **明确：WHERE 一定放在 FROM 后面**

**在 SELECT 列表中所有未包含在组函数中的列都应该包含在 GROUP BY 子句中**

```sql
SELECT   department_id, AVG(salary)
FROM     employees
GROUP BY department_id ;
```

![基本使用](https://img-blog.csdnimg.cn/e57cc1980d304a4181580c9a5826e437.png)

包含在 GROUP BY 子句中的列不必包含在 SELECT 列表中

```sql
SELECT   AVG(salary)
FROM     employees
GROUP BY department_id ;
```

![基本使用](https://img-blog.csdnimg.cn/d754500a39324ef0834d0a3f370c20c2.png)

### 2.2 使用多个列分组

![使用多个列分组](https://img-blog.csdnimg.cn/7b06ebd34bb443d88fdab500da3507b1.png)

```sql
SELECT   department_id dept_id, job_id, SUM(salary)
FROM     employees
GROUP BY department_id, job_id ;
```

![使用多个列分组](https://img-blog.csdnimg.cn/fc217bcd4713491eb1bcc75ed2a778b3.png)

### 2.3 GROUP BY 中使用 WITH ROLLUP

使用`WITH ROLLUP`关键字之后，在所有查询出的分组记录之后增加一条记录，该记录计算查询出的所有记录的总和，即统计记录数量。

```sql
SELECT department_id,AVG(salary)
FROM   employees
WHERE  department_id > 80
GROUP BY department_id WITH ROLLUP;
```

> 注意：
>
> 当使用 ROLLUP 时，不能同时使用 ORDER BY 子句进行结果排序，即 ROLLUP 和 ORDER BY 是互相排斥的。

## 3. HAVING

### 3.1 基本使用

![基本使用](https://img-blog.csdnimg.cn/c31175cf174d4d88b84d936e80b16d7d.png)

**过滤分组：HAVING 子句**

1. 行已经被分组。

2. 使用了聚合函数。

3. 满足 HAVING 子句中条件的分组将被显示。

4. HAVING 不能单独使用，必须要跟 GROUP BY 一起使用。

![过滤分组：HAVING 子句](https://img-blog.csdnimg.cn/203d77c9a1364a17ae3c2698f8ef69b0.png)

```sql
SELECT   department_id, MAX(salary)
FROM     employees
GROUP BY department_id
HAVING   MAX(salary)>10000 ;
```

![过滤分组：HAVING 子句](https://img-blog.csdnimg.cn/a435a578315e4b60906a5f5061470f02.png)

- **非法使用聚合函数 ： 不能在 WHERE 子句中使用聚合函数。** 如下：

  ```sql
  SELECT   department_id, AVG(salary)
  FROM     employees
  WHERE    AVG(salary) > 8000
  GROUP BY department_id;
  ```

  ![非法使用聚合函数 ： 不能在 WHERE 子句中使用聚合函数。](https://img-blog.csdnimg.cn/cf4c6f602afd42dba269256ff77045e5.png)

### 3.2 WHERE 和 HAVING 的对比

**区别 1：WHERE 可以直接使用表中的字段作为筛选条件，但不能使用分组中的计算函数作为筛选条件；HAVING 必须要与 GROUP BY 配合使用，可以把分组计算的函数和分组字段作为筛选条件。**

这决定了，在需要对数据进行分组统计的时候，HAVING 可以完成 WHERE 不能完成的任务。这是因为，在查询语法结构中，WHERE 在 GROUP BY 之前，所以无法对分组结果进行筛选。HAVING 在 GROUP BY 之后，可以使用分组字段和分组中的计算函数，对分组的结果集进行筛选，这个功能是 WHERE 无法完成的。另外，WHERE 排除的记录不再包括在分组中。

**区别 2：如果需要通过连接从关联表中获取需要的数据，WHERE 是先筛选后连接，而 HAVING 是先连接后筛选。** 这一点，就决定了在关联查询中，WHERE 比 HAVING 更高效。因为 WHERE 可以先筛选，用一个筛选后的较小数据集和关联表进行连接，这样占用的资源比较少，执行效率也比较高。HAVING 则需要先把结果集准备好，也就是用未被筛选的数据集进行关联，然后对这个大的数据集进行筛选，这样占用的资源就比较多，执行效率也较低。

小结如下：

|        | 优点                           | 缺点                                     |
| ------ | ------------------------------ | ---------------------------------------- |
| WHERE  | 先筛选数据再关联，执行效率高。 | 不能使用分组中的计算函数进行筛选。       |
| HAVING | 可以使用分组中的计算函数。     | 在最后的结果集中进行筛选，执行效率较低。 |

**开发中的选择：**

WHERE 和 HAVING 也不是互相排斥的，我们可以在一个查询里面同时使用 WHERE 和 HAVING。包含分组统计函数的条件用 HAVING，普通条件用 WHERE。这样，我们就既利用了 WHERE 条件的高效快速，又发挥了 HAVING 可以使用包含分组统计函数的查询条件的优点。当数据量特别大的时候，运行效率会有很大的差别。

## 4. SELECT 的执行过程

### 4.1 查询的结构

> \# 方式 1：
>
> SELECT ...,...,...
> FROM ...,...,....
> WHERE 多表的连接条件
> AND 不包含组函数的过滤条件
> GROUP BY ...,...
> HAVING 包含组函数的过滤条件
> ORDER BY ... ASC/DESC
> LIMIT ...,...
>
> \# 方式 2：
> SELECT ...,...,...
> FROM ... JOIN ...
> ON 多表的连接条件
> JOIN ...
> ON ...
> WHERE 不包含组函数的过滤条件
> AND/OR 不包含组函数的过滤条件
> GROUP BY ...,...
> HAVING 包含组函数的过滤条件
> ORDER BY ... ASC/DESC
> LIMIT ...,...
>
> \# 其中：
> \# （1）from：从哪些表中筛选。
> \# （2）on：关联多表查询时，去除笛卡尔积。
> \# （3）where：从表中筛选的条件。
> \# （4）group by：分组依据。
> \# （5）having：在统计结果中再次筛选。
> \# （6）order by：排序。
> \# （7）limit：分页。

### 4.2 SELECT 执行顺序

你需要记住 SELECT 查询时的两个顺序：

**1. 关键字的顺序是不能颠倒的：**

> SELECT ... FROM ... WHERE ... GROUP BY ... HAVING ... ORDER BY ... LIMIT...

**2.SELECT 语句的执行顺序**（在 MySQL 和 Oracle 中，SELECT 执行顺序基本相同）：

> FROM -> WHERE -> GROUP BY -> HAVING -> SELECT 的字段 -> DISTINCT -> ORDER BY -> LIMIT

![SELECT 执行顺序](https://img-blog.csdnimg.cn/3759dcc2462448ddacc5c2ecfa82f462.png)

比如你写了一个 SQL 语句，那么它的关键字顺序和执行顺序是下面这样的：

```sql
# 顺序 5
SELECT DISTINCT player_id, player_name, count(*) as num

# 顺序 1
FROM player JOIN team ON player.team_id = team.team_id

# 顺序 2
WHERE height > 1.80

# 顺序 3
GROUP BY player.team_id

# 顺序 4
HAVING num > 2

# 顺序 6
ORDER BY num DESC

# 顺序 7
LIMIT 2
```

在 SELECT 语句执行这些步骤的时候，每个步骤都会产生一个`虚拟表`，然后将这个虚拟表传入下一个步骤中作为输入。需要注意的是，这些步骤隐含在 SQL 的执行过程中，对于我们来说是不可见的。

### 4.3 SQL 的执行原理

SELECT 是先执行 FROM 这一步的。在这个阶段，如果是多张表联查，还会经历下面的几个步骤：

1. 首先先通过 CROSS JOIN 求笛卡尔积，相当于得到虚拟表 vt（virtual table）1-1；

2. 通过 ON 进行筛选，在虚拟表 vt1-1 的基础上进行筛选，得到虚拟表 vt1-2；

3. 添加外部行。如果我们使用的是左连接、右链接或者全连接，就会涉及到外部行，也就是在虚拟表 vt1-2 的基础上增加外部行，得到虚拟表 vt1-3。

当然如果我们操作的是两张以上的表，还会重复上面的步骤，直到所有表都被处理完为止。这个过程得到是我们的原始数据。

当我们拿到了查询数据表的原始数据，也就是最终的虚拟表 `vt1`，就可以在此基础上再进行 `WHERE 阶段`。在这个阶段中，会根据 vt1 表的结果进行筛选过滤，得到虚拟表 `vt2`。

然后进入第三步和第四步，也就是 `GROUP 和 HAVING 阶段`。在这个阶段中，实际上是在虚拟表 vt2 的基础上进行分组和分组过滤，得到中间的虚拟表 `vt3` 和 `vt4`。

当我们完成了条件筛选部分之后，就可以筛选表中提取的字段，也就是进入到 `SELECT 和 DISTINCT 阶段`。

首先在 SELECT 阶段会提取想要的字段，然后在 DISTINCT 阶段过滤掉重复的行，分别得到中间的虚拟表 `vt5-1` 和 `vt5-2`。

当我们提取了想要的字段数据之后，就可以按照指定的字段进行排序，也就是 `ORDER BY 阶段`，得到虚拟表 `vt6`。

最后在 vt6 的基础上，取出指定行的记录，也就是 `LIMIT 阶段`，得到最终的结果，对应的是虚拟表 `vt7`。

当然我们在写 SELECT 语句的时候，不一定存在所有的关键字，相应的阶段就会省略。

同时因为 SQL 是一门类似英语的结构化查询语言，所以我们在写 SELECT 语句的时候，还要注意相应的关键字顺序，**所谓底层运行的原理，就是我们刚才讲到的执行顺序。**

# 第 9 章 子查询

子查询指一个查询语句嵌套在另一个查询语句内部的查询，这个特性从 MySQL 4.1 开始引入。

SQL 中子查询的使用大大增强了 SELECT 查询的能力，因为很多时候查询需要从结果集中获取数据，或者需要从同一个表中先计算得出一个数据结果，然后与这个数据结果（可能是某个标量，也可能是某个集合）进行比较。

## 1. 需求分析与问题解决

### 1.1 实际问题

![实际问题](https://img-blog.csdnimg.cn/5d21c0793e0a442090b56817b25bd579.png)

现有解决方式：

```sql
# 方式一：
SELECT salary
FROM employees
WHERE last_name = 'Abel';

SELECT last_name,salary
FROM employees
WHERE salary > 11000;

# 方式二：自连接
SELECT e2.last_name,e2.salary
FROM employees e1,employees e2
WHERE e1.last_name = 'Abel'
AND e1.`salary` < e2.`salary`
```

```sql
# 方式三：子查询
SELECT last_name,salary
FROM employees
WHERE salary > (
    SELECT salary
    FROM employees
    WHERE last_name = 'Abel'
    );
```

![实际问题](https://img-blog.csdnimg.cn/80dc447b782341ee9eb0162886770281.png)

### 1.2 子查询的基本使用

- 子查询的基本语法结构：

  ![子查询的基本使用](https://img-blog.csdnimg.cn/ce9c265d669e4e9d8353e71b223c280a.png)

- 子查询（内查询）在主查询之前一次执行完成。

- 子查询的结果被主查询（外查询）使用。

- **注意事项**

  - 子查询要包含在括号。

  - 将子查询放在比较条件的右侧。

  - 单行操作符对应单行子查询，多行操作符对应多行子查询。

### 1.3 子查询的分类

**分类方式 1：**

我们按内查询的结果返回一条还是多条记录，将子查询分为`单行子查询`、`多行子查询`。

- 单行子查询

  ![子查询的分类](https://img-blog.csdnimg.cn/f78c185c62224d699118f8fd6d888c04.png)

- 多行子查询

  ![子查询的分类](https://img-blog.csdnimg.cn/1130ed8618044936b30cd16535cac04f.png)

**分类方式 2：**

我们按内查询是否被执行多次，将子查询划分为`相关(或关联)子查询`和`不相关(或非关联)子查询`。

子查询从数据表中查询了数据结果，如果这个数据结果只执行一次，然后这个数据结果作为主查询的条件进行执行，那么这样的子查询叫做不相关子查询。

同样，如果子查询需要执行多次，即采用循环的方式，先从外部查询开始，每次都传入子查询进行查询，然后再将结果反馈给外部，这种嵌套的执行方式就称为相关子查询。

## 2. 单行子查询

### 2.1 单行比较操作符

| 操作符 | 含义                     |
| ------ | ------------------------ |
| =      | equal to                 |
| >      | greater than             |
| >=     | greater than or equal to |
| <      | less than                |
| <=     | less than or equal to    |
| <>     | not equal to             |

### 2.2 代码示例

**题目：查询工资大于 149 号员工工资的员工的信息**

![代码示例](https://img-blog.csdnimg.cn/5d145371598c4715bb10d8784b046a9b.png)

![代码示例](https://img-blog.csdnimg.cn/623d5a46b7804d5b876deaf61010c257.png)

**题目：返回 job_id 与 141 号员工相同，salary 比 143 号员工多的员工姓名，job_id 和工资**

```sql
SELECT last_name, job_id, salary
FROM   employees
WHERE  job_id =
                (SELECT job_id
                 FROM   employees
                 WHERE  employee_id = 141)
AND    salary >
                (SELECT salary
                 FROM   employees
                 WHERE  employee_id = 143);
```

![代码示例](https://img-blog.csdnimg.cn/b69df7b0b4e64b1bbad0a6039a39b3f1.png)

**题目：返回公司工资最少的员工的 last_name,job_id 和 salary**

```sql
SELECT last_name, job_id, salary
FROM   employees
WHERE  salary =
                (SELECT MIN(salary)
                 FROM   employees);
```

![代码示例](https://img-blog.csdnimg.cn/81d97c4f6993450bbb6cec035170bda8.png)

**题目：查询与 141 号或 174 号员工的 manager_id 和 department_id 相同的其他员工的 employee_id，manager_id，department_id**

实现方式 1：不成对比较

```sql
SELECT  employee_id, manager_id, department_id
FROM    employees
WHERE   manager_id IN
      (SELECT  manager_id
                   FROM    employees
                   WHERE   employee_id IN (174,141))
AND     department_id IN
      (SELECT  department_id
                   FROM    employees
                   WHERE   employee_id IN (174,141))
AND	employee_id NOT IN(174,141);
```

实现方式 2：成对比较

```sql
SELECT	employee_id, manager_id, department_id
FROM	employees
WHERE  (manager_id, department_id) IN
                      (SELECT manager_id, department_id
                       FROM   employees
                       WHERE  employee_id IN (141,174))
AND	employee_id NOT IN (141,174);
```

### 2.3 HAVING 中的子查询

- 首先执行子查询。

- 向主查询中的 HAVING 子句返回结果。

**题目：查询最低工资大于 50 号部门最低工资的部门 id 和其最低工资**

```sql
SELECT   department_id, MIN(salary)
FROM     employees
GROUP BY department_id
HAVING   MIN(salary) >
                       (SELECT MIN(salary)
                        FROM   employees
                        WHERE  department_id = 50);
```

### 2.4 CASE 中的子查询

在 CASE 表达式中使用单列子查询：

**题目：显式员工的 employee_id,last_name 和 location。其中，若员工 department_id 与 location_id 为 1800 的 department_id 相同，则 location 为’Canada’，其余则为’USA’。**

```sql
SELECT employee_id, last_name,
       (CASE department_id
        WHEN
             (SELECT department_id FROM departments
        WHERE location_id = 1800)
        THEN 'Canada' ELSE 'USA' END) location
FROM   employees;
```

### 2.5 子查询中的空值问题

```sql
SELECT last_name, job_id
FROM   employees
WHERE  job_id =
                (SELECT job_id
                 FROM   employees
                 WHERE  last_name = 'Haas');
```

![子查询中的空值问题](https://img-blog.csdnimg.cn/9dcf075df1264781af85f78f2449e8c2.png)

> **子查询不返回任何行**

### 2.5 非法使用子查询

```sql
SELECT employee_id, last_name
FROM   employees
WHERE  salary =
                (SELECT   MIN(salary)
                 FROM     employees
                 GROUP BY department_id);
```

![非法使用子查询](https://img-blog.csdnimg.cn/62feff54c9c94d31b6f6e008883af490.png)

> **多行子查询使用单行比较符**

## 3. 多行子查询

- 也称为集合比较子查询。

- 内查询返回多行。

- 使用多行比较操作符。

### 3.1 多行比较操作符

| 操作符 | 含义                                                           |
| ------ | -------------------------------------------------------------- |
| IN     | 等于列表中的**任意一个**。                                     |
| ANY    | 需要和单行比较操作符一起使用，和子查询返回的**某一个**值比较。 |
| ALL    | 需要和单行比较操作符一起使用，和子查询返回的**所有**值比较。   |
| SOME   | 实际上是 ANY 的别名，作用相同，一般常使用 ANY。                |

> 体会 ANY 和 ALL 的区别

### 3.2 代码示例

**题目：返回其它 job_id 中比 job_id 为‘IT_PROG’部门任一工资低的员工的员工号、姓名、job_id 以及 salary**

![代码示例](https://img-blog.csdnimg.cn/fddf8574653f40b3891cb14efd789501.png)

![代码示例](https://img-blog.csdnimg.cn/83ac05362d2f424b8a9467f5b8615ba3.png)

**题目：返回其它 job_id 中比 job_id 为‘IT_PROG’部门所有工资都低的员工的员工号、姓名、job_id 以及 salary**

![代码示例](https://img-blog.csdnimg.cn/34b8b4e3533e49ca850eca0d1a1e556f.png)

![代码示例](https://img-blog.csdnimg.cn/9a149296c589493e8a6f65027bacf5ef.png)

**题目：查询平均工资最低的部门 id**

```sql
# 方式1：
SELECT department_id
FROM employees
GROUP BY department_id
HAVING AVG(salary) = (
      SELECT MIN(avg_sal)
      FROM (
        SELECT AVG(salary) avg_sal
        FROM employees
        GROUP BY department_id
        ) dept_avg_sal
      )
```

```sql
# 方式2：
SELECT department_id
FROM employees
GROUP BY department_id
HAVING AVG(salary) <= ALL (
        SELECT AVG(salary) avg_sal
        FROM employees
        GROUP BY department_id
)
```

### 3.3 空值问题

```sql
SELECT last_name
FROM employees
WHERE employee_id NOT IN (
      SELECT manager_id
      FROM employees
      );
```

![空值问题](https://img-blog.csdnimg.cn/444c180fc1634979a258ee2064c49733.png)

## 4. 相关子查询

### 4.1 相关子查询执行流程

如果子查询的执行依赖于外部查询，通常情况下都是因为子查询中的表用到了外部的表，并进行了条件关联，因此每执行一次外部查询，子查询都要重新计算一次，这样的子查询就称之为`关联子查询`。

相关子查询按照一行接一行的顺序执行，主查询的每一行都执行一次子查询。

![相关子查询执行流程](https://img-blog.csdnimg.cn/22752e44b7314880a1b47cdf4f7dbf1e.png)

![相关子查询执行流程](https://img-blog.csdnimg.cn/fef4ad60ec6642809763fe1ef644365b.png)

说明：**子查询中使用主查询中的列**

### 4.2 代码示例

**题目：查询员工中工资大于本部门平均工资的员工的 last_name,salary 和其 department_id**

**方式一：相关子查询**

![代码示例](https://img-blog.csdnimg.cn/2cce308114cc4cb88ea182ebef860828.png)

**方式二：在 FROM 中使用子查询**

```sql
SELECT last_name,salary,e1.department_id
FROM employees e1,(SELECT department_id,AVG(salary) dept_avg_sal FROM employees GROUP BY department_id) e2
WHERE e1.`department_id` = e2.department_id
AND e2.dept_avg_sal < e1.`salary`;
```

> from 型的子查询：子查询是作为 from 的一部分，子查询要用()引起来，并且要给这个子查询取别名，把它当成一张“临时的虚拟的表”来使用。

在 ORDER BY 中使用子查询：

**题目：查询员工的 id,salary,按照 department_name 排序**

```sql
SELECT employee_id,salary
FROM employees e
ORDER BY (
    SELECT department_name
    FROM departments d
    WHERE e.`department_id` = d.`department_id`
  );
```

**题目：若 employees 表中 employee_id 与 job_history 表中 employee_id 相同的数目不小于 2，输出这些相同 id 的员工的 employee_id,last_name 和其 job_id**

```sql
SELECT e.employee_id, last_name,e.job_id
FROM   employees e
WHERE  2 <= (SELECT COUNT(*)
             FROM   job_history
             WHERE  employee_id = e.employee_id);
```

### 4.3 EXISTS 与 NOT EXISTS 关键字

- 关联子查询通常也会和 EXISTS 操作符一起来使用，用来检查在子查询中是否存在满足条件的行。

- **如果在子查询中不存在满足条件的行：**

  - 条件返回 FALSE。

  - 继续在子查询中查找。

- **如果在子查询中存在满足条件的行：**

  - 不在子查询中继续查找。

  - 条件返回 TRUE。

- NOT EXISTS 关键字表示如果不存在某种条件，则返回 TRUE，否则返回 FALSE。

**题目：查询公司管理者的 employee_id，last_name，job_id，department_id 信息**

方式一：

```sql
SELECT employee_id, last_name, job_id, department_id
FROM   employees e1
WHERE  EXISTS ( SELECT *
                 FROM   employees e2
                 WHERE  e2.manager_id =
                        e1.employee_id);
```

方式二：自连接

```sql
SELECT DISTINCT e1.employee_id, e1.last_name, e1.job_id, e1.department_id
FROM   employees e1 JOIN employees e2
WHERE e1.employee_id = e2.manager_id;
```

方式三：

```sql
SELECT employee_id,last_name,job_id,department_id
FROM employees
WHERE employee_id IN (
         SELECT DISTINCT manager_id
         FROM employees

         );
```

**题目：查询 departments 表中，不存在于 employees 表中的部门的 department_id 和 department_name**

```sql
SELECT department_id, department_name
FROM departments d
WHERE NOT EXISTS (SELECT 'X'
                  FROM   employees
                  WHERE  department_id = d.department_id);
```

![EXISTS 与 NOT EXISTS 关键字](https://img-blog.csdnimg.cn/ce062ed28fb54853b4e7d87ffa4dd774.png)

### 4.4 相关更新

```sql
UPDATE table1 alias1
SET    column = (SELECT expression
                 FROM   table2 alias2
                 WHERE  alias1.column = alias2.column);
```

使用相关子查询依据一个表中的数据更新另一个表的数据。

**题目：在 employees 中增加一个 department_name 字段，数据为员工对应的部门名称**

```sql
ALTER TABLE employees
ADD(department_name VARCHAR2(14));

UPDATE employees e
SET department_name =  (SELECT department_name
                         FROM   departments d
                         WHERE  e.department_id = d.department_id);

```

### 4.4 相关删除

```sql
 DELETE FROM table1 alias1
 WHERE column operator (SELECT expression
                        FROM   table2 alias2
                        WHERE  alias1.column = alias2.column);
```

使用相关子查询依据一个表中的数据删除另一个表的数据。

**题目：删除表 employees 中，其与 emp_history 表皆有的数据**

```sql
DELETE FROM employees e
WHERE employee_id in
           (SELECT employee_id
            FROM   emp_history
            WHERE  employee_id = e.employee_id);
```

## 5. 抛一个思考题

**问题：** 谁的工资比 Abel 的高？

**解答：**

```sql
# 方式1：自连接
SELECT e2.last_name,e2.salary
FROM employees e1,employees e2
WHERE e1.last_name = 'Abel'
AND e1.`salary` < e2.`salary`
```

```sql
# 方式2：子查询
SELECT last_name,salary
FROM employees
WHERE salary > (
    SELECT salary
    FROM employees
    WHERE last_name = 'Abel'
    );
```

**问题：** 以上两种方式有好坏之分吗？

**解答：** 自连接方式好！

题目中可以使用子查询，也可以使用自连接。一般情况建议你使用自连接，因为在许多 DBMS 的处理过程中，对于自连接的处理速度要比子查询快得多。

可以这样理解：子查询实际上是通过未知表进行查询后的条件判断，而自连接是通过已知的自身数据表进行条件判断，因此在大部分 DBMS 中都对自连接处理进行了优化。
