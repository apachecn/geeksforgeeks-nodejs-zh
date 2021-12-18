# Node.js http。ClientRequest.end() API

> 原文:[https://www . geesforgeks . org/node-js-http-client request-end-API/](https://www.geeksforgeeks.org/node-js-http-clientrequest-end-api/)

**http。ClientRequest.end()** 是 http 模块内 ClientRequest 类的内置应用编程接口，用于完成请求的发送。如果身体的任何部位没有被切除。

**语法:**

```
const request.end([data[, encoding]][, callback])
```

**参数:**该方法以数据为输入。

**返回值**:这个方法只返回一个回调函数。

**例 1:**

## java 描述语言

```
// Node.js program to demonstrate the 
// request.end() APi

// Importing http module
const http = require('http');

// Create an HTTP server
http.createServer((req, res) => {}).listen(3000, '127.0.0.1', () => {

  // getting client request
  const req = http.request({
    port: 3000,
    host: '127.0.0.1',
  });

  req.setHeader('content-type', 'text/html');

  // finishing sending the request
  req.end()

  // getting header
  // by using getHeader() api
  console.log("header :- " + req.getHeader('content-type'))

  process.exit(0)
});
```

**输出:**

![](img/0dc8ffd410f0fa23d2c5d5c558a7b417.png)

**例 2:**

## java 描述语言

```
// Node.js program to demonstrate the 
// request.end() APi

// Importing http module
const http = require('http');

// Create an HTTP server
const server = http.createServer((req, res) => {
  res.writeHead(200, { 'Content-Type': 'text/plain' });
  res.end('okay');
});

// Now that server is running
server.listen(3000, '127.0.0.1', () => {

  // make a request
  const options = {
    port: 3000,
    host: '127.0.0.1',
    headers: {
      'Connection': 'Upgrade',
      'Upgrade': 'websocket'
    }
  };

  // getting client request
  const req = http.request(options);

  req.setHeader('Cookie', ['type=ninja', 'language=javascript']);

  // getting header
  // by using getHeader() api
  const v = req.getHeader('Cookie');

  // finishing sending the request
  req.end()

  // display the result
  console.log("header :- " + v)

  process.exit(0)
});
```

**输出:**

![](img/4353b2e6f91a41cc0d5bad82899a2441.png)

**参考**:[https://nodejs . org/dist/latest-v 12 . x/docs/API/http . html # http _ request _ end _ data _ encoding _ callback](https://nodejs.org/dist/latest-v12.x/docs/api/http.html#http_request_end_data_encoding_callback)