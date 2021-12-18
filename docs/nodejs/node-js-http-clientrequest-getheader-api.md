# Node.js http。client request . get header()API

> 哎哎哎:# t0]https://www . geeksforgeeks . org/node-js-http-client request-get header API/

**http。ClientRequest.getHeader()** 是 http 模块内 ClientRequest 类的内置应用编程接口，用于获取特定头名的 Header 对象。

**语法:**

```js
const request.getHeader(name)
```

**参数**:该方法以表头名称为参数。

**返回值**:这个方法返回表头的对象作为输出。

**例 1:**

## java 描述语言

```js
// Node.js program to demonstrate the 
// request.getHeader() APi

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

  // getting header
  // by using getHeader() api
  console.log("header :- " + req.getHeader('content-type'))

  process.exit(0)
});
```

**输出:**

![](img/16052b77271dc0ed1696e34c245c266e.png)

**例 2:**

## java 描述语言

```js
// Node.js program to demonstrate the 
// request.getHeader() APi

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

  // display the result
  console.log("header :- " + v)

  process.exit(0)
});
```

**输出:**

![](img/4c7bc1bbe3b98059865c5d797cfcffd8.png)

**参考**:[https://nodejs . org/dist/latest-v 12 . x/docs/API/http . html # http _ request _ getheader _ name](https://nodejs.org/dist/latest-v12.x/docs/api/http.html#http_request_getheader_name)