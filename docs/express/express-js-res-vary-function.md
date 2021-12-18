# Express.js res.vary()函数

> 原文:[https://www.geeksforgeeks.org/express-js-res-vary-function/](https://www.geeksforgeeks.org/express-js-res-vary-function/)

**res.vary()** 功能用于将字段添加到 vary 响应标题中，如果该字段还不存在的话。可变头指示它基本上用于内容协商的头。
**语法:**

```js
res.vary( field )
```

**参数:**字段参数描述字段的名称。
**返回值:**返回一个对象。
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
    res.vary('User-Agent').send(
    "Field added to the Vary response header");
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

2.  现在打开浏览器，进入 *http://localhost:3000/* ，现在在你的屏幕上你会看到如下输出:

```js
Field added to the Vary response header
```

**示例 2:** **文件名:index.js**

## java 描述语言

```js
var express = require('express');
var app = express();
var PORT = 3000;

// With middleware
app.use('/', function(req, res, next){
    res.vary('User-Agent').send(
    "Field added to the Vary response header");

    next();
})

app.get('/', function(req, res){
    console.log('Modified');
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

现在打开一个浏览器，转到 *http://localhost:3000/* ，现在在你的屏幕上你会在你的浏览器屏幕上看到以下输出:

```js
Field added to the Vary response header
```

您将在控制台上看到以下输出:

```js
Server listening on PORT 3000
Modified
```

**参考:**T2 官方文件