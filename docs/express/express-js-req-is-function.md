# Express.js req.is()功能

> 原文:[https://www.geeksforgeeks.org/express-js-req-is-function/](https://www.geeksforgeeks.org/express-js-req-is-function/)

如果传入请求的“内容类型”HTTP 头字段与类型参数指定的 MIME 类型匹配，函数将返回匹配的内容类型，如果请求没有正文，则返回 null，否则返回 false。

**语法:**

```js
req.is( type )
```

**参数:**类型参数是指定的 MIME 类型。

**返回值:**字符串(如果为真)或假。

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

app.get('/', function (req, res) {
    console.log(req.is('text/plain')); 
    res.end();
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

4.  现在向 *http://localhost:3000/* 发出 GET 请求，并将标题设置为**“内容类型:文本/普通”**，然后您将在控制台上看到以下输出:

    ```js
    Server listening on PORT 3000
    text/plain

    ```

**示例 2:** **文件名:index.js**

```js
var express = require('express');
var app = express();
var PORT = 3000;

app.get('/', function (req, res) {
    console.log(req.is('text/html')); 
    res.end();
});

app.listen(PORT, function(err){
    if (err) console.log(err);
    console.log("Server listening on PORT", PORT);
});
```

使用以下命令运行 index.js 文件:

```js
node index.js
```

现在向 *http://localhost:3000/* 发出 GET 请求，并将标题设置为**“内容类型:文本/纯文本”**，然后您将在控制台上看到以下输出:

```js
Server listening on PORT 3000
false

```

**参考:**[https://expressjs . com/en/4x/API . html # req . is](https://expressjs.com/en/4x/api.html#req.is)