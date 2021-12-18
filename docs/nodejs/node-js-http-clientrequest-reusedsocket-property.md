# Node.js http。ClientRequest.reusedSocket 属性

> 原文:[https://www . geesforgeks . org/node-js-http-client request-reusedsocket-property/](https://www.geeksforgeeks.org/node-js-http-clientrequest-reusedsocket-property/)

**http。ClientRequest.reusedSocket** 是 HTTP 模块内 ClientRequest 类的内置应用编程接口，用于检查请求是否通过可重用的套接字发送。

**语法:**

```
const request.reusedSocket
```

**参数:**该属性不接受任何参数作为参数。

**返回值:**该属性返回客户端请求主机的对象。

**示例 1: Filename-index.js**

## java 描述语言

```
// Node.js program to demonstrate the  
// request.reusedSocket method

// Importing http module
const http = require('http');

// Create an HTTP server
const server = http.createServer((req, res) => {
  res.writeHead(200, { 'Content-Type': 'text/plain' });
  res.end('okay');
});

// Now that server is running
server.listen(3000, '127.0.0.1', () => {

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

  req.host = '127.0.0.1'

  // Checking if the message has been
  // sent through reusedSocket or not
  // by using host method
  const v = req.reusedSocket;

  // Display the result
  if (v)
    console.log("message is sent through reusedSocket")
  else
    console.log("message is not sent through reusedSocket")

  process.exit(0)
});
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
message is not sent through reusedSocket
```

**示例 2:Filename-index . js**

## Javascript

```
// Node.js program to demonstrate the  
// request.reusedSocket method

// Importing http module
const http = require('http');

// Create an HTTP server
http.createServer((req, res) => { })
  .listen(3000, '127.0.0.1', () => {

  // Getting client request
  const req = http.request({
    port: 3000,
    host: '127.0.0.1',
  });

  // Checking if the message has been
  // sent through reusedSocket or not
  // by using host method
  if (req.reusedSocket)
    console.log("message is sent through reusedSocket")
  else
    console.log("message is not sent through reusedSocket")

  process.exit(0)
});
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
message is not sent through reusedSocket
```

**参考**:[https://nodejs . org/dist/latest-v 12 . x/docs/API/http . html # http _ request _ reusedssocket](https://nodejs.org/dist/latest-v12.x/docs/api/http.html#http_request_reusedsocket)