# Express.js | app.delete()功能

> 原文:[https://www . geesforgeks . org/express-js-app-delete-function/](https://www.geeksforgeeks.org/express-js-app-delete-function/)

**app.delete()** 函数用于将 HTTP DELETE 请求路由到指定为参数的路径，回调函数作为参数传递。
**语法:**

```js
app.delete(path, callback)
```

**参数:**

1.  **路径:**是调用中间件函数的路径。
2.  **回调:**是一个中间件函数或一系列/数组中间件函数。

**快递模块安装:**

1.  您可以访问[安装快速模块](https://www.npmjs.com/package/express)的链接。您可以使用此命令安装此软件包。

```js
npm install express
```

1.  安装 express 模块后，您可以使用命令在命令提示符下检查您的 express 版本。

```js
npm version express
```

1.  之后，您可以创建一个文件夹并添加一个文件，例如 index.js。

```js
node index.js
```

**文件名:index.js**

## java 描述语言

```js
var express = require('express');
var app = express();
var PORT = 3000;

app.delete('/', (req, res) => {
  res.send("DELETE Request Called")
})

app.listen(PORT, function(err){
    if (err) console.log(err);
    console.log("Server listening on PORT", PORT);
});
```