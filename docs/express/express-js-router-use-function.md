# Express.js | router.use()功能

> 原文:[https://www . geesforgeks . org/express-js-router-use-function/](https://www.geeksforgeeks.org/express-js-router-use-function/)

**router.use()** 函数使用指定的一个或多个中间件函数。它基本上为特定路由器服务的路由安装中间件。

**语法:**

```js
router.use( path, function )
```

**参数:**

1.  **路径:**就是到这个中间件的路径，就像如果我们能有*/用户*的话，现在这个中间件是为所有有这个路由器的*/用户*的 API 调用的。
2.  **函数:**这个函数被传递一个 a 回调，在这个路由器中调用指定路径时被调用。

**快递模块安装:**

1.  您可以访问[安装快速模块](https://www.npmjs.com/package/express)的链接。您可以使用此命令安装此软件包。

    ```js
    npm install express
    ```

2.  安装快速模块后，您可以使用命令在命令提示符下检查您的快速版本。

    ```js
    npm version express
    ```

3.  之后，您可以创建一个文件夹并添加一个文件，例如 index.js。

    ```js
    node index.js
    ```

**文件名:index.js**

```js
var express = require('express');
var app = express();
var router = express.Router();
var PORT = 3000;

// All requests to this router will
// first hit this middleware
router.use(function (req, res, next) {
  console.log("Middleware Called");
  next();
})

// Always invoked
router.use(function (req, res, next) {
  res.send("Greetings from GeeksforGeeks");
})

app.use('/user', router);

app.listen(PORT, function(err){
    if (err) console.log(err);
    console.log("Server listening on PORT", PORT);
});
```

**运行程序的步骤:**

1.  项目结构会是这样的:
    ![](img/3209d9b4369c180282a34be8070d7d6e.png)
2.  使用以下命令确保您已经安装了 **express** 模块:

    ```js
    npm install express
    ```

3.  Run index.js file using below command:

    ```js
    node index.js
    ```

    **输出:**

    ```js
    Server listening on PORT 3000

    ```

4.  Now open your browser and go to *http://localhost:3000/user*, you can see the following output on your screen:

    ```js
    Server listening on PORT 3000
    Middleware Called

    ```

    您将在浏览器上看到以下输出:

    ```js
    Greetings from GeeksforGeeks
    ```