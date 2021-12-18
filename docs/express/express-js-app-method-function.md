# Express.js | app。方法()功能

> 原文:[https://www . geesforgeks . org/express-js-app-method-function/](https://www.geeksforgeeks.org/express-js-app-method-function/)

**应用。METHOD()函数**用于路由一个 HTTP 请求，其中 METHOD 是请求的 HTTP 方法，比如 GET、PUT、POST 等等，小写。因此，实际的方法是 app.get()，app.post()，app.put()，等等。

**语法:**

```js
app.METHOD(path, callback [, callback ...])
```

**参数:**

1.  **路径:**调用中间件功能的路径，可以是以下任意路径:
    *   表示路径的字符串。
    *   路径模式。
    *   匹配路径的正则表达式模式。
    *   上述任意组合的数组。
2.  **回调:**回调函数可以是:

*   中间件功能。
*   一系列中间件功能(用逗号分隔)。
*   一系列中间件功能。
*   以上所有内容的组合。

**快递模块安装:**

1.  您可以访问[安装快速模块](https://www.npmjs.com/package/express)的链接。您可以使用此命令安装此软件包。

    ```js
    npm install express
    ```

2.  安装 express 模块后，您可以使用命令在命令提示符下检查您的 express 版本。

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
var PORT = 3000;

// Handling GET Request
app.get('/user', function(req, res){
    res.send("Handled GET Request");
});

// Handling POST Request
app.post('/user', function(req, res){
    res.send("Handled POST Request");
});

// Handling DELETE Request
app.delete('/remove', function(req, res){
    res.send("Handled DELETE Request");
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

    ```js
    npm install express
    ```

3.  Run index.js file using below command:

    ```js
    node index.js
    ```

    **输出:**

    ```js
    Server listening on Port 3000

    ```

所以这就是你如何使用快递**应用。METHOD()** 函数，是请求的 HTTP 方法，比如 GET、PUT、POST 等等，小写。