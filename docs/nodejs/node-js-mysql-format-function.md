# Node.js MySQL FORMAT()函数

> 原文:[https://www . geesforgeks . org/node-js-MySQL-format-function/](https://www.geeksforgeeks.org/node-js-mysql-format-function/)

**FORMAT()** 函数是 MySQL 中的一个内置函数，用于将输入的数字格式化为**……**、* *、***** 的格式，并将浮点数舍入到特定的小数位数。

**语法:**

```
FORMAT(number, number_of_decimal_places)
```

**参数:**取两个参数如下:

*   **数字:**用于格式化的数字。
*   **小数位数:**是小数位数。

**返回值:**返回一个格式化的数字，格式为**……**，* *，***** 。

**模块安装:**使用以下命令安装 **mysql** 模块:

```
npm install mysql
```

**数据库:**我们的 SQL **发布者** 带有样本数据的表格预览如下所示:

![](img/862e0dc0654aee673b376e8190bacaa5.png)

**例 1:**

## index.js

```
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
    let query = "SELECT FORMAT(12345678.12555, 2) AS output";

    db_con.query(query, (err, rows) => {
        if(err) throw err;

        console.log(rows);
    });
});
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

![](img/da213472266c2bda9238162a1fffeef9.png)

**例 2:**

## index.js

```
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
"SELECT FORMAT(salary, 1) AS formatted_salary FROM publishers";

    db_con.query(query, (err, rows) => {
        if(err) throw err;

        console.log(rows);
    });
});
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

![](img/e62db1a9dc223486b6ba16f0f24a0305.png)