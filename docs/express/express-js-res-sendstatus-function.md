# Express.js res.sendStatus()功能

> 原文:[https://www . geesforgeks . org/express-js-RES-send status-function/](https://www.geeksforgeeks.org/express-js-res-sendstatus-function/)

**res.sendStatus()** 函数用于将响应 HTTP 状态代码设置为 status code，并将其字符串表示作为响应体发送。
**语法:**

```
res.sendStatus( statusCode )
```

**参数:**status code 参数描述 HTTP 状态代码。
**返回:**返回一个对象。
**快递模块安装:**

*   您可以访问[安装快速模块](https://www.npmjs.com/package/express)的链接。您可以使用此命令安装此软件包。

```
npm install express
```

*   安装快速模块后，您可以使用命令在命令提示符下检查您的快速版本。

```
npm version express
```

*   之后，您可以创建一个文件夹并添加一个文件，例如 index.js。

```
node index.js
```

**示例 1:** **文件名:index.js**

## java 描述语言

```
var express = require('express');
var app = express();
var PORT = 3000;

// Without middleware
app.get('/', function(req, res){

    // Equivalent to res.status(200).send('OK')
    res.sendStatus(200);
});

app.listen(PORT, function(err){
    if (err) console.log(err);
    console.log("Server listening on PORT", PORT);
});
```

**运行程序的步骤:**

*   项目结构会是这样的:

![](img/3209d9b4369c180282a34be8070d7d6e.png)

*   使用以下命令确保您已经安装了 **express** 模块:

```
npm install express
```

*   使用以下命令运行 index.js 文件:

```
node index.js
```

**输出:**

```
Server listening on PORT 3000
```

*   现在打开浏览器，转到 *http://localhost:3000/* ，现在检查你的浏览器屏幕，你会看到如下输出:

```
OK
```

**示例 2:** **文件名:index.js**

## java 描述语言

```
var express = require('express');
var app = express();
var PORT = 3000;

// With middleware
app.use('/', function(req, res, next){
    res.sendStatus(200);
    next();
});

app.get('/', function(req, res){
    res.send();
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

现在打开浏览器，转到 *http://localhost:3000/* ，现在检查你的控制台，你会看到如下输出:

```
Server listening on PORT 3000
```

您将在浏览器屏幕上看到以下输出:

```
OK
```

**参考:**[https://expressjs . com/en/5x/API . html # RES . sendstatus](https://expressjs.com/en/5x/api.html#res.sendStatus)