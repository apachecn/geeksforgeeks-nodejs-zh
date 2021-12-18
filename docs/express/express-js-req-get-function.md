# Express.js req.get()函数

> 原文:[https://www.geeksforgeeks.org/express-js-req-get-function/](https://www.geeksforgeeks.org/express-js-req-get-function/)

**req.get()** 函数返回指定的 HTTP 请求头字段，该字段不区分大小写，referer 和 referer 字段可以互换。

**语法:**

```
req.get( field )
```

**参数:**字段参数指定 HTTP 请求头字段。

**返回值:**字符串。

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
var PORT = 3000;

app.get('/', function (req, res) {
    console.log(req.get('Content-Type')); 
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

4.  现在向 *http://localhost:3000/* 发出 GET 请求，并将标题设置为**“内容类型:文本/普通”**，然后您将在控制台上看到以下输出:

    ```
    Server listening on PORT 3000
    text/plain

    ```

**示例 2:** **文件名:index.js**

```
var express = require('express');
var app = express();
var PORT = 3000;

app.get('/', function (req, res) {
    console.log(req.get('Anything-else')); 
    res.end();
});

app.listen(PORT, function(err){
    if (err) console.log(err);
    console.log("Server listening on PORT", PORT);
});
```

使用以下命令运行 index.js 文件:

```
node index.js
```

现在向 *http://localhost:3000/* 发出 GET 请求，然后您将在控制台上看到以下输出:

```
Server listening on PORT 3000
undefined

```

**参考:**[https://expressjs . com/en/4x/API . html # req . get](https://expressjs.com/en/4x/api.html#req.get)