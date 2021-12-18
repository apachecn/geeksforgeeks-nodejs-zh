# Node.js http。方法应用编程接口

> 原文:[https://www . geesforgeks . org/node-js-http-client request-method-API/](https://www.geeksforgeeks.org/node-js-http-clientrequest-method-api/)

**http。ClientRequest.method** 是 http 模块内 ClientRequest 类的内置应用编程接口，用于获取客户端请求方法的对象。

**语法:**

```
const request.method
```

**参数:**此 **API** 不接受任何参数作为参数。

**返回值**:该方法返回客户端请求方法的对象。

**例 1:**

## index.js

```
// Node.js program to demonstrate the  
// request.method APi

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

  // getting method
  // by using method api
  const v = req.method;

  // display the result
  console.log("method :- " + v)

  process.exit(0)
});
```

**输出:**

![](img/4a645bbb29e5f6663f48ab5dfc939cdf.png)

**参考**:[https://nodejs . org/dist/latest-v 12 . x/docs/API/http . html # http _ request _ method](https://nodejs.org/dist/latest-v12.x/docs/api/http.html#http_request_method)