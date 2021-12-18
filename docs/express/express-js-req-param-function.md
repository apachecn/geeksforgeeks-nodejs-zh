# Express.js req.param()函数

> 原文:[https://www . geesforgeks . org/express-js-req-param-function/](https://www.geeksforgeeks.org/express-js-req-param-function/)

**req.param()** 函数存在时基本返回 param 名称的值。当传递参数时，可以使用这个函数访问它。
**语法:**

```
req.param(name [, defaultValue])
```

**参数:**名称参数是参数的名称。
**返回值:**字符串。
**快递模块安装:**

1.  您可以访问[安装快速模块](https://www.npmjs.com/package/express)的链接。您可以使用此命令安装此软件包。

```
npm install express
```

1.  安装快速模块后，您可以使用命令在命令提示符下检查您的快速版本。

```
npm version express
```

1.  之后，您可以创建一个文件夹并添加一个文件，例如 index.js。

```
node index.js
```

**示例 1:** **文件名:index.js**

## java 描述语言

```
var express = require('express');
var app = express();
var PORT = 3000;

app.get('/', function (req, res) {
    //reading single parameter
    console.log(req.param('title'));
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

1.  使用以下命令确保您已经安装了 **express** 模块:

```
npm install express
```

1.  使用以下命令运行 index.js 文件:

```
node index.js
```

1.  **输出:**

```
Server listening on PORT 3000
```

2.  现在向 *http://localhost:3000 发出 GET 请求？title=GeeksforGeeks* ，然后您将在控制台上看到以下输出:

```
Server listening on PORT 3000
GeeksforGeeks
```

**示例 2:** **文件名:index.js**

## java 描述语言

```
var express = require('express');
var app = express();
var PORT = 3000;

app.get('/', function (req, res) {

    // Reading multiple parameter
    console.log("Title:", req.param('title'));
    console.log("Domain:", req.param('domain'));

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

现在向 *http://localhost:3000 发出 GET 请求？title = GeeksforGeeks&domain = CS*，然后您将在控制台上看到以下输出:

```
Server listening on PORT 3000
Title: GeeksforGeeks
Domain: CS
```

**参考:**[https://expressjs . com/en/4x/API . html # req . param](https://expressjs.com/en/4x/api.html#req.param)