# Express.js express.raw()功能

> 原文:[https://www . geesforgeks . org/express-js-express-raw-function/](https://www.geeksforgeeks.org/express-js-express-raw-function/)

**express.raw()** 功能是 express 中内置的中间件功能。它将传入的请求有效负载解析到一个缓冲区中，并基于主体解析器。

**语法:**

```js
express.raw( [options] )
```

**参数:**选项参数包含各种属性，如膨胀、限制、类型等。

**返回值:**返回一个对象。

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

app.use(express.raw());

app.post('/', function (req, res) {
    console.log(req.body);
    res.end();
})

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

4.  现在向 *http://localhost:3000/* 发出 POST 请求，头部设置为**‘内容类型’–‘应用程序/八位字节流’**和正文 **{“名称”:“GeeksforGeeks”}**，然后您将在屏幕上看到以下输出:
    ![](img/40359ebf9dde034e337b5cae141d95da.png)

**示例 2:** **文件名:index.js**

```js
var express = require('express');
var app = express();
var PORT = 3000;

// Without this middleware
// app.use(express.raw());
app.post('/', function (req, res) {
    console.log(req.body);
    res.end();
})

app.listen(PORT, function(err){
    if (err) console.log(err);
    console.log("Server listening on PORT", PORT);
});
```

使用以下命令运行 index.js 文件:

```js
node index.js
```

现在向 *http://localhost:3000/* 发出 POST 请求，将头设置为**‘内容类型’–‘应用程序/八位字节流’**和正文 **{“名称”:“geeks forgeeks”}**，然后您将在屏幕上看到以下输出:

```js
Server listening on PORT 3000
undefined

```

**参考:** [官方文件](https://expressjs.com/en/4x/api.html#express.raw)