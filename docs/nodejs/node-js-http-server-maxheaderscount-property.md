# node . js http . server . maxheaders count 属性

> 原文:[https://www . geesforgeks . org/node-js-http-server-maxheaderscout-property/](https://www.geeksforgeeks.org/node-js-http-server-maxheaderscount-property/)

**http . Server . MaxHeaderscount**是 HTTP 模块内类服务器的内置应用编程接口，用于获取最大传入头数。

**语法:**

```js
const server.maxHeadersCount
```

**参数:**该属性不接受任何参数作为参数。

**返回值:** TIt 不返回值。

**示例 1: Filename-index.js**

## java 描述语言

```js
// Node.js program to demonstrate the  
// server.maxHeadersCount property

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
// by using listen() method
httpServer.listen(PORT, () => {
    console.log("Server is running at port 3000...");
});

// Getting max header count 
// by using maxHeadersCount method
const v = httpServer.maxHeadersCount

// Display the result
console.log('maximum header count :-' + v)
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
maximum header count :-null
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
// server.maxHeadersCount method

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

// Listening to http Server 
// by using listen() method
var httpServer = http.createServer(
    http2Handlers).listen(3000, () => {
    console.log("Server is running at port 3000...");
});

// Getting max header count 
// by using maxHeadersCount method
const v = httpServer.maxHeadersCount

if (v || v > 1) {
    console.log("maximum header count is greater than 1")
} else {
    console.log("maximum header count is less than 1")
}
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
maximum header count is less than 1
Server is running at port 3000...
displaying the result...
server is closed
```

现在在浏览器中运行 **http://localhost:3000/** ，你会在屏幕上看到如下输出:

```js
socket local address : ::1
```

**参考:**T2【https://nodejs . org/dist/latest-v 12 . x/docs/API/http . html # http _ server _ maxheaders count