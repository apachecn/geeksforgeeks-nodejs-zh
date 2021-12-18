# Node.js http。ServerResponse.setTimeout()方法

> 原文:[https://www . geesforgeks . org/node-js-http-server response-settimeout-method/](https://www.geeksforgeeks.org/node-js-http-serverresponse-settimeout-method/)

**HTTP servereresponse . settimeout**是 HTTP 模块中类 ServerResponse 的内置应用编程接口，用于将套接字的超时值设置为*毫秒(毫秒)*。

**语法:**

```js
const response.setTimeout(msecs[, callback])
```

**参数:**该方法以毫秒为单位取第一个参数为套接字超时值，第二个参数为回调函数，可选。

**返回值:**这个方法只返回一个回调函数做进一步操作。

**示例 1: Filename-index.js**

## java 描述语言

```js
// Node.js program to demonstrate the  
// response.setTimeout() method

// Importing http module 
var http = require('http'); 

// Setting up PORT 
const PORT = process.env.PORT || 3000; 

// Creating http Server 
var httpServer = http.createServer(
  function(request, response) { 

  // Setting the socket time out value
  // by using setTimeout method
  response.setTimeout(6000,() => {
    console.log("socket is destroyed due to timeout")
  })
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
socket is destroyed due to timeout
```

现在打开浏览器，转到***http://localhost:3000/***，会看到如下输出:

```js
ERR_CONNECTION_REFUSED
```

**示例 2:Filename-index . js**

## Javascript

```js
// Node.js program to demonstrate the  
// response.setTimeout() Method

// Importing http module 
var http = require('http'); 

// Request and response handler 
const httpHandlers = (request, response) => { 

  // Setting the socket time out value
  // by using setTimeout method
  response.setTimeout(5000,() => {
    console.log("socket is destroyed due to timeout")
  })
} 

// Creating http Server 
var httpServer = http.createServer(
    httpHandlers).listen(3000, () => { 
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
socket is destroyed due to timeout
```

现在打开浏览器，转到***http://localhost:3000/***，会看到如下输出:

```js
ERR_CONNECTION_REFUSED
```

**参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/http . html # http _ response _ settimeout _ msecs _ callback](https://nodejs.org/dist/latest-v12.x/docs/api/http.html#http_response_settimeout_msecs_callback)