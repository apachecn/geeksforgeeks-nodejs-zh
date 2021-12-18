# node . js http . server . keepalivetimeout 属性

> 原文:[https://www . geesforgeks . org/node-js-http-server-keepalivetimeout-property/](https://www.geeksforgeeks.org/node-js-http-server-keepalivetimeout-property/)

**http . server . keepalivetimeout**是 [http](https://www.geeksforgeeks.org/node-js-http-module/) 模块中类 Server 的内置应用编程接口，用于获取服务器等待额外传入数据所需的不活动毫秒数。

**语法:**

```
server.keepAliveTimeout
```

**参数**:该 Api 不接受任何参数作为参数。

**返回值**:此方法返回服务器等待额外传入数据所需的不活动毫秒数。

**示例 1:文件名:index.js**

## java 描述语言

```
// Node.js program to demonstrate the  
// server.keepAliveTimeout property

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
  response.end( "Socket buffersize : " 
      + value.bufferSize, 'utf8', () => { 
      console.log("displaying the result..."); 

      // Closing server 
      // by using close() api
      httpServer.close(()=>{
          console.log("server is closed")
      })
  }); 
}); 

// Listening to http Server 
// by using listen() api
httpServer.listen(PORT, () => { 
    console.log("Server is running at port 3000..."); 
});

// Getting keep alive timeout value
// by using keepAliveTimeout api
const v = httpServer.keepAliveTimeout

// Display the result
console.log('keep alive time out value :-' + v)
```

使用以下命令运行 **index.js 文件**:

```
node index.js
```

**控制台输出:**

```
keep alive time out value :-5000
Server is running at port 3000...
displaying the result...
displaying the result...
server is closed
server is closed
```

**浏览器输出:**在浏览器的搜索栏中粘贴 localhost 地址 http://localhost:3000/即可。

```
Socket buffersize : 0
```

**示例 2:Filename:index . js**

## Javascript

```
// Node.js program to demonstrate the  
// server.keepAliveTimeout property

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
  response.end( "Socket local address : " 
      + value.localAddress, 'utf8', () => { 
      console.log("displaying the result..."); 

      // Closing server 
      // by using close() api
      httpServer.close(()=>{
          console.log("server is closed")
      })
  });
}; 

// Listening to http Server 
// by using listen() api
var httpServer = http.createServer(
    http2Handlers).listen(3000, () => { 
    console.log("Server is running at port 3000..."); 
}); 

// Getting keep alive timeout value
// by using keepAliveTimeout property
const v = httpServer.keepAliveTimeout

// Display the result
console.log('keep alive time out value :-' + v)
```

使用以下命令运行 **index.js 文件**:

```
node index.js
```

**控制台输出:**

```
keep alive time out value :-5000
Server is running at port 3000...
displaying the result...
displaying the result...
server is closed
server is closed
```

**浏览器输出:**在浏览器的搜索栏中粘贴 localhost 地址 http://localhost:3000/即可。

```
Socket local address : ::1
```

**参考**:[https://nodejs . org/dist/latest-v 12 . x/docs/API/http . html # http _ server _ keepalivetimeout](https://nodejs.org/dist/latest-v12.x/docs/api/http.html#http_server_keepalivetimeout)