# Express.js res.send()功能

> 原文:[https://www.geeksforgeeks.org/express-js-res-send-function/](https://www.geeksforgeeks.org/express-js-res-send-function/)

**res.send()** 功能基本发送 HTTP 响应。正文参数可以是字符串、缓冲区对象、对象或数组。

**语法:**

```js
res.send( [body] )
```

**参数:**该函数接受单个参数**正文**，该参数描述响应中要发送的正文。

**返回:**返回一个对象。

**快递模块安装:**

1.您可以访问[安装快速模块](https://www.npmjs.com/package/express)的链接。您可以使用此命令安装此软件包。

```js
npm install express
```

2.安装快速模块后，您可以使用命令在命令提示符下检查您的快速版本。

```js
npm version express
```

3.之后，您可以创建一个文件夹并添加一个文件，例如 index.js。

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
    res.send({ title: 'GeeksforGeeks' });
});

app.listen(PORT, function(err){
    if (err) console.log(err);
    console.log("Server listening on PORT", PORT);
});
```

**运行程序的步骤:**

1.项目结构如下所示:

![](img/3209d9b4369c180282a34be8070d7d6e.png)

2.使用以下命令确保您已经安装了 **express** 模块:

```js
npm install express
```

3.使用以下命令运行 index.js 文件:

```js
node index.js
```

**输出:**

```js
Server listening on PORT 3000
```

4.现在打开浏览器，转到 *http://localhost:3000/* ，现在检查你的浏览器，你会看到如下输出:

```js
{"title":"GeeksforGeeks"}
```

**示例 2:** **文件名:index.js**

## java 描述语言

```js
var express = require('express');
const path = require('path');
var app = express();
var PORT = 3000;

// With middleware
app.use('/', function(req, res, next){
   res.send({"name":"GeeksforGeeks"});
   next();
});

app.get('/', function(req, res){
    console.log("Body Sent")
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

现在打开浏览器，转到 *http://localhost:3000/* ，现在检查你的控制台，你会看到如下输出:

```js
Server listening on PORT 3000
Body Sent
```

您将在浏览器屏幕上看到以下输出:

```js
{"name":"GeeksforGeeks"}
```

**参考:**[https://expressjs . com/en/5x/API . html # RES . send](https://expressjs.com/en/5x/api.html#res.send)