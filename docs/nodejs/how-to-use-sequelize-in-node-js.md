# 如何在 Node.js 中使用 Sequelize？

> 原文:[https://www . geeksforgeeks . org/使用方法-sequelize in node-js/](https://www.geeksforgeeks.org/how-to-use-sequelize-in-node-js/)

Sequelize 是一个基于承诺的 Node.js ORM，适用于 Postgres、MySQL、MariaDB、SQLite 和微软 SQL Server。它的特点是坚实的事务支持、关系、急切和懒惰的加载、读复制等等。

Sequelize 的特性:

*   Sequelize is a third-party package, specifically a **object relational mapping library (ORM).** 。
*   **Standardized** forms usually have a single schema definition in the code. This makes it very clear what the pattern is, and it is very simple to change it.
*   **No need to learn SQL** -The query is written in plain JavaScript.

**设置 Node.js app:**

*   Use the following command to start node.jsapp:

    ```
    npm init -y
    ```

**安装 Sequelize:**

1.  Sequelize needs to install MySql module in your project. If you have not installed MySql module yet, please make sure that you need to install [MySQL 2 module](https://www.npmjs.com/package/mysql2) before installing Sequelize. You need to use the following command to install this module.

    ```
    npm install mysql2
    ```

2.  After installing *MySQL 2 module* , we need to install [Sequelize module](https://www.npmjs.com/package/sequelize) to install this module with the following command.

    ```
    npm install sequelize
    ```

**需求模块:**

*   You need to use these lines to include the Sequelize module in the project.

    ```
    const Sequelize = require('sequelize');
    ```

**配置**文件:

```
// Include Sequelize module
const Sequelize = require('sequelize')

// Creating new Object of Sequelize
const sequelize = new Sequelize(
    'DATABASE_NAME',
    'DATABASE_USER_NAME',
    'DATABASE_PASSWORD', {

        // Explicitly specifying 
        // mysql database
        dialect: 'mysql',

        // By default host is 'localhost'           
        host: 'localhost'
    }
);

// Exporting the sequelize object. 
// We can use it in another file
// for creating models
module.exports = sequelize
```