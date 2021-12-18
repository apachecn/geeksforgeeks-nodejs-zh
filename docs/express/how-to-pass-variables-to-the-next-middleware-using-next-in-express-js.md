# 如何使用 Express.js 中的 next()将变量传递给下一个中间件？

> 原文:[https://www . geesforgeks . org/如何使用下一个 in-express-js 将变量传递给下一个中间件/](https://www.geeksforgeeks.org/how-to-pass-variables-to-the-next-middleware-using-next-in-express-js/)

以下示例介绍了如何使用 Express.js 中的 next()将变量传递给下一个中间件

**进场:**

我们不能直接将数据传递给下一个中间件，但是我们可以通过请求对象发送数据。

> [中间件 1][中间件 2]
> request . mydata = some data；——- >让 data from middleware 1 = request . my data；

**快递模块安装:**

您可以访问链接 [<u>安装快递模块</u>](https://www.npmjs.com/package/express) 。您可以使用此命令安装此软件包。

```
npm install express
```

之后，您可以创建一个文件夹并添加一个文件，例如 index.js。

```
node index.js
```

**文件名:index.js**

## java 描述语言

```
// Requiring module
const express = require("express");
const app = express();

function middleware1(req, res, next) {
  // Set data
  req.dataFromMiddleware1 = "Data of Middleware 1";

  // Go to next middleware
  next();
}

function middleware2(req, res, next) {
  console.log("We are in Middleware 2.");

  // Get Data of Middleware1
  console.log(req.dataFromMiddleware1);

  // Go to next middleware
  next();
}

// Handling Get Request '/'
app.get("/", middleware1, middleware2, (req, res) => {
  return res.send(req.dataFromMiddleware1);
});

// Server Setup
app.listen(5000, () => {
  console.log(`Server is up and running on 5000 ...`);
});
```

**运行程序的步骤:**

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

我们将在控制台上看到以下输出:

```
Server is up and running on 5000 ...

```

现在打开浏览器，转到***http://localhost:5000/，**你会在屏幕上看到如下输出:*

![](img/5fd1c60b9196e14a31ab6a5aab2676e3.png)

浏览器上的输出

现在再次检查终端输出，如下所示:

```
Server is up and running on 5000 ...
We are in Middleware 2.
Data of Middleware 1
```