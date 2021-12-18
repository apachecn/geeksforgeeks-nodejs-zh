# Express.js res.attachment()功能

> 原文:[https://www . geesforgeks . org/express-js-RES-attachment-function/](https://www.geeksforgeeks.org/express-js-res-attachment-function/)

**res.attachment()** 功能用于将 HTTP 响应内容-处置头字段设置为“附件”。如果文件名是给定的，那么它通过 res.type()函数根据扩展名设置内容类型，最后设置内容处理“文件名=”参数。
**语法:**

```js
res.attachment( [filename] )
```

**参数:**文件名参数描述文件的名称。
**返回值:**返回一个对象。
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
    res.attachment('Hello.txt');
    console.log(res.get('Content-Disposition'));
});

app.listen(PORT, function(err){
    if (err) console.log(err);
    console.log("Server listening on PORT", PORT);
});
```

将任何可以附加的文件放在项目的根目录中，就像这里我们使用的 **Hello.txt** 一样。
T3】运行程序的步骤:T5】

1.  项目结构会是这样的:

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

*   打开浏览器，转到 *http://localhost:3000/* ，现在可以在控制台上看到如下输出:

```js
Server listening on PORT 3000
attachment; filename="Hello.txt"
```