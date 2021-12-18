# Node.js http。方法

> 原文:[https://www . geesforgeks . org/node-js-http-incoming message-URL-method/](https://www.geeksforgeeks.org/node-js-http-incomingmessage-url-method/)

**http。IncomingMessage.url** 是 [http](https://www.geeksforgeeks.org/node-js-http-module/#:~:text=The%20HTTP%20module%20creates%20an,with%20the%20help%20of%20http.) 模块内的类 IncomingMessage 的内置应用编程接口，用于获取请求 url 字符串，也用于验证特定 URL。

**语法:**

```js
request.url
```

**参数**:该方法不接受任何参数作为参数。

**返回值**:该方法返回客户端实际 HTTP 请求中存在的请求 URL 字符串

**示例 1:文件名:index.js**

## java 描述语言

```js
// Node.js program to demonstrate the  
// request.url APi

// Importing http module 
var http = require('http'); 

// Setting up PORT 
const PORT = process.env.PORT || 3000; 

// Creating http Server 
var httpServer = http.createServer(
  function(request, response){ 

  // Getting url by using request.url Api
  const value = request.url;

  // Display result
  response.end( "URL : " + value, 'utf8', () => { 
      console.log("displaying the result..."); 

  //Closing the server
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

```js
URL : /
```

**示例 2:Filename:index . js**

## Javascript

```js
// Node.js program to demonstrate the  
// request.url APi

// Importing http module 
var http = require('http'); 

// Request and response handler 
const http2Handlers = (request, response) => { 

  // Getting url 
  // by using request.url Api
  const value = request.url;

  // Display result
  response.end( "URL : " + value, 'utf8', () => { 
      console.log("displaying the result..."); 

      //Closing the server
      httpServer.close(()=>{
          console.log("server is closed")
      })
  });
  }; 

// Creating http Server and listening
// on the 3000 port
var httpServer = http.createServer(
    http2Handlers).listen(3000, () => { 
    console.log("Server is running at port 3000..."); 
});
```

**执行命令:**

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

```js
URL : /
```

**参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/http . html # http _ message _ URL](https://nodejs.org/dist/latest-v12.x/docs/api/http.html#http_message_url)