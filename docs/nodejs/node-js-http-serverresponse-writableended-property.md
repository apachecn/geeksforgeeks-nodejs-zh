# Node.js http。服务器响应.可写结束属性

> 原文:[https://www . geesforgeks . org/node-js-http-server response-writableend-property/](https://www.geeksforgeeks.org/node-js-http-serverresponse-writableended-property/)

**http 模块内的**类服务器响应的内置应用编程接口，用于检查是否调用了 response.end()。

**语法:**

```js
response.writableEnded
```

**参数:**此方法不接受任何参数。

**返回值:**当且仅当 response.end()被调用时，该方法返回 true，否则返回 false。

**示例 1:文件名:index.js**

## java 描述语言

```js
// Node.js program to demonstrate the  
// response.writableEnded APi

// Importing http module 
var http = require('http'); 

// Setting up PORT 
const PORT = process.env.PORT || 3000; 

// Creating http Server 
var httpServer = http.createServer(
  function(request, response){ 

  // Checking if the response.end has 
  // been called or not by using 
  // writableEnded API
  const value = response.writableEnded;

  // Display result
  // by using end() api
  response.end( "response.end() has been called : "
      + value, 'utf8', () => { 
      console.log("displaying the result..."); 

      // Closing the server
      httpServer.close(()=>{
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

**控制台输出:**

```js
Server is running at port 3000...
displaying the result...
displaying the result...
server is closed
server is closed
```

**浏览器输出:**粘贴本地主机地址 http://localhost:3000/。在浏览器的搜索栏中。

**输出:**

```js
response.end() has been called : false
```

**示例 2:Filename:index . js**

## Javascript

```js
// Node.js program to demonstrate the  
// response.writableEnded APi

// Importing http module 
var http = require('http'); 

// Request and response handler 
const http2Handlers = (request, response) => { 

  // Checking if the response.end has
  // been called or not by using 
  // writableEnded API
  const value = response.writableEnded;

  if(value)
    response.write(
"<h1>Response.end() has been called<h1>")
  else
    response.write(
"<h1>Response.end() has been not called<h1>")

  // Ending the response
  response.end()
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

**控制台输出:**

```js
Server is running at port 3000...
```

**浏览器输出:**粘贴 localhost 地址 http://localhost:3000/。在浏览器的搜索栏中。

**输出:**

```js
Response.end() has been not called
```

**参考**:[https://nodejs . org/dist/latest-v 12 . x/docs/API/http . html # http _ response _ writableended](https://nodejs.org/dist/latest-v12.x/docs/api/http.html#http_response_writableended)