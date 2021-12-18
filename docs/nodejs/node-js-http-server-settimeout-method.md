# node . js http . server . settimeout()方法

> 原文:[https://www . geesforgeks . org/node-js-http-server-settimeout-method/](https://www.geeksforgeeks.org/node-js-http-server-settimeout-method/)

**http.server.setTimeout()** 是 [HTTP](https://www.geeksforgeeks.org/node-js-http-module/#:~:text=The%20HTTP%20module%20creates%20an,with%20the%20help%20of%20http.) 模块中类 server 的内置应用编程接口，用于设置套接字的超时值。

**语法:**

```js
server.setTimeout([msecs][, callback])
```

**参数**:该方法以毫秒为单位取套接字超时值。

**返回值**:这个方法只返回一个回调函数做进一步操作。

**示例 1:文件名:index.js**

## java 描述语言

```js
// Node.js program to demonstrate the  
// server.setTimeout() APi

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
  }); 
}); 

// Listening to http Server 
// by using listen() api
httpServer.listen(PORT, () => { 
    console.log(
    "Server is running at port 3000..."); 
});

httpServer.setTimeout(3000,()=>{

  console.log(
    "Socket is destroyed due to timeout")

    // Closing server 
    // by using close() api
    httpServer.close(()=>{
        console.log("Server is closed")
    })
})
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**控制台输出:**

```js
Server is running at port 3000...
Displaying the result...
Displaying the result...
Socket is destroyed due to timeout
Socket is destroyed due to timeout
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
// server.setTimeout() APi

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
  });
  }; 

// Listening to http Server 
// by using listen() api
var httpServer = http.createServer(
    http2Handlers).listen(3000, () => { 
    console.log("Server is running at port 3000..."); 
}); 

httpServer.setTimeout(3000,()=>{
    console.log(
    "Socket is destroyed due to timeout")

      // Closing server 
      // by using close() api
      httpServer.close(()=>{
          console.log("Server is closed")
      })
    })
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**控制台输出:**

```js
Server is running at port 3000...
Displaying the result...
Displaying the result...
Socket is destroyed due to timeout
Socket is destroyed due to timeout
Server is closed
Server is closed
```

**浏览器输出:**在浏览器的搜索栏中粘贴 localhost 地址 http://localhost:3000/即可。

```js
socket local address : ::1
```

**参考**:[https://nodejs . org/dist/latest-v 12 . x/docs/API/http . html # http _ server _ settimeout _ msecs _ callback](https://nodejs.org/dist/latest-v12.x/docs/api/http.html#http_server_settimeout_msecs_callback)