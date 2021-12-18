# Node.js http。已完成的应用编程接口

> 原文:[https://www . geesforgeks . org/node-js-http-client request-writable finished-API/](https://www.geeksforgeeks.org/node-js-http-clientrequest-writablefinished-api/)

**http。client request . writable finished**是 http 模块内 **ClientRequest** 类的内置应用编程接口，用于检查所有数据是否已刷新。

**语法:**

```
const request.writableEnded
```

**参数**:该 API 不接受任何参数作为参数。

**返回值**:当且仅当所有的**数据已经被刷新**时，该方法返回**真**。

**例 1:**

## index.js

```
// NodeJS program to demonstrate the  
// request.writableFinished APi

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

  // checking if the all data has been flushed
  // by using writableFinished api
  if(req.writableFinished)
  console.log('all data has been flushed')
  else
  console.log('all data has not been flushed')

  process.exit(0)
});
```

**输出:**

![](img/bb2eea8674ec0a4715a0280dc9b63f27.png)