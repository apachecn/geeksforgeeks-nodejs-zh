# 如何在 Express.js 中使用 handle get 请求？

> 原文:[https://www . geesforgeks . org/如何使用-处理-获取-请求-in-express-js/](https://www.geeksforgeeks.org/how-to-use-handle-get-request-in-express-js/)

**简介:** Express.js 是 node.js 最强大的框架，是一个处理网页不同路由的路由和中间件框架，工作在请求和响应周期之间。它使用不同类型的中间件功能来完成客户端对 Eg 的不同请求。客户端可以发出 get、put、post 和 delete 请求，这些请求可以通过这些中间件功能轻松处理。

在本文中，我们将讨论如何在 express.js 中处理 get 请求，express.js 的 [app.get()](https://www.geeksforgeeks.org/express-js-app-get-request-function/#:~:text=get()%20Request%20Function,-Last%20Updated%20%3A%2005&text=The%20app.,the%20middleware%20to%20your%20application.) 方法用于处理来自客户端的传入 get 请求基本上是为了将中间件绑定到您的应用程序。

**语法:**

```
app.get( path, callback )
```

**参数:**

*   **路径:**是调用中间件函数的路径。
*   **回调:**它们可以是中间件函数，也可以是中间件函数的系列/数组。

**注意:**使用 express.js 中间件的优势之一我们可以使用 express.js 的每个请求处理功能中存在的 next()函数来转发传入的请求，参考 [**这篇**](https://www.geeksforgeeks.org/working-of-express-js-middleware-and-its-benefits/) **文章。**

**我们来看看分步实现。**

**第一步:创建 npm 项目，清空 package.json 文件。**

```
npm init
```

**步骤 2:使用以下命令安装快速模块。**

```
npm install express
```

**项目结构:我们的项目结构会如下图所示。**

![](img/d2312c8a3bef348413d47abc45f72213.png)

**示例 1:在本例中，我们将创建一条有 get 请求和无 get 请求转发的路由。**

**文件名:index.js**

## java 描述语言

```
// Importing expresss
const express=require("express")
const app=express();

// Handling get request
app.get("/get",(req,res,next)=>{
  res.send("This is the get request");

})
app.get("/get/users",(req,res,next)=>{
    res.send("This is the get/users request")
})
app.listen(8000,()=>{
    console.log("Server is Running");
})
```