# Express.js res.sendFile()功能

> 原文:[https://www . geesforgeks . org/express-js-RES-sendfile-function/](https://www.geeksforgeeks.org/express-js-res-sendfile-function/)

**res.sendFile()** 函数基本上以给定的路径传输文件，并根据文件扩展名设置内容类型响应 HTTP 头字段。
**语法:**

```js
res.sendFile(path [, options] [, fn])
```

**参数:**path 参数描述路径，options 参数包含 maxAge、root 等各种属性，fn 为回调函数。
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
var path = require('path');
var PORT = 3000;

// Without middleware
app.get('/', function(req, res){
    var options = {
        root: path.join(__dirname)
    };

    var fileName = 'Hello.txt';
    res.sendFile(fileName, options, function (err) {
        if (err) {
            next(err);
        } else {
            console.log('Sent:', fileName);
        }
    });
});

app.listen(PORT, function(err){
    if (err) console.log(err);
    console.log("Server listening on PORT", PORT);
});
```

现在，创建一个. txt 文件，就像我们在项目根目录下创建的 **Hello.txt** 一样，包含以下文本:

```js
Greetings from GeeksforGeeks
```

**运行程序的步骤:**

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

*   现在打开浏览器，转到 *http://localhost:3000/* ，现在检查你的控制台，你会看到如下输出:

```js
Server listening on PORT 3000
Sent: Hello.txt
```

*   在屏幕上，您将看到以下输出:

```js
Greetings from GeeksforGeeks
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

    var options = {
        root: path.join(__dirname)
    };

    var fileName = 'GeeksforGeeks.txt';
    res.sendFile(fileName, options, function (err) {
        if (err) {
            next(err);
        } else {
            console.log('Sent:', fileName);
            next();
        }
    });
});

app.get('/', function(req, res){
    console.log("File Sent")
    res.send();
});

app.listen(PORT, function(err){
    if (err) console.log(err);
    console.log("Server listening on PORT", PORT);
});
```

请确保您创建了一个. txt 文件，就像我们在项目根目录下用以下文本创建的 **GeeksforGeeks.txt** :

```js
Welcome from GeeksforGeeks
```

使用以下命令运行 index.js 文件:

```js
node index.js
```

现在打开浏览器，转到 *http://localhost:3000/* ，现在检查你的控制台，你会看到如下输出:

```js
Server listening on PORT 3000
Sent: GeeksforGeeks.txt
File Sent
```

您将在浏览器屏幕上看到以下输出:

```js
Welcome from GeeksforGeeks
```

**参考:**[https://expressjs . com/en/5x/API . html # RES . sendfile](https://expressjs.com/en/5x/api.html#res.sendFile)