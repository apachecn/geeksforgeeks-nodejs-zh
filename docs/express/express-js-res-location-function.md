# Express.js | res.location()功能

> 原文:[https://www . geesforgeks . org/express-js-RES-location-function/](https://www.geeksforgeeks.org/express-js-res-location-function/)

**res.location()** 函数用于将响应位置 HTTP 头设置为正在指定的路径参数。基本上是用来设置响应头的。它不会结束响应，在使用它之后，如果你想写，你可以写一个响应体。

**语法:**

```js
res.location( path )
```

**参数:**

*   **路径:**是指请求的**引用者**头中指定的网址。

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
var PORT = 3000;

app.get('/', function(req, res){
    res.location('http://demo.com');
    console.log(res.get('location')); // http://demo.com
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

4.  现在打开浏览器，转到 *http://localhost:3000/* ，现在检查你的控制台，你会看到如下输出:

    ```js
    Server listening on PORT 3000
    http://demo.com

    ```