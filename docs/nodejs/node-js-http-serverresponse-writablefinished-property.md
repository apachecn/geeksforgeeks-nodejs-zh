# Node.js http。服务器响应.可写成品属性

> 原文:[https://www . geesforgeks . org/node-js-http-server response-writable finished-property/](https://www.geeksforgeeks.org/node-js-http-serverresponse-writablefinished-property/)

**httpServerResponse . writable finished**是 [http](https://www.geeksforgeeks.org/node-js-http-module/#:~:text=The%20HTTP%20module%20creates%20an,with%20the%20help%20of%20http.) 模块中类 serverrresponse 的内置应用编程接口，用于检查是否所有数据都已刷新。

**语法:**

```js
response.writableFinished
```

**参数**:该属性不接受任何参数作为参数。

**返回值**:当且仅当所有数据都已刷新或未刷新时，该属性返回真。

**示例 1:文件名:index.js**

## java 描述语言

```js
// Node.js program to demonstrate the  
// response.writableFinished APi

// Importing http module 
var http = require('http'); 

// Setting up PORT 
const PORT = process.env.PORT || 3000; 

// Creating http Server 
var httpServer = http.createServer(
  function(request, response){ 

  // Checking all the data has been flushed
  // or not by using writableFinished API
  const value = response.writableFinished;

  // Display the result
  // by using end() api
  response.end( "Data has been flushed : "
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

**浏览器输出:**

*   **Paste the localhost address http://localhost:3000/. In the search bar of the browser.**

```js
 Data has been flushed : false
```

**示例 2:Filename:index . js**

## Javascript

```js
// Node.js program to demonstrate the  
// response.writableFinished APi

// Importing http module 
var http = require('http'); 

// Request and response handler 
const http2Handlers = (request, response) => { 

  // checking all the data has been flushed or not
  // by using writableFinished API
  const value = response.writableFinished;

  // display result
  // by using end() api
  response.end( "Data has been flushed : " 
      + value, 'utf8', () => { 
      console.log("displaying the result..."); 

      const value1 = response.writableFinished;
      console.log("Data has been flushed "+value1);
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

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**控制台输出:**

```js
Server is running at port 3000...
displaying the result...
Data has been flushed true
```

**浏览器输出:**

*   **Paste the localhost address http://localhost:3000/. In the search bar of the browser.**

```js
Data has been flushed : false
```

**参考**:[https://nodejs . org/dist/latest-v 12 . x/docs/API/http . html # http _ response _ writable finished](https://nodejs.org/dist/latest-v12.x/docs/api/http.html#http_response_writablefinished)