# Express.js | app.get()请求功能

> 原文:[https://www . geesforgeks . org/express-js-app-get-request-function/](https://www.geeksforgeeks.org/express-js-app-get-request-function/)

**app.get()** 函数将 HTTP GET 请求路由到由指定回调函数指定的路径。基本上是为了将中间件绑定到您的应用程序。
**语法:**

```js
app.get( path, callback )
```

**参数:**

1.  **路径:**是调用中间件函数的路径。

2.  **回调:**它们可以是中间件函数，也可以是中间件函数的系列/数组。

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

app.get('/', (req, res) => {
  res.send("GET Request Called")
})

app.listen(PORT, function(err){
    if (err) console.log(err);
    console.log("Server listening on PORT", PORT);
});
```