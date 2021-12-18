# Node.js http。ClientRequest.path 属性

> 原文:[https://www . geesforgeks . org/node-js-http-client request-path-property/](https://www.geeksforgeeks.org/node-js-http-clientrequest-path-property/)

**http。ClientRequest.path** 是 http 模块内 ClientRequest 类的内置应用编程接口，用于获取特定客户端请求的请求路径。

**语法:**

```js
request.path
```

**参数**:该属性不接受任何参数作为参数。

**返回值**:该属性返回特定客户端请求的请求路径。

**示例 1:文件名:index.js**

## java 描述语言

```js
// Node.js program to demonstrate the  
// request.path property

// Importing http module 
var http = require('http'); 

// Setting up PORT 
const PORT = process.env.PORT || 3000; 

// Creating http Server 
var httpServer = http.createServer(
  function(request, response) { 

  // Getting request path
  // by using request.path
  const value = request.path;
  console.log("Request URL: ", request.url)

  // Display result
  response.end( "request path : " + value, 'utf8', () => { 
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

```js
node index.js
```

**输出:**

```js
Server is running at port 3000...
```

现在打开浏览器，转到 **http://localhost:3000/** 、**T4，你会在屏幕上看到如下输出:**

```js
request path : undefined
```

现在关闭浏览器，您将在终端屏幕上看到以下输出:

```js
Server is running at port 3000...
Request URL:  /
displaying the result...
Request URL:  /favicon.ico
displaying the result...
```

**示例 2:Filename:index . js**

## Javascript

```js
// Node.js program to demonstrate the  
// request.path property

// Importing http module 
var http = require('http'); 

// Request and response handler 
const http2Handlers = (request, response) => { 

    // Getting request path
    // by using request.path
    const value = request.path;

    // display result
    response.end( "request path : " + value, 'utf8', () => { 
        console.log("displaying the result...");

        httpServer.close(() => {
            console.log("server is closed")
        })
    });
}; 

// Creating http Server 
var httpServer = http.createServer(http2Handlers)
  .listen(3000, () => { 
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
```

现在打开浏览器，转到 **http://localhost:3000/** 、**T4，你会在屏幕上看到如下输出:**

```js
request path : undefined
```

现在关闭浏览器，您将在终端屏幕上看到以下输出:

```js
Server is running at port 3000...
displaying the result...
server is closed
```

**参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/http . html # http _ request _ path](https://nodejs.org/dist/latest-v12.x/docs/api/http.html#http_request_path)