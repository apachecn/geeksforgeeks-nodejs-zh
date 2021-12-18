# Express.js res.json()功能

> 原文:[https://www.geeksforgeeks.org/express-js-res-json-function/](https://www.geeksforgeeks.org/express-js-res-json-function/)

**res.json()** 函数发送 json 响应。此方法发送响应(具有正确的内容类型)，该响应是使用 JSON.stringify()方法转换为 JSON 字符串的参数。
**语法:**

```
res.json( [body] )
```

**参数:**正文参数是响应中要发送的正文。
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
    res.json({ user: 'geek' });
});

app.listen(PORT, function(err){
    if (err) console.log(err);
    console.log("Server listening on PORT", PORT);
});
```

**运行程序的步骤:**

1.项目结构会是这样的:

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
{"user":"geek"}
```

**示例 2:** **文件名:index.js**

## java 描述语言

```
var express = require('express');
var app = express();
var PORT = 3000;

// With middleware
app.use('/', function(req, res, next){
    res.json({title: "GeeksforGeeks"})
    next();
})

app.get('/', function(req, res){
     console.log("User Page")
     res.end();
});

app.listen(PORT, function(err){
    if (err) console.log(err);
    console.log("Server listening on PORT", PORT);
});
```

使用以下命令运行 index.js 文件:

```
node index.js
```

现在打开一个浏览器，进入 *http://localhost:3000/* ，现在在你的屏幕上你会看到如下输出:

```
{"title":"GeeksforGeeks"}
```

您将在控制台上看到以下输出:

```
User Page
```

**参考资料:**[https://expressjs . com/en/4x/API . html # RES . JSON](https://expressjs.com/en/4x/api.html#res.json)