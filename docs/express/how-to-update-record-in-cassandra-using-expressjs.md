# 如何使用 ExpressJS 更新 Cassandra 中的记录？

> 原文:[https://www . geesforgeks . org/如何使用-expressjs/](https://www.geeksforgeeks.org/how-to-update-record-in-cassandra-using-expressjs/) 更新 cassandra 中的记录

Apache Cassandra 是一个免费开源、分布式、高度可扩展、宽列存储的 NoSQL 数据库管理系统。它旨在处理大量数据，提供无单点故障的高可用性。

本文向您展示了如何使用 express js 使用 Cassandra，还展示了如何使用 express Cassandra orm 框架更新 Cassandra 中的记录。

**特性:**本文使用了以下特性。

*   Use the docker Hub to configure Cassandra docker container.
*   express-Cassandra ORM-express jso express Cassandraúlvo。
*   CQLSH (Cassandra Query Language Shell) command.

**示例:**本示例在 Cassandra 数据存储中创建具有以下列/属性的 Person Table。

## Javascript

```js
module.exports = {
   fields:{
       name    : "text",
       surname : "text",
       age     : "int",
       created : "timestamp"
   },
   key:["name"]
}
```