# 在 Node.js

中使用 EJS 作为模板引擎

> 原文:[https://www . geesforgeks . org/use-ejs-as-template-engine-in-node-js/](https://www.geeksforgeeks.org/use-ejs-as-template-engine-in-node-js/)

**EJS:** EJS 或 Embedded Javascript Templating 是 Node.js 使用的一个模板引擎，模板引擎帮助用最少的代码创建一个 HTML 模板。此外，它可以在客户端将数据注入到 HTML 模板中，并生成最终的 HTML。EJS 是一种简单的模板语言，用于生成带有普通 JavaScript 的 HTML 标记。它还有助于将 JavaScript 嵌入到 HTML 页面中。首先，使用 EJS 作为模板引擎，我们需要使用给定的命令安装 EJS:

```js
npm install ejs --save
```

**注意:**以上命令中的 npm 代表节点包管理器，一个安装所有依赖项的地方。–在 Node 5.0.0 版本之后，不再需要保存标志，因为我们现在安装的所有模块都将被添加到依赖项中。
现在，我们需要做的第一件事是用 Express 将 EJS 设置为我们的模板引擎，这是一个 Node.js web 应用服务器框架，专门为构建单页、多页和混合 web 应用程序而设计。它已经成为 node.js 的标准服务器框架。

## java 描述语言

```js
// Set express as Node.js web application
// server framework.
// To install express before using it as
// an application server by using
// "npm install express" command.
var express = require('express');
var app = express();

// Set EJS as templating engine
app.set('view engine', 'ejs');
```

EJS 的默认行为是在“视图”文件夹中查找要渲染的模板。因此，让我们在我们的主节点项目文件夹中创建一个“视图”文件夹，并创建一个名为“home.ejs”的文件，该文件将在我们的节点项目中满足一些期望的请求。本页面内容为:

## 超文本标记语言

```js
<!DOCTYPE html>
<html>

<head>
    <title>Home Page</title>

    <style type="text/css" media="screen">
        body {
            background-color: skyblue;
            text-decoration-color: white;
            font-size:7em;
        }
    </style>
</head>

<body>
    <center>This is our home page.</center>
</body>

</html>   
```