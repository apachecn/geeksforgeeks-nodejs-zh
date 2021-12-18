# Node.js http.server.listen()方法

> 原文:[https://www . geesforgeks . org/node-js-http-server-listen-method/](https://www.geeksforgeeks.org/node-js-http-server-listen-method/)

**http.server.listen()** 是 http 模块内类 server 的内置应用编程接口，用于启动服务器接受新的连接。

**语法:**

```
const server.listen(options[, callback])
```

**参数:**该方法接受以下两个参数:

*   **Option:** It can be port, host, path, backlog, exclusive, readableAll, writableAll, ipv6Only, etc. according to user's needs.
*   **Callback:** is an optional parameter and a callback function passed as a parameter.

**返回值:**这个方法只返回一个回调函数。

**示例 1: Filename-index.js**

## java 描述语言

```
// Node.js program to demonstrate the  
// server.listen() method

// Importing http module 
var http = require('http');

// Setting up PORT 
const PORT = process.env.PORT || 3000;

// Creating http Server 
var httpServer = http.createServer(
    function (request, response) {

    // Getting the reference of the
    // underlying socket object
    // by using socket method
    const value = response.socket;

    // Display result
    // by using end() method
    response.end("socket buffersize : " 
        + value.bufferSize, 'utf8', () => {
            console.log("displaying the result...");

            // Closing server 
            // by using close() method
            httpServer.close(() => {
                console.log("server is closed")
            })
        });
});

// Listening to http Server 
// by using listen() method
httpServer.listen(PORT, () => {
    console.log("Server is running at port 3000...");
});
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
Server is running at port 3000...
displaying the result...
server is closed
```

现在在浏览器中运行 **http://localhost:3000/** ，你会在屏幕上看到如下输出:

```
socket buffersize : 0
```

**示例 2:Filename-index . js**

## Javascript

```
// Node.js program to demonstrate the  
// server.listen() method

// Importing http module 
var http = require('http');

// Request and response handler 
const httpHandlers = (request, response) => {

    // Getting the reference of the
    // underlying socket object
    // by using socket method
    const value = response.socket;

    // Display result by using end() method
    response.end("socket local address : " 
        + value.localAddress, 'utf8', () => {
            console.log("displaying the result...");

            // Closing server by using close() method
            httpServer.close(() => {
                console.log("server is closed")
            })
        });
};

// Listening to http Server 
// by using listen() method
var httpServer = http.createServer(
    httpHandlers).listen(3000, () => {
    console.log("Server is running at port 3000...");
});
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
Server is running at port 3000...
displaying the result...
server is closed
```

现在在浏览器中运行 **http://localhost:3000/** ，你会在屏幕上看到如下输出:

```
socket local address : ::1
```

**参考**:[https://nodejs . org/dist/latest-v 12 . x/docs/API/http . html # http _ server _ listen](https://nodejs.org/dist/latest-v12.x/docs/api/http.html#http_server_listen)