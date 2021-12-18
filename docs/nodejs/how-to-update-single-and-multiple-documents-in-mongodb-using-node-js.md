# 如何使用 Node.js 更新 MongoDB 中的单个和多个文档？

> 原文:[https://www . geesforgeks . org/如何更新-mongodb 中的单个和多个文档-使用节点-js/](https://www.geeksforgeeks.org/how-to-update-single-and-multiple-documents-in-mongodb-using-node-js/)

**MongoDB** 最受欢迎的 NoSQL 数据库，是一个开源的面向文档的数据库。术语“NoSQL”的意思是“非关系的”。这意味着 MongoDB 不是基于类似表的关系数据库结构，而是提供了一种完全不同的数据存储和检索机制。这种存储格式称为 BSON(类似于 JSON 格式)。参考([本](https://www.geeksforgeeks.org/mongodb-an-introduction/))篇。

**MongoDB 模块:**node . js 的这个模块用于连接 MongoDB 数据库，也用于操作 MongoDB 中的集合和数据库。mongodb.connect()方法用于连接在您的计算机上的特定服务器上运行的 mongodb 数据库。(参考[这篇](https://www.geeksforgeeks.org/how-to-connect-mongodb-server-with-node-js/)文章)。我们还可以在这个方法中使用 promises 来解析包含集合操作所需的所有方法和属性的对象，并在连接过程中拒绝出现的错误。

**安装模块:**

```
node install mongodb

```

**项目结构:**

![](img/680c11a4a464432626c22f3eee5f7f10.png)

**在本地 IP 上运行服务器:**

```
mongod --dbpath=data --bind_ip 127.0.0.1

```

![](img/b17079668307c9a66022081b23d3c23d.png)

**MongoDB 数据库:**

```
Database:GFG
Collection:GFGcollections

```

**GFG 数据库结构:**

![](img/70bba757025e358fbb7a109566b7bdb0.png)

**Index.js:**

## java 描述语言

```
const MongoClient = require("mongodb");
const url = 'mongodb://localhost:27017/';
const databasename = "GFG";   // Database name
MongoClient.connect(url).then((client) => {

    const connect = client.db(databasename);

    // Connect to collection
    const collection = connect
            .collection("GFGcollections");

    // Update one collection
    collection.updateOne(
        { "name": "saini" }, 
        { $set: { "class": "bye" } }
    );

    // Update multiple documents having
    // GFGNEW class
    collection.updateMany(
        { "class": "GFGNEW" }, 
        { $set: { "class": "GFG" } }
    );

    console.log("update successful");
}).catch((err) => {

    // Handling the error
    console.log(err.Message);
})
```

**输出:**

![](img/e9e05f9e85fd401922f8bc8b99e4a318.png)

**更新 MongoDb 收藏:**

![](img/08b73c208545a1783e2c2e2c20c7e435.png)