# next()函数在 Express.js 中有什么用？

> 原文:[https://www . geesforgeks . org/express-js/](https://www.geeksforgeeks.org/what-is-the-use-of-next-function-in-express-js/)下一个函数的用途是什么

[Express.js](https://www.geeksforgeeks.org/working-of-express-js-middleware-and-its-benefits/) 是 node.js 的一个强大框架，这个框架的一个主要优势就是定义了不同的路由或者中间件来处理客户端不同的传入请求。在本文中，我们将讨论 next()函数在 express.js 的每个中间件中的使用。

Express.js 中有很多中间件功能，比如 [Express.js app.use()](https://www.geeksforgeeks.org/express-js-app-use-function/) 功能等等。 *app.use()* 中间件基本上用于定义客户端发出的特定请求的处理程序。

**语法:**

```js
app.use(path,(req,res,next))
```

**参数:**接受上述两个参数，描述如下:

*   **路径:**是调用中间件函数的路径。它可以是表示路径或路径模式的字符串，也可以是匹配路径的正则表达式模式。
*   **回调:**是包含请求对象、响应对象、**和** next()函数的回调函数，如果当前中间件的响应没有终止，则调用下一个中间件函数。在第二个参数中，我们还可以传递中间件的函数名。

**安装模块:**使用以下命令安装快速模块。

```js
npm install express
```

**项目结构:**会是这样的。

![](img/680c11a4a464432626c22f3eee5f7f10.png)

**示例 1:** 没有 next()功能的服务器

## index.js

```js
// Importing the express module
const express = require("express");
const app = express()

// Creating First Middleware
app.use("/", (req, res, next) => {
    console.log("Hello");
    // There is no next() function calls here
})

// Creating second middlware
app.get("/", (req, res, next) => {
    console.log("Get Request")
})

// Execution the server
app.listen(3000, () => {
    console.log("Server is Running")
})
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**如果没有 next()函数，中间件不会调用下一个中间件，即使它们请求相同的路径

```js
Server is Running
Hello
```

**示例 2:** 具有 next()功能的服务器

## index.js

```js
// Importing the express module
const express = require("express");
const app = express()

// Creating First Middleware
app.use("/", (req, res, next) => {
    console.log("Hello");
    // The next() function called
    next();
})

// Creating second middlware
app.get("/", (req, res, next) => {
    console.log("Get Request")
})

// Execution the server
app.listen(3000, () => {
    console.log("Server is Running")
})
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
Server is Running
Hello
Get Request
```