# 用 Express

在 Node.js 中构建您的第一台路由器

> 原文:[https://www . geesforgeks . org/build-your-first-in-router-node-js-with-express/](https://www.geeksforgeeks.org/build-your-first-router-in-node-js-with-express/)

[Express.js](https://www.geeksforgeeks.org/working-of-express-js-middleware-and-its-benefits/) 是 node.js 的一个强大框架，这个框架的一个主要优势就是定义了不同的路由或者中间件来处理客户端不同的传入请求。在本文中，我们将讨论如何在 express.js 服务器中使用路由器。

**快车。Router()** 功能用于创建新的路由器对象。当您想在程序中创建一个新的路由器对象来处理请求时，可以使用这个函数。借助 Express.js 中的 Router()函数，可以轻松区分多个请求。这就是使用 Router 的优势。

**语法:**

```js
express.Router( [options] )
```

**可选参数:**

*   **区分大小写:**这将启用区分大小写。
*   **合并参数:**保留请求。来自父路由器的参数值。
*   **严格:**这样可以实现严格的路由。

**返回值:**该函数返回新的路由器对象。>

**安装模块:**

```js
npm install express
```

**项目结构:**如下图。

![](img/f09bf3bc101970f33ef36a9d7c1a9987.png)

**现在我们将创建所有路线:**

**步骤 1:** 在路由文件夹内部创建 Home.js 文件，该文件将处理“/home”网址。

## Home.js

```js
// Importing express module
const express=require("express")
const router=express.Router()

// Handling request using router
router.get("/home",(req,res,next)=>{
    res.send("This is the homepage request")
})

// Importing the router
module.exports=router
```

**步骤 2:** 现在我们将创建第二条路由，用于登录，并将处理“/log in”URL。

## log in . js-登入

```js
// Importing the module
const express=require("express")

// Creating express Router
const router=express.Router()

// Handling login request
router.get("/login",(req,res,next)=>{
  res.send("This is the login request")
})
module.exports=router
```

**步骤 3:** 现在在 index.js 文件中，我们将导入所有创建的路由并使用它们。

## Index.js

```js
const express=require("express")
// Importing all the routes
const homeroute=require("./routes/Home.js")
const loginroute=require("./routes/login")

// Creating express server
const app=express()

// Handling routes request
app.use("/",homeroute)
app.use("/",loginroute)
app.listen((3000),()=>{
    console.log("Server is Running")
})
```

**运行应用程序的步骤:**打开终端，使用以下命令运行 **index.js** :

```js
node index.js
```

**输出:**打开浏览器，键入 localhost:3000，处理客户端的/home 请求。

![](img/534776c85cd625fcc36b8b7fba077443.png)