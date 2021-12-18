# Express.js res.cookie()功能

> 原文:[https://www . geesforgeks . org/express-js-RES-cookie-function/](https://www.geeksforgeeks.org/express-js-res-cookie-function/)

**res.cookie()** 函数用于将 cookie 名称设置为值。值参数可以是转换为 JSON 的字符串或对象。
**语法:**

```
res.cookie(name, value [, options])
```

**参数:**name 参数保存 cookie 的名称，value 参数是分配给 cookie 名称的值。options 参数包含各种属性，如编码、过期、域等。
**返回值:**返回一个对象。
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

// Without middleware
app.get('/', function(req, res){

    // key-value
    res.cookie('name', 'geeksforgeeks');
    res.send("Cookie Set");
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

2.  打开浏览器，进入 *http://localhost:3000/* ，现在你的屏幕上出现了如下输出:

```
Cookie Set
```

**示例 2:** **文件名:index.js**

## java 描述语言

```
var express = require('express');
var app = express();
var PORT = 3000;

// With middleware
app.use('/', function(req, res, next){
    res.cookie('title', 'GeeksforGeeks');
    res.send("Cookie Set");
    next();
})

app.get('/', function(req, res){
    console.log('Cookie SET');
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
Cookie SET
```

您将在浏览器上看到以下输出:

```
Cookie Set
```

**参考:**[https://expressjs . com/en/5x/API . html # RES . cookie](https://expressjs.com/en/5x/api.html#res.cookie)