# Express.js res.render()函数

> 原文:[https://www . geesforgeks . org/express-js-RES-render-function/](https://www.geeksforgeeks.org/express-js-res-render-function/)

**res.render()** 函数用于渲染视图，并将渲染后的 HTML 字符串发送给客户端。

**语法:**

```
res.render(view [, locals] [, callback])
```

**参数:**该函数接受两个参数，如上所述，如下所述:

*   **局部变量:**它基本上是一个对象，其属性定义了视图的局部变量。
*   **回调**是一个回调函数。

**返回:**返回一个对象。

**快递模块安装:**

1.您可以访问[安装快速模块](https://www.npmjs.com/package/express)的链接。您可以使用此命令安装此软件包。

```
npm install express
```

2.安装快速模块后，您可以使用命令在命令提示符下检查您的快速版本。

```
npm version express
```

3.之后，您可以创建一个文件夹并添加一个文件，例如 index.js。

```
node index.js
```

**示例 1:** **文件名:index.js**

## java 描述语言

```
var express = require('express');
var app = express();
var PORT = 3000;

// View engine setup
app.set('view engine', 'ejs');

// Without middleware
app.get('/user', function(req, res){

    // Rendering home.ejs page
    res.render('home');
})

app.listen(PORT, function(err){
    if (err) console.log(err);
    console.log("Server listening on PORT", PORT);
});
```

在视图文件夹中创建一个 **home.ejs** 文件，代码如下:
**文件名:home.ejs**

## 超文本标记语言

```
<html>
<head>
    <title>res.render() Demo</title>
</head>
<body>
    <h2>Welcome to GeeksforGeeks</h2>
</body>
</html>
```

**运行程序的步骤:**

1.使用以下命令确保您已经安装了 **express** 和 **ejs** 模块:

```
npm install express
npm install ejs
```

2.使用以下命令运行 index.js 文件:

```
node index.js
```

**输出:**

```
Server listening on PORT 3000
```

3.现在打开浏览器，转到*http://localhost:3000/user*，您可以在屏幕上看到以下输出:

```
Welcome to GeeksforGeeks
```

**示例 2:** **文件名:index.js**

## java 描述语言

```
var express = require('express');
var app = express();
var PORT = 3000;

// View engine setup
app.set('view engine', 'ejs');

// With middleware
app.use('/', function(req, res, next){
    res.render('User')
    next();
});

app.get('/', function(req, res){
    console.log("Render Working")
    res.send();
});

app.listen(PORT, function(err){
    if (err) console.log(err);
    console.log("Server listening on PORT", PORT);
});
```

在视图文件夹中创建一个 **User.ejs** 文件，代码如下:
**文件名:User.ejs**

## 超文本标记语言

```
<html>
<head>
    <title>res.render() Demo</title>
</head>
<body>
    <h2>Render Function Demo</h2>
</body>
</html>
```

使用以下命令运行 index.js 文件:

```
node index.js
```

运行上述命令后，您将在控制台屏幕上看到以下输出:

```
Server listening on PORT 3000
Render Working
```

现在打开浏览器，转到 *http://localhost:3000* ，在你的屏幕上可以看到如下输出:

```
Render Function Demo
```

**参考:**[https://expressjs . com/en/5x/API . html # RES . render](https://expressjs.com/en/5x/api.html#res.render)