# Node.js http。服务器发起方。套接字 Api

> 哎哎哎:# t0]https://www . geeksforgeeks . org/node-js-http 服务器发起方套接字 api/

**httpServerResponse . socket**是 [http](https://www.geeksforgeeks.org/node-js-http-module/#:~:text=The%20HTTP%20module%20creates%20an,with%20the%20help%20of%20http.) 模块中类 serverrresponse 的内置应用编程接口，用于获取底层 socket 对象的引用。

**语法:**

```
response.socket
```

**参数**:此方法不接受任何参数作为参数。

**返回值**:这个方法返回底层套接字对象的引用。

**示例 1:文件名:index.js**

## java 描述语言

```
// Node.js program to demonstrate the  
// response.socket APi

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

  // display result
  // by using end() api
  response.end( "socket buffersize : " 
      + value.bufferSize, 'utf8', () => { 
      console.log("displaying the result..."); 

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

```
node index.js
```

**控制台输出:**

```
Server is running at port 3000...
displaying the result...
displaying the result...
server is closed
server is closed
```

**浏览器输出:**

*   **Paste the localhost address http://localhost:3000/. In the search bar of the browser.**

```
socket buffersize : 0
```

**示例 2:Filename:index . js**

## Javascript

```
// Node.js program to demonstrate the  
// response.socket APi

// Importing http module 
var http = require('http'); 

// Request and response handler 
const http2Handlers = (request, response) => { 

  // Getting the reference of the underlying socket object
  // by using socket API
  const value = response.socket;

  // Display result
  // by using end() api
  response.end( "Socket local address : " 
      + value.localAddress, 'utf8', () => { 
      console.log("displaying the result..."); 

      // Closing the server
      httpServer.close(()=>{
          console.log("server is closed")
      })
  });
  }; 

// Creating http Server and listening
// on the given port 
var httpServer = http.createServer(
    http2Handlers).listen(3000, () => { 
    console.log("Server is running at port 3000..."); 
});
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**控制台输出:**

```
Server is running at port 3000...
displaying the result...
displaying the result...
server is closed
server is closed
```

**浏览器输出:**

*   **Paste the localhost address http://localhost:3000/. In the search bar of the browser.**

```
socket local address : ::1
```

**参考**:[https://nodejs . org/dist/latest-v 12 . x/docs/API/http . html # http _ response _ socket](https://nodejs.org/dist/latest-v12.x/docs/api/http.html#http_response_socket)