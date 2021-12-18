# Node.js MySQL LCASE()函数

> 原文:[https://www.geeksforgeeks.org/node-js-mysql-lcase-function/](https://www.geeksforgeeks.org/node-js-mysql-lcase-function/)

**LCASE()** 函数是 MySQL 中的内置函数，用于将给定字符串的所有字符转换为小写。

**语法:**

```js
LCASE(input_string)
```

**参数:**取一个参数如下:

*   **input_string** :作为参数传递的输入字符串，用于将该字符串转换为小写。

**返回值:**返回一个新的小写字符串。

**模块安装:**使用以下命令安装 **mysql** 模块:

```js
npm install mysql
```

**数据库:**我们的 SQL **发布者** 带有样本数据的表格预览如下所示:

![](img/534657a55e995a601f42564a686b906b.png)

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

db_con.connect((err) => {
    if (err) {
      console.log("Database Connection Failed !!!", err);
      return;
    }

    console.log("We are connected to gfg_db database");

    // Here is the query
    let query = 
"SELECT LCASE('This iNpUT strinG @!#$%^&*()?') AS lowercase_name";

    db_con.query(query, (err, rows) => {
        if(err) throw err;

        console.log(rows);
    });
});
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

![](img/d0fa9b92e2ab062a9bbb7e84c565a6a8.png)

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

db_con.connect((err) => {
    if (err) {
      console.log("Database Connection Failed !!!", err);
      return;
    }

    console.log("We are connected to gfg_db database");

    // Here is the query
    let query = 
"SELECT LCASE(name) AS lowercase_name FROM publishers";

    db_con.query(query, (err, rows) => {
        if(err) throw err;

        console.log(rows);
    });
});
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

![](img/b6b1c0468c666a0ab60bc1c04ad95bb1.png)