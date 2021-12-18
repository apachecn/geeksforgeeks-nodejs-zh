# Express.js | app.param()功能

> 原文:[https://www . geesforgeks . org/express-js-app-param-function/](https://www.geeksforgeeks.org/express-js-app-param-function/)

**app.param()** 函数用于将回调触发器添加到路由参数中。它通常用于检查所请求的与路线参数相关的数据是否存在。

**语法:**

```
app.param([name], callback)
```

**参数:**

1.  **名称:**是参数的名称或它们的数组。
2.  **回调:**是作为参数传递的函数。

**快递模块安装:**

1.  您可以访问[安装快速模块](https://www.npmjs.com/package/express)的链接。您可以使用此命令安装此软件包。

    ```
    npm install express
    ```

2.  安装快速模块后，您可以使用命令在命令提示符下检查您的快速版本。

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

app.param('id', function (req, res, next, id) {
    console.log('CALLED ONLY ONCE');
    next();
});

app.get('/user/:id', function (req, res, next) {
    console.log('Greetings from geeksforgeeks');
    next();
});

app.get('/user/:id', function (req, res) {
    console.log('Once again greetings from geeksforgeeks');
    res.end();
});

app.listen(PORT, function(err){
    if (err) console.log("Error in server setup");
    console.log("Server listening on Port", PORT);
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
    Server listening on Port 3000

    ```

4.  打开浏览器，进入*http://localhost:3000/user/42*。现在检查你的控制台，以下将是输出:

    ```
    Server listening on Port 3000
    CALLED ONLY ONCE
    Greetings from geeksforgeeks
    Once again greetings from geeksforgeeks

    ```

这就是如何使用 express **app.param()** 函数添加回调触发器来路由参数。