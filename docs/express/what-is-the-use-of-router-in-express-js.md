# 路由器在 Express.js 中有什么用？

> 原文:[https://www . geesforgeks . org/express-js 中路由器的用途是什么/](https://www.geeksforgeeks.org/what-is-the-use-of-router-in-express-js/)

[Express.js](https://www.geeksforgeeks.org/working-of-express-js-middleware-and-its-benefits/) 是 node.js 的一个强大框架，这个框架的一个主要优势就是定义了不同的路由或者中间件来处理客户端不同的传入请求。在本文中，我们将讨论如何在 express.js 服务器中使用路由器。

**快车。Router()** 功能用于创建新的路由器对象。当您想在程序中创建一个新的路由器对象来处理请求时，可以使用这个函数。借助 Express.js 中的 Router()函数，可以轻松区分多个请求。这就是使用 Router 的优势。

**语法:**

```js
express.Router( [options] )
```

**参数:**该函数接受一个可选参数，其属性如下所示。

*   **区分大小写:**这将启用区分大小写。
*   **合并参数:**它保留来自父路由器的请求参数值。
*   **严格:**这样可以实现严格的路由。

**返回值:** 该函数返回新的路由器对象。

**安装模块:**使用以下命令安装模块。

```js
npm install express
```

**项目结构:**会是这样的。

![](img/f09bf3bc101970f33ef36a9d7c1a9987.png)

**注意:*****路线*** 文件夹包含 *Home.js* 和 *login.js* 文件。

**实施:**

## Home.js

```js
// Importing express module
const express = require("express")

// Creating express router
const router = express.Router()

// Handling request using router
router.get("/home", (req,res,next) => {
    res.send("This is the homepage request")
})

// Exporting router
module.exports = router
```

## log in . js-登入

```js
// Importing the module
const express = require("express")

// Creating express Router
const router = express.Router()

// Handling login request
router.get("/login", (req,res,next) => {
  res.send("This is the login request")
})

module.exports = router
```

## index.js

```js
// Requiring module
const express = require("express")

// Importing all the routes
const homeroute = require("./routes/Home.js")
const loginroute = require("./routes/login")

// Creating express server
const app = express()

// Handling routes request
app.use("/", homeroute)
app.use("/", loginroute)

// Server setup
app.listen((3000), () => {
    console.log("Server is Running")
})
```

使用以下命令运行 **index.js** :

```js
node index.js
```

**输出:**我们将在终端屏幕上看到以下输出。

```js
Server is Running
```

现在转到***http://localhost:3000/登录*** 和***http://localhost:3000/home，*** 我们会在浏览器屏幕上看到如下输出。

![](img/534776c85cd625fcc36b8b7fba077443.png)