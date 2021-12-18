# Node.js http。ServerResponse.writeProcessing()方法

> 原文:[https://www . geesforgeks . org/node-js-http-server response-write processing-method/](https://www.geeksforgeeks.org/node-js-http-serverresponse-writeprocessing-method/)

**HTTP ServerResponse . write Processing()**是 HTTP 模块内类 server response 的内置应用编程接口，用于向客户端发送 HTTP/1.1 102 Processing 消息。

**语法:**

```
response.writeProcessing()
```

**参数:**此方法不接受任何参数作为参数。

**返回值**:这个方法没有什么可返回的。

**示例 1: Filename-index.js**

## java 描述语言

```
// Node.js program to demonstrate the  
// response.writeProcessing() method

// Importing http module 
var http = require('http');

// Setting up PORT 
const PORT = process.env.PORT || 3000;

// Creating http Server 
var httpServer = http.createServer(
    function (request, response) {

    // Sending a HTTP/1.1 102 Processing message
    // by using socket method
    response.writeProcessing();

    // Display result
    // by using end() method
    response.end("HTTP/1.1 102 Processing message"
    + " has been sent", 'utf8', () => {
        console.log("displaying the result...");
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
HTTP/1.1 102 Processing message has been sent
```

**示例 2:Filename-index . js**

## Javascript

```
// Node.js program to demonstrate the  
// response.writeProcessing() method

// Importing http module 
var http = require('http');

// Request and response handler 
const http2Handlers = (request, response) => {

    // Sending a HTTP/1.1 102 Processing message
    // by using socket method
    response.writeProcessing();

    // Display result
    // by using end() method
    response.end("HTTP/1.1 102 Processing message"
    + " has been sent", 'utf8', () => {
            console.log("displaying the result...");

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
HTTP/1.1 102 Processing message has been sent
```

**参考**:[https://nodejs . org/dist/latest-v 12 . x/docs/API/http . html # http _ response _ write processing](https://nodejs.org/dist/latest-v12.x/docs/api/http.html#http_response_writeprocessing)