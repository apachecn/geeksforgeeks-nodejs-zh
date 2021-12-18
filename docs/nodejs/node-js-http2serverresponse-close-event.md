# Node.js Http2ServerResponse 关闭事件

> 原文:[https://www . geesforgeks . org/node-js-http2 server response-close-event/](https://www.geeksforgeeks.org/node-js-http2serverresponse-close-event/)

当底层 Http2Stream 关闭时，会发出 http2 服务器中的**“关闭”**事件。

**语法:**

```
Event: 'close'

```

**参数**:此事件不接受任何参数作为参数。

**返回值**:这个事件只返回一个回调函数。

**如何生成私钥和公钥证书？**

**1。文件名:私钥**

打开记事本，复制粘贴以下密钥，将文件保存为 ***私钥. PEM***T0】

**2。文件名:公共证书**

打开记事本，复制粘贴以下密钥，将文件保存为 ***公共证书***T0】

**示例 1:Filename:index . js**

## Javascript

```
// Node.js program to demonstrate the
// Http2ServerResponse 'close' event 

const http2 = require('http2');
const fs = require('fs');

// Private key and public certificate for access
const options = {
  key: fs.readFileSync('private-key.pem'),
  cert: fs.readFileSync('public-cert.pem'),
};

// Request and response handler
const http2Handlers = (request, response) => {

  // Emitting close event
  response.on('close', () => {
    console.log("stream is closed")
  })
};

// Creating and initializing server
// by using http2.createServer() method
const server = http2.createServer(options, http2Handlers);

server.on('stream', (stream, requestheader) => {
  stream.respond({ 
    ':status': 200, 
    'content-type': 'text/plain' 
  });
  stream.write('hello ');

  // Getting all information of this http2stream object
  // by using state method
  const status = stream.state;

  stream.end("priority weight : " + status.weight);

  stream.close()

  // Stopping the server
  // by using the close() method
  server.close(() => {
    console.log("server destroyed");
  })
});

server.listen(8000);

// Creating and initializing client
// by using tls.connect() method
const client = http2.connect('http://localhost:8000');

const req = client.request({ ':method': 'GET', 
':path': '/name'});

req.on('response', (responsesocket) => {
  console.log("status : " + responsesocket[":status"]);
});

req.on('data', (data) => {
  console.log('Received: %s ',
  data.toString().replace(/(\n)/gm,""));
});

req.on('end', () => {
  client.close(() => {
    console.log("client destroyed");
  })
});
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
stream is closed
status : 200
Received: hello
Received: priority weight : 16
client destroyed
server destroyed

```

**示例 2:Filename:index . js**

## Javascript

```
// Node.js program to demonstrate the
// Http2ServerResponse 'close' event

const http2 = require('http2');
const fs = require('fs');

// Private key and public certificate for access
const options = {
  key: fs.readFileSync('private-key.pem'),
  cert: fs.readFileSync('public-cert.pem'),
};

// Request and response handler
const http2Handlers = (request, response) => {

  // Emitting close event
  response.on('close', () => {
    console.log("stream is closed")
  })
};

// Creating and initializing server
// by using http2.createServer() method
const server = http2.createServer(options, http2Handlers);

server.on('stream', (stream, requestHeaders) => {

  // Getting all information of this http2stream object
  // by using state method
  const status = stream.state;

  stream.end("The sum weight of all Http2Stream : " + 
  status.sumDependencyWeight);

  stream.close()

  // Stopping the server
  // by using the close() method
  server.close(() => {
    console.log("server destroyed");
  })
});

server.listen(8000);

// Creating and initializing client
// by using tls.connect() method
const client = http2.connect('http://localhost:8000');

const req = client.request({ ':method': 'GET', 
':path': '/www.geeksforgeeks.org' });

req.on('data', (data) => {
  console.log('Received: %s ',
  data.toString().replace(/(\n)/gm,""));
});

req.on('end', () => {
  client.close(() => {
    console.log("client destroyed");
  })
});
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
stream is closed
Received: The sum weight of all Http2Stream : 0
client destroyed
server destroyed

```

**参考:**T2【https://nodejs . org/dist/latest-v 12 . x/docs/API/https 2 . html # https 2 _ event _ close _ 3