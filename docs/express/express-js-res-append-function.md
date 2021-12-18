# Express.js res.append()函数

> 原文:[https://www . geesforgeks . org/express-js-RES-append-function/](https://www.geeksforgeeks.org/express-js-res-append-function/)

**res.append()** 函数将指定的值追加到 HTTP 响应头字段中，如果还没有设置头，则使用指定的值创建头。
**语法:**

```js
res.append(field [, value])
```

**参数:**字段参数描述需要追加的字段名称，值参数可以是字符串，也可以是数组。
**返回:**返回一个对象。
**快递模块安装:**

*   您可以访问[安装快速模块](https://www.npmjs.com/package/express)的链接。您可以使用此命令安装此软件包。

```js
npm install express
```

*   安装快速模块后，您可以使用命令在命令提示符下检查您的快速版本。

```js
npm version express
```

*   之后，您可以创建一个文件夹并添加一个文件，例如 index.js。

```js
node index.js
```

**示例 1:** **文件名:index.js**

## java 描述语言

```js
var express = require('express');
var app = express();
var PORT = 3000;

// Without middleware
app.get('/', function(req, res){
    res.append('Warning', '201 Warning');
    console.log(res.get('Warning')); // 201 Warning
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

```js
npm install express
```

*   使用以下命令运行 index.js 文件:

```js
node index.js
```

**输出:**

```js
Server listening on PORT 3000
```

*   打开浏览器，转到 *http://localhost:3000/* ，现在在控制台上看到如下输出:

```js
Server listening on PORT 3000
201 Warning
```

**示例 2:** **文件名:index.js**

## java 描述语言

```js
var express = require('express');
var app = express();
var PORT = 3000;

// With middleware
app.use('/', function(req, res, next){
    res.append('Warning', '201 Its a Warning');
    next();
})

app.get('/', function(req, res){
    console.log(res.get('Warning'));
    res.send();
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

现在，打开浏览器，转到 *http://localhost:3000/* ，现在检查您的控制台，您将看到以下输出:

```js
Server listening on PORT 3000
201 Its a Warning
```

**参考:**[https://expressjs . com/en/5x/API . html # RES . append](https://expressjs.com/en/5x/api.html#res.append)