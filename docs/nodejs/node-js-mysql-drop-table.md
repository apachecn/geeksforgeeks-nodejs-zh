# Node.js MySQL 投递表

> 原文:[https://www.geeksforgeeks.org/node-js-mysql-drop-table/](https://www.geeksforgeeks.org/node-js-mysql-drop-table/)

删除表查询用于从 MySQL 数据库中删除或删除表。

**语法:**

*   这将删除用户表。但是，如果用户表不在那里，这将引发错误。

    ```js
    DROP TABLE users
    ```

    *   仅当用户表存在时，此操作才会将其删除。

    ```js
    DROP TABLE IF EXISTS users
    ```

    **模块:**

    *   mysql:处理 MySQL 连接和查询

        ```js
        npm install mysql
        ```

    **SQL*****gfg _ db***
    **数据库预览(显示表格):**

    ![](img/f4ee5641597d9381f4f2191d11484612.png)

    **示例 1:** 删除用户表

    ## java 描述语言

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

        // here is our query
        let query = 'DROP TABLE users';

        db_con.query(query, (err, rows) => {
            if(err) throw err;

            console.log('Deleted users Table');
        });
    });
    ```

    **输出:**

    ![](img/4ec5e7083deac294fec0c65e9df542be.png)

    **示例 2:** 仅当用户表存在时才删除用户表

    ## java 描述语言

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

        // notice the if exists in below query
        let query = 'DROP TABLE IF EXISTS users';

        db_con.query(query, (err, rows) => {
            if(err) throw err;

            console.log('Deleted users Table');
        });
    });
    ```

    **输出:**

    ![](img/4ec5e7083deac294fec0c65e9df542be.png) ![](img/71e3715307381e8ba4d181ba206e879d.png)