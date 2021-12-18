# Express.js | app.listen()功能

> 原文:[https://www . geesforgeks . org/express-js-app-listen-function/](https://www.geeksforgeeks.org/express-js-app-listen-function/)

**app.listen()功能**用于绑定和监听指定主机和端口上的连接。这个方法和 Node 的 http 是一样的。Server.listen()方法。
如果端口号被省略或为 0，操作系统将分配一个任意未使用的端口，这对于自动化任务(测试等)非常有用。).
express()返回的 app 实际上是一个 JavaScript 函数，旨在作为回调传递给 Node 的 HTTP 服务器来处理请求。这使得为应用程序的 HTTP 和 HTTPS 版本提供相同的代码库变得很容易，因为应用程序并不继承这些代码库(它只是一个回调)。

## java 描述语言

```js
var express = require('express')
var https = require('https')
var http = require('http')
var app = express()

http.createServer(app).listen(80)
https.createServer(options, app).listen(443)
```

**语法:**

```js
app.listen([port[, host[, backlog]]][, callback])
```

语法解释:

1.  (可选)它指定我们希望应用程序监听的端口。
2.  (可选)它指定我们希望应用程序侦听的主机的 IP 地址。只有当您已经指定了端口时，才可以指定主机。(因为您在([，host[，backlog]]后面有一个右(']')括号，正如您在上面的语法中看到的，所以这意味着在指定 host 和 backlog 之前必须指定 port)。
3.  (可选)它指定挂起连接的最大队列长度。只有当您已经指定了端口和主机时，才可以指定积压。(因为您在([，backlog]之后有一个右括号，所以这意味着您必须在指定 backlog 之前指定 host)
4.  (可选)它指定了一个函数，一旦您的应用程序开始监听指定的端口，该函数就会被执行。您可以单独指定回调，即不指定端口、主机和积压。(由于这是一组单独的参数，位于左方括号和右方括号([，callback])中，这意味着您可以指定这些参数，而无需指定前面左方括号和右方括号中的参数。

**快递模块安装:**

*   您可以访问[安装快速模块](https://www.npmjs.com/package/express)的链接。您可以使用此命令安装此软件包。

```js
npm install express
```

*   安装 express 模块后，您可以使用命令在命令提示符下检查您的 express 版本。

```js
npm version express
```

*   之后，您可以创建一个文件夹并添加一个文件，例如 index.js。

```js
node index.js
```

**文件名:index.js**

## java 描述语言

```js
var express = require('express');
var app = express();
var PORT = 3000;

app.listen(PORT, function(err){
    if (err) console.log("Error in server setup")
    console.log("Server listening on Port", PORT);
})
```

**运行程序的步骤:**

*   项目结构如下所示:

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
Server listening on Port 3000
```

这就是如何使用 express **app.listen()** 函数绑定并监听指定主机和端口上的连接。