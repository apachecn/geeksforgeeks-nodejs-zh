# Express.js res.end()功能

> 原文:[https://www.geeksforgeeks.org/express-js-res-end-function/](https://www.geeksforgeeks.org/express-js-res-end-function/)

**res.end()** 功能用于结束响应过程。这个方法实际上来自 Node 核心，具体就是 HTTP.ServerResponse 的 response.end()方法，用来快速结束没有任何数据的响应。
**语法:**

```js
res.end([data] [, encoding])
```

**参数:**默认编码为‘utf8’，数据参数基本上是用户想要结束响应的数据。
**返回值:**返回实物。
**快递模块安装:**

1.  您可以访问[安装快速模块](https://www.npmjs.com/package/express)的链接。您可以使用此命令安装此软件包。

```js
npm install express
```

1.  安装快速模块后，您可以使用命令在命令提示符下检查您的快速版本。

```js
npm version express
```

1.  之后，您可以创建一个文件夹并添加一个文件，例如 index.js。

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

```js
npm install express
```

1.  使用以下命令运行 index.js 文件:

```js
node index.js
```

1.  **输出:**

```js
Server listening on PORT 3000
```

2.  现在打开浏览器，转到 *http://localhost:3000/* 会看到空白响应，因为这个函数是用来快速结束没有任何数据的响应。

**示例 2:** **文件名:index.js**

## java 描述语言

```js
var express = require('express');
var app = express();
var PORT = 3000;

// With middleware
app.use('/user', function(req, res, next){
     console.log("/user called")
     res.end();
})

app.get('/user', function(req, res){
    console.log("User Page")
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

现在打开你的浏览器，进入*http://localhost:3000/user*，然后你会在你的控制台上看到如下输出:

```js
Server listening on PORT 3000
/user called
```

**参考:**[https://expressjs . com/en/4x/API . html # RES . end](https://expressjs.com/en/4x/api.html#res.end)