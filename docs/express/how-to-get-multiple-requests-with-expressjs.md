# 如何用 ExpressJS 获取多个请求？

> 原文:[https://www . geesforgeks . org/how-to-get-multi-requests-with-express js/](https://www.geeksforgeeks.org/how-to-get-multiple-requests-with-expressjs/)

**Express.js** 是 [node.js](https://www.geeksforgeeks.org/working-of-express-js-middleware-and-its-benefits/) 最强大的框架。Express.js 是一个路由和中间件框架，用于处理网页的不同路由，它在请求和响应周期之间工作。Express.js 使用不同种类的中间件功能以便完成发出的不同请求客户端对于例如客户端可以发出 get、 put、 post 、和删除请求这些请求可以通过这些中间件功能轻松处理

**工作的** **中间件** **功能:**

![](img/dd781d8749a4ffc38c006e9da1a7a8a1.png)

**安装模块:**使用以下命令安装快速模块。

```js
npm install express
```

**项目结构:**我们的项目结构会是这样的。

![](img/d2312c8a3bef348413d47abc45f72213.png)

**使用 Express.js 处理多个请求:**

Express.js 包含多种方法来处理所有类型的请求，而不是处理单一类型的请求，如下所示:

*   [**express . js req . get()**](https://www.geeksforgeeks.org/express-js-req-get-function/)**方法:**客户端发出 get 请求时使用该方法，例如重定向另一个网页请求等
*   [**express . js req . post()**](https://www.geeksforgeeks.org/express-js-app-post-function/)**方法:**该方法用于客户端发出帖子请求时，例如上传文档等。
*   [**express . js req . delete()**](https://www.geeksforgeeks.org/express-js-app-delete-function/)**方法:**该方法在客户端执行删除请求时使用，主要由管理端执行，例如从服务器删除记录。
*   [**express . js req . put()**](https://www.geeksforgeeks.org/express-js-app-put-function/)**方法:**客户端通过网站进行更新请求更新信息时使用此方法。

![](img/680c11a4a464432626c22f3eee5f7f10.png)

## index.js

```js
// Requiring module 
const express = require("express"); 

// Creating express app object 
const app = express(); 

app.post("/check",(req,res,next)=>{
  res.send("This is the post request")
  next()
})

app.get("/gfg",(req,res,next)=>{
  res.send("This is the get request")
  res.end()
})

app.delete("/gfgdelete",(req,res,next)=>{
  res.send("This is the delete request");
  res.end()
})

// Server setup 
app.listen(3000, () => { 
  console.log("Server is Running"); 
})
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
Server is Running
```

**处理多个请求:**现在打开邮递员工具，发送以下请求:

*   **来自客户端的删除请求:**

    ![](img/c87d09f9973ae1de08277a61c4bba0d2.png)

*   **从客户端获取请求:**

    ![](img/521aa791d72dddff035c880d668e569d.png)