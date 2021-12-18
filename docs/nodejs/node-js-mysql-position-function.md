# Node.js MySQL POSITION()函数

> 原文:[https://www . geesforgeks . org/node-js-MySQL-position-function/](https://www.geeksforgeeks.org/node-js-mysql-position-function/)

**POSITION()** 函数是 MySQL 中的一个内置函数，用于从特定位置搜索时获取文本中某个模式第一次出现的位置。

**注意:**不区分大小写。

**语法:**

```js
POSITION(pattern IN text)
```

**参数:** POSITION()函数接受两个参数，如上所述，如下所述。

*   **模式:**要搜索的模式
*   **文本:**在该文本中，将搜索模式

**返回值:** POSITION()函数返回从特定位置搜索时文本中第一个模式出现的位置。如果出现问题，它将返回 0。

**模块:**

*   **mysql:** 处理 mysql 连接和查询

```js
npm install mysql
```

**SQL 发布者表预览:**

![](img/862e0dc0654aee673b376e8190bacaa5.png)

**例 1:**

## java 描述语言

```js
const mysql = require("mysql");

let db_con = mysql.createConnection({
  host: "localhost",
  user: "root",
  password: "",
  database: "gfg_db",
});

db_con.connect((err) => {
  if (err) {
    console.log("Database Connection Failed !!!", err);
    return;
  }

  console.log("We are connected to gfg_db database");

  // notice the ? in query
  let query = `SELECT POSITION('for' IN 'GEEKSFORGEEKS') AS POSITION_Output`;

  db_con.query(query, (err, rows) => {
    if (err) throw err;

    console.log(rows);
  });
});
```

**输出:**

![](img/92a7323b18d72a476c607c5d1656740a.png)

**例 2:**

## java 描述语言

```js
const mysql = require("mysql");

let db_con = mysql.createConnection({
  host: "localhost",
  user: "root",
  password: "",
  database: "gfg_db",
});

db_con.connect((err) => {
  if (err) {
    console.log("Database Connection Failed !!!", err);
    return;
  }

  console.log("We are connected to gfg_db database");

  // notice the ? in query
  let query = `SELECT name, POSITION('a' IN name) 
               AS POSITION_Output FROM publishers`;

  db_con.query(query, (err, rows) => {
    if (err) throw err;

    console.log(rows);
  });
});
```

**输出:**

![](img/a2aac5043b5351810410f83403ec37c6.png)