# Node.js http。ClientRequest.socket 属性

> 原文:[https://www . geesforgeks . org/node-js-http-client request-socket-property/](https://www.geeksforgeeks.org/node-js-http-clientrequest-socket-property/)

**http。ClientRequest.socket** 是 http 模块内 ClientRequest 类的一个内置应用编程接口，用来获取一个代理对象，充当*网。插座*。

**语法:**

```js
request.socket
```

**参数**:该属性不接受任何参数作为参数。

**返回值**:该属性返回一个代理对象，作为 net.Socket。

**示例 1:文件名:index.js**

## java 描述语言

```js
// Node.js program to demonstrate the  
// request.socket property

// Importing http module 
var http = require('http'); 

// Setting up PORT 
const PORT = process.env.PORT || 3000; 

// Creating http Server 
var httpServer = http.createServer(
  function(request, response) { 

  // Getting proxy socket 
  // by using request.socket
  const value = request.socket;

  // Display result
  response.end( value.remoteFamily, 'utf8', () => { 
    console.log("Writing remotefamily of socket..."); 

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
IPv6
```

现在关闭浏览器，您将在终端屏幕上看到以下输出:

```js
Server is running at port 3000...
Writing remotefamily of socket...
server is closed
```

**示例 2:Filename:index . js**

## Javascript

```js
// Node.js program to demonstrate the  
// request.socket property

// Importing http module 
var http = require('http'); 

// Request and response handler 
const http2Handlers = (request, response) => { 

  // Getting proxy socket 
  // by using request.socket method
  const value = request.socket;

  // Display result
  response.end( value.remoteFamily, 'utf8', () => { 
    console.log("Writing remotefamily of socket..."); 

    httpServer.close(() => {
        console.log("server is closed")
    })
  });
}; 

// Creating http Server 
var httpServer = http.createServer
  (http2Handlers).listen(3000, () => { 
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
IPv6
```

现在关闭浏览器，您将在终端屏幕上看到以下输出:

```js
Server is running at port 3000...
Writing remotefamily of socket...
server is closed
```

**参考**:[https://nodejs . org/dist/latest-v 12 . x/docs/API/http . html # http _ request _ socket](https://nodejs.org/dist/latest-v12.x/docs/api/http.html#http_request_socket)