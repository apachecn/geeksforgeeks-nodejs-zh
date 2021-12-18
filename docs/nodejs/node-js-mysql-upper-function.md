# Node.js MySQL UPPER()函数

> 原文:[https://www.geeksforgeeks.org/node-js-mysql-upper-function/](https://www.geeksforgeeks.org/node-js-mysql-upper-function/)

**UPPER()** 函数是 MySQL 中的内置函数，用于将给定字符串的所有字符转换为大写。

**语法:**

```js
UPPER(input_string)
```

**参数:**取一个参数如下:

*   **input_string** :传递给大写转换的是给定的字符串。

**返回值:**返回一个新的大写字符串。

**模块安装:**使用以下命令安装 **mysql** 模块:

```js
npm install mysql
```

**数据库:**我们的 SQL **发布者** 带有样本数据的表格预览如下所示:

![Database table](img/862e0dc0654aee673b376e8190bacaa5.png)

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
    let query = "SELECT UPPER('This iNpUT 
          strinG @!#$%^&*()?') AS uppercase_name";

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

![index.js file execution](img/d357f700a4f6eab801c54b51da606881.png)

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
    let query = "SELECT name, UPPER(name) AS 
              uppercase_name FROM publishers";

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

![index.js file execution](img/3989485534eddcfd3450341450c6e926.png)