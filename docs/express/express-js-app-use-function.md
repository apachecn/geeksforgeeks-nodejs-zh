# Express.js | app.use()功能

> 原文:[https://www.geeksforgeeks.org/express-js-app-use-function/](https://www.geeksforgeeks.org/express-js-app-use-function/)

**app.use()** 函数用于在指定的路径上安装指定的中间件函数。它主要用于为您的应用程序设置中间件。

**语法:**

```
app.use(path, callback)
```

**参数:**

1.  **路径:**是调用中间件函数的路径。它可以是表示路径或路径模式的字符串，也可以是匹配路径的正则表达式模式。
2.  **回调:**是一个中间件函数或一系列/数组中间件函数。

**快递模块安装:**

1.  您可以访问[安装快速模块](https://www.npmjs.com/package/express)的链接。您可以使用此命令安装此软件包。

    ```
    npm install express
    ```

2.  安装 express 模块后，您可以使用命令在命令提示符下检查您的 express 版本。

    ```
    npm version express
    ```

3.  之后，您可以创建一个文件夹并添加一个文件，例如 index.js。

    ```
    node index.js
    ```

**文件名:index.js**

```
var express = require('express');
var app = express();
var PORT = 3000;

// This middleware will not allow the
// request to go beyond it
app.use(function (req, res, next) {
    console.log("Middleware called")
    next();
});

// Requests will never reach this route
app.get('/user', function (req, res) {
    console.log("/user request called");
    res.send('Welcome to GeeksforGeeks');
});

app.listen(PORT, function(err){
    if (err) console.log(err);
    console.log("Server listening on PORT", PORT);
});
```

**运行程序的步骤:**

1.  项目结构会是这样的:
    ![](img/3209d9b4369c180282a34be8070d7d6e.png)
2.  使用以下命令确保您已经安装了 **express** 模块:

    ```
    npm install express
    ```

3.  Run index.js file using below command:

    ```
    node index.js
    ```

    **输出:**

    ```
    Server listening on PORT 3000

    ```

4.  Now open your browser and go to *http://localhost:3000/user* and you can see the following output on console as shown below:

    ```
    Server listening on PORT 3000
    Middleware called
    /user request called

    ```

    在浏览器上你会看到**欢迎来到极客论坛**。