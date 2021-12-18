# node . js http . server . listing 属性

> 原文:[https://www . geesforgeks . org/node-js-http-server-listening-property/](https://www.geeksforgeeks.org/node-js-http-server-listening-property/)

**http . server . listing**是 http 模块内类 Server 的内置应用编程接口，用于检查服务器是否在监听连接。

**语法:**

```
const server.listening
```

**参数:**不接受任何参数作为参数。

**返回值:**不返回值。

**示例 1:** **文件名:index.js**

## java 描述语言

```
// Node.js program to demonstrate the  
// server.listening APi

// Importing http module 
var http = require('http'); 

// Setting up PORT 
const PORT = process.env.PORT || 3000; 

// Creating http Server 
var httpServer = http.createServer(
  function(request, response){ 

  // getting the reference of the 
  // underlying socket object
  // by using socket API
  const value = response.socket;

  // display result
  // by using end() api
  response.end( "socket buffersize : " 
  + value.bufferSize, 'utf8', () => { 
      console.log("displaying the result..."); 

      // closing server 
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

// checking if the server is listening or not
if(httpServer.listening)
console.log("server is listening")
else
console.log("server is not listening")
```

**输出:**

**输出:控制台内**

```
server is listening
Server is running at port 3000...
displaying the result...
displaying the result...
server is closed
server is closed
```

**现在在浏览器中运行 http://localhost:3000/即可。**

**输出:浏览器内**

```
socket buffersize : 0
```

**示例 2:** **文件名:index . js**

## Javascript

```
// Node.js program to demonstrate the  
// server.listening APi

// Importing http module 
var http = require('http'); 

// Request and response handler 
const http2Handlers = (request, response) => { 

  // getting the reference of the
  // underlying socket object
  // by using socket API
  const value = response.socket;

  // display result
  // by using end() api
  response.end( "socket local address : " 
  + value.localAddress, 'utf8', () => { 
      console.log("displaying the result..."); 

      // closing server 
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

// checking if the server is listening or not
if(httpServer.listening)
console.log("server is listening")
else
console.log("server is not listening")
```

**输出:**

**输出:控制台内**

```
server is listening
Server is running at port 3000...
displaying the result...
displaying the result...
server is closed
server is closed
```

**现在在浏览器中运行 http://localhost:3000/即可。**

**输出:浏览器内**

```
socket local address : ::1
```

**参考**:[https://nodejs . org/dist/latest-v 12 . x/docs/API/http . html # http _ server _ listing](https://nodejs.org/dist/latest-v12.x/docs/api/http.html#http_server_listening)