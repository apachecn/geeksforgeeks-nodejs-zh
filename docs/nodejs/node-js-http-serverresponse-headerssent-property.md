# Node.js http。server response . header sent 属性

> 原文:[https://www . geesforgeks . org/node-js-http-server response-header sent-property/](https://www.geeksforgeeks.org/node-js-http-serverresponse-headerssent-property/)

**HTTP ServerResponse . header sent**是 HTTP 模块内类 servereresponse 的一个内置应用编程接口，用于检查报头是否已经发送。

**语法:**

```
const response.headersSent
```

**参数:**该属性不接受任何参数作为参数。

**返回值:**当且仅当发送了标头时，此属性返回真，否则返回假。

**示例 1: Filename-index.js**

## java 描述语言

```
// Node.js program to demonstrate the  
// response.headersSent() method

// Importing http module 
var http = require('http');

// Setting up PORT 
const PORT = process.env.PORT || 3000;

// Creating http Server 
var httpServer = http.createServer(
    function (request, response) {

    // Checking if response header is sent or not
    // by using headersSent method
    const value = response.headersSent;

    // Display result by using end() method
    response.end("Headers have been sent : "
                   + value, 'utf8', () => {
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

现在打开浏览器，转到***http://localhost:3000/***，会看到如下输出:

```
Headers have been sent : false
```

**示例 2:Filename-index . js**

## Javascript

```
// Node.js program to demonstrate the  
// response.headersSent() method

// Importing http module 
var http = require('http');

// Request and response handler 
const httpHandlers = (request, response) => {

    // Checking if response header is sent or not
    // by using headersSent method
    const value = response.headersSent;

    // Display result by using end() method
    response.end("Headers have been sent : "
                      + value, 'utf8', () => {
        console.log("displaying the result...");

        httpServer.close(() => {
            console.log("server is closed")
        })
    });
};

// Creating http Server 
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

现在打开浏览器，转到***http://localhost:3000/***，会看到如下输出:

```
Headers have been sent : false
```

**参考:**T2【https://nodejs . org/dist/latest-v 12 . x/docs/API/http . html # http _ response _ header sent