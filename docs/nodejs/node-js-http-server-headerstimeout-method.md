# node . js http . server . header time out 方法

> 原文:[https://www . geesforgeks . org/node-js-http-server-header timeout-method/](https://www.geeksforgeeks.org/node-js-http-server-headerstimeout-method/)

**http . server . header time out**是 HTTP 模块内类 Server 的内置应用编程接口，用于获取解析器接收完整 HTTP 头的等待时间。

**语法:**

```js
server.headersTimeout
```

**参数**:此方法不接受任何参数作为参数。

**返回值**:这个方法返回时间，解析器会等待接收完整的 HTTP 头。

**示例 1: Filename-index.js**

## java 描述语言

```js
// Node.js program to demonstrate the  
// server.headersTimeout method

// Importing http module 
var http = require('http');

// Setting up PORT 
const PORT = process.env.PORT || 3000;

// Creating http Server 
var httpServer = http.createServer(
    function (request, response) {

    // Display result by using end() method
    response.end("hello world", 'utf8', () => {
        console.log("displaying the result...");

        const value = httpServer.headersTimeout;
        console.log("header time out value : " + value)

        // Closing server by using close() method
        httpServer.close(() => {
            console.log("server is closed")
        })
    });
});

// Listening to http Server 
httpServer.listen(PORT, () => {
    console.log("Server is running at port 3000...");
});
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
Server is running at port 3000...
displaying the result...
header time out value : 60000
server is closed
```

现在在浏览器中运行 **http://localhost:3000/** ，你会在屏幕上看到如下输出:

```js
hello world
```

**示例 2:Filename-index . js**

## Javascript

```js
// Node.js program to demonstrate the  
// server.headersTimeout method

// Importing http module 
var http = require('http');

// Request and response handler 
const http2Handlers = (request, response) => {

    // Display result
    // by using end() method
    response.end("hello world", 'utf8', () => {
        console.log("displaying the result...");

        const value = httpServer.headersTimeout;
        console.log("header time out value : " + value)

        // Closing server 
        // by using close() method
        httpServer.close(() => {
            console.log("server is closed")
        })
    });
};

// Creating http Server 
var httpServer = http.createServer(
    http2Handlers).listen(3000, () => {
    console.log("Server is running at port 3000...");
});
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
Server is running at port 3000...
displaying the result...
header time out value : 60000
server is closed
```

现在在浏览器中运行 **http://localhost:3000/** ，你会在屏幕上看到如下输出:

```js
hello world
```

**参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/http . html # http _ server _ header time out](https://nodejs.org/dist/latest-v12.x/docs/api/http.html#http_server_headerstimeout)