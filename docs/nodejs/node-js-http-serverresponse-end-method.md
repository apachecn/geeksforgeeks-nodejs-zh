# Node.js http。ServerResponse.end()方法

> 原文:[https://www . geesforgeks . org/node-js-http-server response-end-method/](https://www.geeksforgeeks.org/node-js-http-serverresponse-end-method/)

**httpserverrresponse . end()**是 [http](https://www.geeksforgeeks.org/node-js-http-module/#:~:text=The%20HTTP%20module%20creates%20an,with%20the%20help%20of%20http.) 模块内的类 ServerResponse 的内置应用编程接口，用于向服务器发送所有头都已发送的信号。

**语法:**

```js
response.end(data, Encodingtype, Callbackfunction)
```

**参数**:该方法取三个参数

*   **Data** : the data block to be sent.
*   **Code Type** : Data Type [Code](https://www.geeksforgeeks.org/understanding-character-encoding/)
*   **Callback** : Callback function, and further operation if necessary.

**返回值**:这个方法返回这个服务器响应对象。

**示例 1:文件名:index.js**

## java 描述语言

```js
// Node.js program to demonstrate the  
// response.end() method

// Importing http module 
var http = require('http'); 

// Setting up PORT 
const PORT = process.env.PORT || 3000; 

// Creating http Server 
var httpServer = http.createServer(
  function(request, response){ 

  // Getting connection by using
  // response.connection method
  const value = response.connection;

  // Ending the response
  response.end( "port address : " + 
  value.address().port, 'utf8', () => { 
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
port address : 3000
```

**示例 2:Filename:index . js**

## Javascript

```js
// Node.js program to demonstrate the  
// response.end() method

// Importing http module 
var http = require('http'); 

// Request and response handler 
const http2Handlers = (request, response) => { 

  // Getting connection 
  // by using response.connection Api
  const value = response.connection;

  // Display result by using end()
  // api and ending the response
  response.end( "family  : " + 
  value.address().family, 'utf8', () => { 
      console.log("displaying the result..."); 

      httpServer.close(()=>{
          console.log("server is closed")
      })
  });
  }; 

// Creating http Server  and listening
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

**浏览器输出:**

*   **Paste the localhost address http://localhost:3000/. In the search bar of the browser.**

```js
family  : IPv6
```

**参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/http . html # http _ response _ end _ data _ encoding _ callback](https://nodejs.org/dist/latest-v12.x/docs/api/http.html#http_response_end_data_encoding_callback)