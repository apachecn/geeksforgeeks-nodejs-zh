# Express.js req.range()函数

> 原文:[https://www . geesforgeks . org/express-js-req-range-function/](https://www.geeksforgeeks.org/express-js-req-range-function/)

**req.range()** 函数基本上是一个 range 头解析器，其中 Accept-Ranges 响应头字段允许服务器指示其接受资源的范围请求。

**语法:**

```
req.range(size[, options])
```

**参数:**

1.  **大小:**是资源的最大大小。
2.  **选项:**是可以有*组合*属性的对象。

**返回值:**返回一个范围数组。

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
    console.log(req.get('Range'));    
    console.log(req.range());
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

4.  现在向 *http://localhost:3000/* 发出 GET 请求，头部设置为**“范围:字节= 200-1000”**，然后您将在控制台上看到以下输出:

    ```
    Server listening on PORT 3000
    bytes=200-1000
    [ { start: 200, end: 1000 }, type: 'bytes' ]

    ```

**示例 2:** **文件名:index.js**

```
var express = require('express');
var app = express();
var PORT = 3000;

app.get('/', function (req, res) {

    // Without range header set
    console.log(req.range());
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

现在向 *http://localhost:3000/* 发出 GET 请求，不设置任何头，那么在你的控制台上会看到如下输出:

```
Server listening on PORT 3000
undefined

```

**参考:**[https://expressjs . com/en/5x/API . html # req . range](https://expressjs.com/en/5x/api.html#req.range)