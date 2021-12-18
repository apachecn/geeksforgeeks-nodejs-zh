# Express.js router.param()功能

> 原文:[https://www . geesforgeks . org/express-js-router-param-function/](https://www.geeksforgeeks.org/express-js-router-param-function/)

**router.param()** 的参数为**名称**和一个**功能**。其中**名称**为参数实际名称，**函数**为回调函数。基本上 router.param()函数在用户路由到该参数时触发回调函数。该回调函数在请求响应周期中只被调用一次，即使用户多次路由到该参数。

**语法:**

```js
router.param(name, function)
```

**回调函数参数为:**

1.  请求–请求对象
2.  RES–响应对象
3.  下一个——下一个中间件功能
4.  id——名称参数的值

首先，您需要将 express 节点模块安装到您的 node js 应用程序中。

**快速 js 的安装如下:**

```js
npm init 
npm install express 
```

创建一个文件名 **app.js** 并将以下代码粘贴到文件中。

```js
//
const express = require("express");
const app = express();

//import router module from route.js file
const userRoutes = require("./route");

app.use("/", userRoutes);

//PORT
const port = process.env.PORT || 8000;

//Starting a server
app.listen(port, () => {
  console.log(`app is running at ${port}`);
});
```

我们必须在同一目录下创建另一个名为 **route.js** 的文件

**route.js** 文件的代码

```js
const express = require("express");
const router = express.Router();

router.param("userId", (req, res, next, id) => {
    console.log("This function will be called first");
    next();
});

router.get("/user/:userId", (req, res) => {
    console.log("Then this function will be called");
    res.end();
});
// Export router 
module.exports = router;
```

通过输入以下命令启动服务器

```js
node app.js
```

在浏览器中输入以下地址

![](img/902024419411ee93377c0a4b7c4af12a.png)

http://localhost:8000/user/343

您将在终端中看到以下输出

![](img/1fe73ad335fdfe44741721c993f7a219.png)