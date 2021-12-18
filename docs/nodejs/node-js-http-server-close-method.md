# Node.js http.server.close()方法

> 原文:[https://www . geesforgeks . org/node-js-http-server-close-method/](https://www.geeksforgeeks.org/node-js-http-server-close-method/)

**http.server.close()** 是 http 模块内类 server 的内置应用编程接口，用于阻止服务器接受新的连接。

**语法:**

```js
const server.close([callback])
```

**参数:**这个方法只接受一个可选的回调函数参数作为参数。

**返回值:**这个方法只返回一个回调函数。

**示例 1: Filename-index.js**

## java 描述语言

```js
// Node.js program to demonstrate the  
// server.close() method

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

    // Display result by using end() method
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
server is closed
```

现在在浏览器中运行 **http://localhost:3000/** ，你会在屏幕上看到如下输出:

```js
socket buffersize : 0
```

**示例 2:Filename-index . js**

## Javascript

```js
// Node.js program to demonstrate the  
// server.close() method

// Importing http module 
var http = require('http');

// Request and response handler 
const http2Handlers = (request, response) => {

    // Getting the reference of the
    // underlying socket object
    // by using socket method
    const value = response.socket;

    // Display result by using end() method
    response.end("socket local address : " 
        + value.localAddress, 'utf8', () => {
            console.log("displaying the result...");

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
server is closed
```

现在在浏览器中运行 **http://localhost:3000/** ，你会在屏幕上看到如下输出:

```js
socket local address : ::1
```

**参考**:[https://nodejs . org/dist/latest-v 12 . x/docs/API/http . html # http _ server _ close _ callback](https://nodejs.org/dist/latest-v12.x/docs/api/http.html#http_server_close_callback)