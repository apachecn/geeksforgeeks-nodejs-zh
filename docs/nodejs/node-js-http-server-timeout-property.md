# Node.js http.server.timeout 属性

> 原文:[https://www . geesforgeks . org/node-js-http-server-time out-property/](https://www.geeksforgeeks.org/node-js-http-server-timeout-property/)

**http.server.timeout** 是 [http](https://www.geeksforgeeks.org/node-js-http-module/#:~:text=The%20HTTP%20module%20creates%20an,with%20the%20help%20of%20http.) 模块中类 server 的内置应用编程接口，用于获取默认的 timeout 值(以毫秒为单位)。在 Node.js 中，默认服务器超时对于最新版本为 0 毫秒，对于旧版本为 2 分钟(即 120000 毫秒)。

**语法:**

```js
server.timeout
```

**参数:**不接受任何参数作为参数。

**返回值:**该属性以毫秒为单位返回默认超时值。

**示例 1:文件名:index.js**

## java 描述语言

```js
// Node.js program to demonstrate the  
// server.timeout APi

// Importing http module 
var http = require('http'); 

// Setting up PORT 
const PORT = process.env.PORT || 3000; 

// Creating http Server 
var httpServer = http.createServer(
  function(request, response){ 

  // Getting the reference of the 
  // underlying socket object
  // by using socket API
  const value = response.socket;

  // Display result
  // by using end() api
  response.end( "socket buffersize : " 
      + value.bufferSize, 'utf8', () => { 
      console.log("Displaying the result..."); 

      // Closing server by
      // using close() api
      httpServer.close(()=>{
          console.log("Server is closed")
      })
  }); 
}); 

// Listening to http Server 
// by using listen() api
httpServer.listen(PORT, () => { 
    console.log("Server is running at port 3000..."); 
});

// Getting default timeout value
// by using timeout api
const v = httpServer.timeout

// Display the Timout value
console.log('Default time out value :- ' + v)
```

使用以下命令运行 **index.js 文件**:

```js
node index.js
```

**控制台输出:**

```js
Default time out value :- 0
Server is running at port 3000...
Displaying the result...
Displaying the result...
Server is closed
Server is closed
```

**浏览器输出:**在浏览器的搜索栏中粘贴 localhost 地址 http://localhost:3000/即可。

```js
socket buffersize : 0
```

**示例 2:Filename:index . js**

## Javascript

```js
// Node.js program to demonstrate the  
// server.timeout APi

// Importing http module 
var http = require('http'); 

// Request and response handler 
const http2Handlers = (request, response) => { 

  // Getting the reference of the
  // underlying socket object
  // by using socket API
  const value = response.socket;

  // Display result
  // by using end() api
  response.end( "socket local address : " 
      + value.localAddress, 'utf8', () => { 
      console.log("Displaying the result..."); 

      // Closing server 
      // by using close() api
      httpServer.close(()=>{
          console.log("Server is closed")
      })
  });
  }; 

// Listening to http Server 
// by using listen() api
var httpServer = http.createServer(
    http2Handlers).listen(3000, () => { 
    console.log("Server is running at port 3000..."); 
}); 

// Getting default timeout value
// by using timeout api
const v = httpServer.timeout

// Display the Default time
console.log('Default time out value :- ' + v)
```

使用以下命令运行 **index.js 文件**:

```js
node index.js
```

**控制台输出:**

```js
Default time out value :- 0
Server is running at port 3000...
Displaying the result...
Displaying the result...
Server is closed
Server is closed
```

**浏览器输出:**在浏览器的搜索栏中粘贴 localhost 地址 http://localhost:3000/即可。

```js
socket local address : ::1
```

**参考:**[https://nodejs . org/API/http . html # http _ server _ time out](https://nodejs.org/api/http.html#http_server_timeout)