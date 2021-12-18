# Node.js http。输入消息.完成方法

> 原文:[https://www . geesforgeks . org/node-js-http-incoming message-complete-method/](https://www.geeksforgeeks.org/node-js-http-incomingmessage-complete-method/)

**http。IncomingMessage.complete** 是 http 模块内类 IncomingMessage 的内置应用编程接口，用于检查是否收到完整的 HTTP 消息并成功解析。

**语法:**

```js
const message.complete
```

**参数:**此方法不接受任何参数作为参数。

**返回值:**当且仅当收到完整的 HTTP 消息并成功解析时，此方法返回 true。

**示例 1:** **文件名:index.js**

## java 描述语言

```js
// Node.js program to demonstrate the  
// request.complete Method 

// Importing http module 
var http = require('http'); 

// Setting up PORT 
const PORT = process.env.PORT || 3000; 

// Creating http Server 
var httpServer = http.createServer(
  function(request, response){ 

  // Checking if message is parsed or not
  // by using request.complete Api
  const value = request.complete;

  // Display result
  response.end( "message has been sent : " 
      + value, 'utf8', () => { 
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

**输出:**

**输出:**控制台内

```js
Server is running at port 3000...
displaying the result...
displaying the result...
server is closed
server is closed
```

**现在在浏览器中运行 http://localhost:3000/即可。**

```js
message has been sent : false
```

**示例 2:** **文件名:index . js**

## Javascript

```js
// Node.js program to demonstrate the  
// request.complete Method 

// Importing http module 
var http = require('http'); 

// Request and response handler 
const http2Handlers = (request, response) => { 

  // Checking if message is parsed or not
  // by using request.complete Api
  const value = request.complete;

  // Display result
  response.end( "message has been sent : " 
      + value, 'utf8', () => { 
      console.log("displaying the result..."); 

      httpServer.close(()=>{
          console.log("server is closed")
      })
  });
  }; 

// Creating http Server 
var httpServer = http.createServer(
    http2Handlers).listen(3000, () => { 
    console.log("Server is running at port 3000..."); 
});
```

**输出:**

**输出**:控制台内

```js
Server is running at port 3000...
displaying the result...
displaying the result...
server is closed
server is closed
```

**现在在浏览器中运行 http://localhost:3000/即可。**

```js
message has been sent : false
```

**参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/http . html # http _ message _ complete](https://nodejs.org/dist/latest-v12.x/docs/api/http.html#http_message_complete)