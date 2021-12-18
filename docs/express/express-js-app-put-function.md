# Express.js | app.put()功能

> 原文:[https://www.geeksforgeeks.org/express-js-app-put-function/](https://www.geeksforgeeks.org/express-js-app-put-function/)

**app.put()函数**通过指定的回调函数将 HTTP PUT 请求路由到指定的路径。

**语法:**

```
app.put(path, callback [, callback ...])
```

**论据:**

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

app.put('/', (req, res) => {
  res.send("PUT Request Called")
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

4.  现在向 *http://localhost:3000/* 发出 PUT 请求，会得到如下输出:

    ```
    PUT Request Called
    ```

这就是如何使用 express **app.put()** 函数，该函数使用指定的回调函数将 HTTP PUT 请求路由到指定的路径。