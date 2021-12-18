# node . js http 2 server request . socket 方法

> 原文:[https://www . geesforgeks . org/node-js-http2 server request-socket-method/](https://www.geeksforgeeks.org/node-js-http2serverrequest-socket-method/)

**http2 ServerRequest . socket**是 Http 2 模块中 Http2ServerRequest 类的内置应用程序编程接口，用于获取一个充当网络的 Proxy 对象。套接字(或 tls。TLSSocket)。

**语法:**

```
const request.socket

```

**参数**:该方法不接受任何参数作为参数。

**返回值**:这个方法返回一个代理对象，作为一个网。套接字(或 tls。TLSSocket)。

**如何生成私钥和公钥证书？**

**1。文件名:私钥**

打开记事本，复制粘贴以下密钥，将文件保存为 ***私钥. PEM***T0】

**2。文件名:公共证书**

打开记事本，复制粘贴以下密钥，将文件保存为 ***公共证书***T0】

**示例 1:** **文件名:index . js**

## Javascript

```
// Node.js program to demonstrate the
// Http2ServerRequest.socket method

const http2 = require('http2');
const fs = require('fs');

// Private key and public certificate for access
const options = {
  key: fs.readFileSync('private-key.pem'),
  cert: fs.readFileSync('public-cert.pem'),
};

// Request and response handler
const http2Handlers = (request, response) => {

  // Getting socket of http2 
  // by using request.socket method
  const auth = request.socket;
  console.log( "socket address port :- " 
    + auth.address().port)
};

// Creating and initializing server
// by using http2.createServer() method
const server = http2.createServer(options, http2Handlers);

server.on('stream', (stream, requestheader) => {
  stream.respond({ ':status': 200, 'content-type':
  'text/plain' });
  stream.write('hello ');

  // Getting all information of this http2stream object
  // by using state method
  const status = stream.state;

  stream.end("priority weight : " + status.weight);

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

const req = client.request({ 
  ':method': 'GET', ':path': '/'});

req.on('response', (responsesocket) => {  
  console.log("status : " 
  + responsesocket[":status"]);
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
socket address port :- 8000
status : 200
Received: hello
Received: priority weight : 16
client destroyed
server destroyed

```

**示例 2:** **文件名:index . js**

## Javascript

```
// Node.js program to demonstrate the
// Http2ServerRequest.socket method

const http2 = require('http2');
const fs = require('fs');

// Private key and public certificate for access
const options = {
  key: fs.readFileSync('private-key.pem'),
  cert: fs.readFileSync('public-cert.pem'),
};

// Request and response handler
const http2Handlers = (request, response) => {

  // Getting socket of http2 
  // by using request.socket method
  const auth = request.socket;
  response.end( "socket address family :- " 
    + auth.address().family)
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

const req = client.request({ 
  ':method': 'GET', ':path': '/' });

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
Received: socket address family :- IPv6
client destroyed
server destroyed

```

**参考**:[https://nodejs . org/dist/latest-v 12 . x/docs/API/https 2 . html # https 2 _ request _ socket](https://nodejs.org/dist/latest-v12.x/docs/api/http2.html#http2_request_socket)