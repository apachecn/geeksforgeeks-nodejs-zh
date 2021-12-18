# Node.js http。引入消息.拖车方法

> 原文:[https://www . geesforgeks . org/node-js-http-incoming message-trainers-method/](https://www.geeksforgeeks.org/node-js-http-incomingmessage-trailers-method/)

**http。传入消息.预告片**是 [http](https://www.geeksforgeeks.org/node-js-http-module/#:~:text=The%20HTTP%20module%20creates%20an,createServer()%20method.) 模块内类传入消息的内置应用编程接口，用于获取请求/响应[预告片](https://www.geeksforgeeks.org/http-headers-trailer/)对象。

**语法:**

```
request.trailers or response.trailers
```

**参数**:该方法不接受任何参数作为参数。

**返回值**:该方法返回请求或响应拖车对象。

**示例 1:文件名:index.js**

## java 描述语言

```
// Node.js program to demonstrate the  
// request.trailers APi

// Importing http module 
var http = require('http'); 

// Setting up PORT 
const PORT = process.env.PORT || 3000; 

// Creating http Server 
var httpServer = http.createServer(
  function(request, response){ 

  // Getting trailers 
  // by using request.trailers Api
  const value = request.trailers;

  // Display the request trailers
  console.log(value)

  // Display the result
  response.end(  "hello world", 'utf8', () => { 
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

```
node index.js
```

**控制台输出:**

```
Server is running at port 3000...
{}
displaying the result...
{}
displaying the result...
server is closed
server is closed
```

**浏览器输出:**粘贴 localhost 地址 http://localhost:3000/。在浏览器的搜索栏中。
T3】

**示例 2:文件名:index.js**

## java 描述语言

```
// Node.js program to demonstrate the  
// request.trailers APi

// Importing http module 
var http = require('http'); 

// Request and response handler 
const http2Handlers = (request, response) => { 

  // Getting trailers 
  // by using request.trailers Api
  const value = request.trailers;

  // Display the request trailer
  console.log(value)

  // Display result
  response.end( "GeeksForGeeks", 'utf8', () => { 
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

```
node index.js
```

**控制台输出:**

```
Server is running at port 3000...
{}
displaying the result...
{}
displaying the result...
server is closed
server is closedserver is closed
```

**浏览器输出:**粘贴 localhost 地址 http://localhost:3000/。在浏览器的搜索栏中。

```
GeeksForGeeks
```

**参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/http . html # http _ message _ traines](https://nodejs.org/dist/latest-v12.x/docs/api/http.html#http_message_trailers)