# node . js 中的不同服务器

> 原文:[https://www.geeksforgeeks.org/different-servers-in-node-js/](https://www.geeksforgeeks.org/different-servers-in-node-js/)

Node.js 是一个开源的跨平台运行时环境，用于在浏览器之外执行 JavaScript 代码。你需要记住 NodeJS 不是一个框架，也不是一种编程语言。大多数人都很困惑，明白这是一个框架或者一种编程语言。我们经常使用 Node.js 来构建后端服务，比如像 Web App 或者移动 App 这样的 API。
创建服务器甚至节点的方法有很多，js 有自己内置的服务器‘http’。下面提到其中一些:
**1。使用“*****【http】*****”模块创建服务器:**

**导入** ***http*** **模块:**导入 *http* 模块，并将返回的 http 实例存储到变量中。

**语法:**

```js
var http = require("http");
```

**创建和绑定服务器:**使用 *createServer()* 方法创建一个服务器实例，并使用 *listen()* 方法将其绑定到某个端口。

**语法:**

```js
const server = http.createServer().listen(port) 
```

**参数:**这个方法(listen())接受一个参数，如上所述，如下所述:

*   **端口<** *编号***T7:**端口在 1024 到 65535 之间，包含注册端口和动态端口。

下面的例子说明了 Node.js 中 *http* 模块的使用

**示例:** **文件名:index.js**

## java 描述语言

```js
// Node.js program to create
// http server

// Using require to access http module
const http = require("http");

// Port number
const PORT = process.env.PORT || 2020;

// Creating server
const server = http.createServer(
   // Server listening on port 2020
   function (req, res) {
      res.write('Hello geeksforgeeks!');
      // Write a response to the client
      res.end();
   }
)
.listen(PORT, error => {
  // Prints in console
  console.log(`Server listening on port ${PORT}`)
});
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

> 服务器监听端口 2020

现在在网页浏览器中输入***http://127 . 0 . 0 . 1:2020/***或***http://localhost:2020***查看输出。

**2。使用“******模块创建服务器:****

****注意:**为了创建一个 *HTTPS* 服务器，我们需要 **SSL 密钥和证书**，以及内置的 *https* Node.js 模块。**

****导入 https 模块:**导入 *https* 模块，并将返回的 HTTP 实例存储到变量中。**

****语法:****

```js
var https = require("https");
```

****创建和绑定服务器:**使用 createServer()方法创建一个服务器实例，并使用 listen()方法将其绑定到某个端口。**

****语法:****

```js
const server = https.createServer(options, 
            onResponseCallback).listen(port) 
```

****参数:**该方法接受三个参数，如上所述，如下所述:**

*   ****选项** < *钥匙、证件* > **:包括钥匙、证件通过。****
*   ****on responsecallback**<*Callback*>:是响应 createServer 调用的回调函数。**
*   ****端口** < *编号* > **:** 端口在 1024 到 65535 之间，包含注册端口和动态端口。**

**下面的例子说明了 Node.js 中 *https* 模块的使用**

****示例:** **文件名:index.js****

## **java 描述语言**

```js
// Node.js program to create
// https server

// Using require to access https module
var https = require('https');
var fs = require('fs');
const port= 8000;

var options = {

  // Note: We require SSL and certificate
  // to create https servers 
  key: fs.readFileSync('key.pem'),
  cert: fs.readFileSync('cert.pem')
};

https.createServer(options, function (req, res) {

  // Returns the status
  res.writeHead(200);
  res.end("Hello GeeksforGeeks");
}).listen(port);
```