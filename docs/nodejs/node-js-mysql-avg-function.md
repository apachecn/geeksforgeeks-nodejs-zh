# Node.js MySQL AVG()函数

> 原文:[https://www.geeksforgeeks.org/node-js-mysql-avg-function/](https://www.geeksforgeeks.org/node-js-mysql-avg-function/)

我们使用 AVG 函数来获取 MySQL 表的给定列中所有行的平均值。

**语法:**

```js
AVG([column_name])
```

**参数:** AVG()函数接受单个参数，如上所述，如下所述。

*   **列名:**我们要从中返回平均值的列名。

**模块安装:**使用以下命令安装 **mysql** 模块。

```js
npm install mysql
```

**数据库:**我们的 SQL **发布者** 带有样本数据的表格预览如下所示:

![](img/80ff88815de592500f8a01f6035f3226.png)

**例 1:**

## index.js

```js
const mysql = require("mysql");

let db_con  = mysql.createConnection({
    host: "localhost",
    user: "root",
    password: '',
    database: 'gfg_db'
});

db_con.on('error', (err) => {
    console.log(err.code);
});

db_con.connect((err) => {
    if (err) {
      console.log("Database Connection Failed !!!", err.code);
      return;
    }

    console.log("We are connected to gfg_db database");

    // Here is the query
    let query = "SELECT AVG(salary) AS avg_salary FROM publishers";

    db_con.query(query, (err, rows) => {
        if(err) throw err;

        console.log(rows);
    });
});
```

使用以下命令运行 **index.js** 文件。

```js
node index.js
```

**输出:**

![](img/a66e59df614d9d0ab1f5f84c64b55cb0.png)

**例 2:**

## index.js

```js
const mysql = require("mysql");

let db_con  = mysql.createConnection({
    host: "localhost",
    user: "root",
    password: '',
    database: 'gfg_db'
});

db_con.on('error', (err) => {
    console.log(err.code);
});

db_con.connect((err) => {
    if (err) {
      console.log("Database Connection Failed !!!", err.code);
      return;
    }

    console.log("We are connected to gfg_db database");

    // Here is the query
    let query = "SELECT AVG(salary) AS avg_salary 
                 FROM publishers WHERE id < 8";

    db_con.query(query, (err, rows) => {
        if(err) throw err;

        console.log(rows);
    });
});
```

使用以下命令运行 **index.js** 文件。

```js
node index.js
```

**输出:**

![](img/8beeac2d099438e76423a6faf3b2ab3c.png)