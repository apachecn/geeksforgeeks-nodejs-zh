# Express.js res.jsonp()功能

> 原文:[https://www . geesforgeks . org/express-js-RES-jsonp-function/](https://www.geeksforgeeks.org/express-js-res-jsonp-function/)

**res.jsonp()** 函数用于发送一个支持 jsonp 的 JSON 响应，这个函数类似于 res.json()函数，只是它选择了-in 来支持 JSONP 回调。

**语法:**

```
res.jsonp( [body] )
```

**参数:**body 参数描述可以响应发送的 body 类型。
**返回值:**返回一个对象。

**快递模块安装:**

1.您可以访问[安装快速模块](https://www.npmjs.com/package/express)的链接。您可以使用此命令安装此软件包。

```
npm install express
```

2.安装快速模块后，您可以使用命令在命令提示符下检查您的快速版本。

```
npm version express
```

3.之后，您可以创建一个文件夹并添加一个文件，例如 index.js。

```
node index.js
```

**示例 1:** **文件名:index.js**

## java 描述语言

```
var express = require('express');
var app = express();
var PORT = 3000;

// Without middleware
app.get('/', function(req, res){
    res.jsonp({ title: 'GeeksforGeeks' });
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

```
npm install express
```

3.使用以下命令运行 index.js 文件:

```
node index.js
```

**输出:**

```
Server listening on PORT 3000
```

4.现在打开浏览器，进入 *http://localhost:3000/* ，现在在你的屏幕上你会看到如下输出:

```
{"title":"GeeksforGeeks"}
```

**示例 2:** **文件名:index.js**

## java 描述语言

```
var express = require('express');
var app = express();
var PORT = 3000;

// With middleware
app.use('/', function(req, res, next) {
    res.jsonp({ name: 'Legend' });
    next();
})

app.get('/', function(req, res) {
    res.send();
});

app.listen(PORT, function(err) {
    if (err) console.log(err);
    console.log("Server listening on PORT", PORT);
});
```

使用以下命令运行 index.js 文件:

```
node index.js
```

现在打开浏览器，转到 *http://localhost:3000/* ，现在检查你的浏览器屏幕，你会看到如下输出:

```
{"name":"Legend"}
```

**参考资料:**[https://expressjs . com/en/5x/API . html # RES . jsonp](https://expressjs.com/en/5x/api.html#res.jsonp)