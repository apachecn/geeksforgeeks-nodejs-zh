# 如何用 Node.js 和 Express.js 在 REST API 中实现搜索和过滤？

> 原文:[https://www . geeksforgeeks . org/如何通过节点-js-and-express-js/](https://www.geeksforgeeks.org/how-to-implement-search-and-filtering-in-a-rest-api-with-node-js-and-express-js/) 实现静态搜索和过滤 api

搜索和过滤是应用编程接口必须具备的非常基本的功能，以便有效地向客户端应用程序提供数据。通过在服务器端处理这些操作，我们可以减少必须在客户端应用程序上完成的处理量，从而提高其性能。

一种非常流行的实现方式是借助查询字符串。查询字符串是 URL 的一部分，它允许我们以参数及其值的形式将数据从客户端传递到服务器，反之亦然。

**语法:**

```
http://test.com?name=John&age=21
```

这里，问号**后面的部分(？)**是查询字符串。这些基本上是键值对，我们可以用于各种目的。在本文中，我们将看到如何构建一个 Node.js REST API，它可以接受这些查询字符串，根据这些提供的参数过滤用户列表，然后返回匹配的结果。

**设置项目:**

*   首先，我们必须使用[节点包管理器](https://nodejs.org/en/download/)初始化一个新项目。我们可以通过选择所有默认选项来完成设置。

    ```
    npm init
    ```

*   接下来，我们要安装快递包裹。

    ```
    npm install express --save
    ```

这个应用程序的入口点将是 **app.js** 文件。我们所有的业务逻辑都在这里。REST 应用编程接口将只包含一条返回用户列表的路由，并支持使用查询字符串进行搜索和过滤。

**示例:**最初，app.js 文件看起来是这样的，路由只返回一条基本消息。

## app . js

```
const express = require('express');
const data = require('./data');

// Initialize App
const app = express();

// Assign route
app.use('/', (req, res, next) => {
  res.send('Node.js Search and Filter');
});

// Start server on PORT 5000
app.listen(5000, () => {
  console.log('Server started!');
});
```

**添加模拟数据:**为了进行搜索和过滤，我们需要一些模拟数据，即我们可以对其进行这些操作的用户列表。为此，我们可以单独创建一个文件

```
const data = [
  { id: 1, name: 'Alan Wake', age: 21, city: 'New York' },
  { id: 2, name: 'Steve Rogers', age: 106, city: 'Chicago' },
  { id: 3, name: 'Tom Hanks', age: 47, city: 'Detroit' },
  { id: 4, name: 'Ryan Burns', age: 16, city: 'New York' },
  { id: 5, name: 'Jack Ryan', age: 31, city: 'New York' },
  { id: 6, name: 'Clark Kent', age: 34, city: 'Metropolis' },
  { id: 7, name: 'Bruce Wayne', age: 21, city: 'Gotham' },
  { id: 8, name: 'Tim Drake', age: 21, city: 'Gotham' },
  { id: 9, name: 'Jimmy Olsen', age: 21, city: 'Metropolis' },
  { id: 10, name: 'Ryan Burns', age: 21, city: 'New York' },
];

module.exports = data;
```