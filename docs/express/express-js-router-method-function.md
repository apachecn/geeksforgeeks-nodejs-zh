# Express.js 路由器。方法()功能

> 原文:[https://www . geesforgeks . org/express-js-router-method-function/](https://www.geeksforgeeks.org/express-js-router-method-function/)

**路由器。METHOD()** 方法在 Express 中提供路由功能，其中 METHOD 是 HTTP 方法之一，如 GET、PUT、POST 等，小写。

**语法:**

```
router.METHOD(path, [callback, ...] callback)
```

**参数:**path 参数指定 URL 上的路径，回调是调用该路径时执行的函数。

**返回值:**因为它提供了路由功能，所以可以返回响应。

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

**示例 1:** **文件名:index.js**

```
var express = require('express');
var app = express();
var router = express.Router();
var PORT = 3000;

// Single route 
router.get('/user', function (req, res, next) {
    console.log("GET request called");
    res.end();
});

app.use(router);

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

4.  现在向 *http://localhost:3000/* 发出 GET 请求，您可以在屏幕上看到以下输出:

    ```
    Server listening on PORT 3000
    GET request called

    ```

**示例 2:** **文件名:index.js**

```
var express = require('express');
var app = express();
var router = express.Router();
var PORT = 3000;

// Multiple routes  
router.get('/user', function (req, res, next) {
    console.log("GET request called");
    res.end();
});

router.post('/user', function (req, res, next) {
    console.log("POST request called");
    res.end();
});

router.delete('/user', function (req, res, next) {
    console.log("DELETE request called");
    res.end();
})

app.use(router);

app.listen(PORT, function(err){
    if (err) console.log(err);
    console.log("Server listening on PORT", PORT);
});
```

使用以下命令运行 index.js 文件:

```
node index.js
```

现在向 *http://localhost:3000/* 发出 GET、POST、DELETE 请求，在屏幕上可以看到如下输出:

```
Server listening on PORT 3000
GET request called
POST request called
DELETE request called

```

**参考:**T2】https://expressjs.com/en/4x/api.html#router.METHOD