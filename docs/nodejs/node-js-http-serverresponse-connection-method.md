# Node.js http。服务器响应.连接方法

> 原文:[https://www . geesforgeks . org/node-js-http-server response-connection-method/](https://www.geeksforgeeks.org/node-js-http-serverresponse-connection-method/)

**http ServerResponse . connection**是 [http](https://www.geeksforgeeks.org/node-js-http-module/) 模块内类 Server Response 的内置应用编程接口，用于获取该 HTTP 连接的响应[套接字](https://www.geeksforgeeks.org/introduction-to-sockets-io-in-node/)。

**语法:**

```
response.connection
```

**参数:**此方法不接受任何参数作为参数。

**返回值:**这个方法返回这个 HTTP 连接的响应套接字。

**示例 1:文件名:index.js**

## java 描述语言

```
// Node.js program to demonstrate the  
// response.connection APi

// Importing http module 
var http = require('http'); 

// Setting up PORT 
const PORT = process.env.PORT || 3000; 

// Creating http Server 
var httpServer = http.createServer(
  function(request, response){ 

  // Getting connection 
  // by using response.connection Api
  const value = response.connection;

  // Display result
  response.end( "port address : " 
  + value.address().port, 'utf8', () => { 
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

**执行命令:**

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

**浏览器输出:**在浏览器的搜索栏中粘贴 localhost 地址 http://localhost:3000/即可。
T3】

**示例 2:文件名:index.js**

## java 描述语言

```
// Node.js program to demonstrate the  
// response.connection APi

// Importing http module 
var http = require('http'); 

// Request and response handler 
const http2Handlers = (request, response) => { 

  // Getting connection 
  // by using response.connection Api
  const value = response.connection;

  // Display result
  response.end( "family  : " 
  + value.address().family, 'utf8', () => { 
      console.log("displaying the result..."); 

      // Closing the server
      httpServer.close(()=>{
          console.log("server is closed")
      })
  });
}; 

// Creating http Server and listing
// on the port 3000
var httpServer = http.createServer(
    http2Handlers).listen(3000, () => { 
    console.log("Server is running at port 3000..."); 
});
```

**执行命令:**

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

**浏览器输出:**在浏览器的搜索栏中粘贴 localhost 地址 http://localhost:3000/即可。
T3】

**参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/http . html # http _ response _ connection](https://nodejs.org/dist/latest-v12.x/docs/api/http.html#http_response_connection)