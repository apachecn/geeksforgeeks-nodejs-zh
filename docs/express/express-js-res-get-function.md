# Express.js res.get()函数

> 原文:[https://www.geeksforgeeks.org/express-js-res-get-function/](https://www.geeksforgeeks.org/express-js-res-get-function/)

he **res.get()** 函数返回字段指定的 HTTP 响应头。匹配不区分大小写。
**语法:**

```js
res.get( field )
```

**参数:**字段参数描述字段的名称。
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

    // Setting the response
    res.set({
        'Content-Type': 'text/plain',
        'Content-Length': '123',
        ETag: '12345'
    });

    // "text/plain"
    console.log(res.get('Content-Type'));
});

app.listen(PORT, function(err){
    if (err) console.log(err);
    console.log("Server listening on PORT", PORT);
});
```

**运行程序的步骤:**

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

*   打开浏览器，转到 *http://localhost:3000/* ，然后在控制台上会看到如下输出:

```js
Server listening on PORT 3000
text/plain; charset=utf-8
```

**示例 2:** **文件名:index.js**

## java 描述语言

```js
var express = require('express');
var app = express();
var PORT = 3000;

// With middleware
app.use('/', function(req, res, next){
    //Setting the response
    res.set({
        'Content-Type': 'text/html',
        'Content-Length': '33',
        ETag: '66'
    });
    next();
})

app.get('/', function(req, res){
    console.log(res.get('Content-Type'));
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

现在打开浏览器，转到 *http://localhost:3000/* ，现在检查你的控制台，你会看到如下输出:

```js
text/html; charset=utf-8
```

**参考:**[https://expressjs . com/en/5x/API . html # RES . get](https://expressjs.com/en/5x/api.html#res.get)