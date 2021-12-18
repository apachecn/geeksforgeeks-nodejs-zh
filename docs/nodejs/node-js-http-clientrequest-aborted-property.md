# Node.js http。ClientRequest .中止属性

> 原文:[https://www . geesforgeks . org/node-js-http-client request-aborted-property/](https://www.geeksforgeeks.org/node-js-http-clientrequest-aborted-property/)

**http。ClientRequest.aborted** 是 [http](https://www.geeksforgeeks.org/node-js-http-module/) 模块中类 ClientRequest 的内置应用编程接口，用于检查客户端请求是否已被中止。

**语法:**

```
request.aborted
```

**参数:**不接受任何参数作为参数。

**返回值:**不返回值。

**示例 1:文件名:index.js**

## java 描述语言

```
// Node.js program to demonstrate the  
// request.aborted APi

// Importing http module
const http = require('http');

// Create an HTTP server
const server = http.createServer((req, res) => {
  res.writeHead(200, { 'Content-Type': 'text/plain' });
  res.end('okay');
});

// Now that server is running
server.listen(3000, '127.0.0.1', () => {

console.log("Server is Started")
  // Make a request
  const options = {
    port: 3000,
    host: '127.0.0.1',
    headers: {
      'Connection': 'Upgrade',
      'Upgrade': 'websocket'
    }
  };

  // Getting client request
  const req = http.request(options);

  // Aborting the request
  // by using abort() api
  req.abort()

  // checking if the client request
  // has been aborted or not
  // by using aborted api
  if(req.aborted)
    console.log("client request has been aborted")
  else
    console.log("client request has not been aborted")
});
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**控制台输出:**

```
client request has been aborted
```

**示例 2:Filename:index . js**

## Javascript

```
// Node.js program to demonstrate the  
// request.aborted APi

// Importing http module
const http = require('http');

// Creating an HTTP server
http.createServer((req, res) => {})
.listen(3000, '127.0.0.1', () => {

  // Getting client request
  const req = http.request({
    port: 3000,
    host: '127.0.0.1',
  });

  // Checking if the client request
  // has been aborted or not
  // by using aborted api
  if(req.aborted)
    console.log("client request has been aborted")
  else
    console.log("client request has not been aborted")

  process.exit(0)
});
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**控制台输出:**

```
client request has not been aborted
```

**参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/http . html # http _ request _ 中止](https://nodejs.org/dist/latest-v12.x/docs/api/http.html#http_request_aborted)