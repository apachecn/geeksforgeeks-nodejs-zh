# Express.js 快递。路由器()功能

> 原文:[https://www . geesforgeks . org/express-js-express-router-function/](https://www.geeksforgeeks.org/express-js-express-router-function/)

**快车。Router()** 功能用于创建新的路由器对象。当您想在程序中创建一个新的路由器对象来处理请求时，可以使用这个函数。

**语法:**

```js
express.Router( [options] )
```

**可选参数:**

*   **区分大小写:**这将启用区分大小写。
*   **合并参数:**它保留来自父路由器的 req.params 值。
*   **严格:**这样可以实现严格的路由。

**返回值:**该函数返回新的路由器对象。

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

**示例 1:** **文件名:index.js**

```js
var express = require('express');
var app = express();
var PORT = 3000;

// Single routing
var router = express.Router();

router.get('/', function (req, res, next) {
    console.log("Router Working");
    res.end();
})

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

4.  现在打开浏览器，进入 *http://localhost:3000/* ，屏幕上会出现如下输出:

    ```js
    Server listening on PORT 3000
    Router Working

    ```

**示例 2:** **文件名:index.js**

```js
var express = require('express');
var app = express();
var PORT = 3000;

// Multiple routing
var router1 = express.Router();
var router2 = express.Router();
var router3 = express.Router();

router1.get('/user', function (req, res, next) {
    console.log("User Router Working");
    res.end();
});

router2.get('/admin', function (req, res, next) {
    console.log("Admin Router Working");
    res.end();
});

router2.get('/student', function (req, res, next) {
    console.log("Student Router Working");
    res.end();
});

app.use(router1);
app.use(router2);
app.use(router3);

app.listen(PORT, function(err){
    if (err) console.log(err);
    console.log("Server listening on PORT", PORT);
});
```

使用以下命令运行 index.js 文件:

```js
node index.js
```

现在向*http://localhost:3000/用户*、*http://localhost:3000/admin*和*http://localhost:3000/学生*发出 GET 请求，然后您将在控制台上看到以下输出:

```js
Server listening on PORT 3000
User Router Working
Admin Router Working
Student Router Working

```

**参考:** [官方文件](https://expressjs.com/en/4x/api.html#express.router)