# Node.js http。ClientRequest.setHeader()方法

> 原文:[https://www . geesforgeks . org/node-js-http-client request-set header-method/](https://www.geeksforgeeks.org/node-js-http-clientrequest-setheader-method/)

**http。ClientRequest.setHeader()** 是 HTTP 模块内 ClientRequest 类的内置应用编程接口，用于设置头的对象。

**语法:**

```js
const request.setHeader(name, value)
```

**参数:**该方法以特定报头的名称和值作为参数作为键值对。

**返回值:**这个方法没有什么可返回的。

**示例 1: Filename-index.js**

## java 描述语言

```js
// Node.js program to demonstrate the  
// request.setHeader() method

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

  req.setHeader('content-type', 'text/html');

  console.log("before operation :- " 
    + req.getHeader('content-type'))

  // Removing header by using
  // removeHeader() method
  req.removeHeader('content-type')

  console.log("after operation :- " 
  + req.getHeader('content-type'))

  process.exit(0)
});
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
before operation :- text/html
after operation :- undefined
```

**示例 2:Filename-index . js**

## Javascript

```js
// Node.js program to demonstrate the  
// request.setHeader() method

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

  req.setHeader('Cookie', ['type=ninja',
            'language=javascript']);

  console.log("before operation :- " 
  + req.getHeader('Cookie'))

  // Removing header by using
  // removeHeader() method
  req.removeHeader('Cookie')

  console.log("after operation :- " 
  + req.getHeader('Cookie'))

  process.exit(0)
});
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
before operation :- type=ninja,language=javascript
after operation :- undefined
```

**参考**:[https://nodejs . org/dist/latest-v 12 . x/docs/API/http . html # http _ request _ set header _ name _ value](https://nodejs.org/dist/latest-v12.x/docs/api/http.html#http_request_setheader_name_value)