# Node.js Http2ServerRequest 关闭事件

> 原文:[https://www . geesforgeks . org/node-js-http2 server request-close-event/](https://www.geeksforgeeks.org/node-js-http2serverrequest-close-event/)

当底层 Http2Stream 关闭时，会发出 http2 服务器中的**“关闭”**事件。

**语法:**

```js
Event: 'close'

```

**参数**:此事件不接受任何参数作为参数。

**返回值**:这个事件只返回一个回调函数。

**如何生成私钥和公钥证书？**

**1。文件名:私钥**

打开记事本，复制粘贴以下密钥，将文件保存为 ***私钥. PEM***T0】

**2。文件名:公共证书**

打开记事本，复制粘贴以下密钥，将文件保存为 ***公共证书***T0】

**示例 1:** **文件名:index . js**

## Javascript

```js
// Node.js program to demonstrate the
// Http2ServerRequest close event method

const http2 = require('http2');
const fs = require('fs');

// Private key and public certificate for access
const options = {
  key: fs.readFileSync('private-key.pem'),
  cert: fs.readFileSync('public-cert.pem'),
};

// Creating and initializing server
// by using http2.createServer() method
const server = http2.createServer(options);

server.on('stream', (stream, requestHeaders) => {

  // Creating and initializing the http2 server request
  const request = new http2.Http2ServerRequest(stream)

  // Emitting close event
  request.on('close' , () => {
    console.log("request is closed")
  })

  // Setting additional header 
  // by using additionalHeaders() method
  stream.additionalHeaders({ ':status': 100, 'content-type': 
  'text/plain' });

  stream.end("the end");

  // Closing the stream event
  stream.close();

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
':path': '/' });

// Emitting header event
req.on('headers', (headers, flags) => {
  console.log(headers);
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

```js
node index.js
```

**输出:**

```js
request is closed
[Object: null prototype] {
  ':status': 100,
  'content-type': 'text/plain'
}
Received: the end
client destroyed
server destroyed

```

**示例 2:** **文件名:index . js**

## Javascript

```js
// Node.js program to demonstrate the
// Http2ServerRequest close event method

const http2 = require('http2');
const fs = require('fs');

// Private key and public certificate for access
const options = {
  key: fs.readFileSync('private-key.pem'),
  cert: fs.readFileSync('public-cert.pem'),
};

// Creating and initializing server
// by using http2.createServer() method
const server = http2.createServer(options);

server.on('stream', (stream, requestHeaders) => {

  // Creating and initializing the http2 server request
  const request = new http2.Http2ServerRequest(stream)

  // Emitting close event
  request.on('close' , ()=>{
    console.log("request is closed")
  })

  // Setting additional header 
  // by using additionalHeaders() method
  stream.additionalHeaders({ 
    ':status': 100, 
    'content-type': 'text/plain' 
  });

  // Getting rst stream code
  // by using sentInfoHeaders method
  const status = stream.sentInfoHeaders;

  console.log(status)

  // Closing the stream event
  stream.close();

  // Stopping the server
  // by using the close() method
  server.close(() => {
    console.log("server destroyed");
  })
});

server.listen(8000);

// Creating and initializing client
// by using tls.connect() method
const client = http2.connect(
    'http://localhost:8000');

const req = client.request({ 
  ':method': 'GET', ':path': '/' });

// Emitting header event
req.on('headers', (headers, flags) => {
  console.log(headers);
  client.close();
});
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
[
  [Object: null prototype] {    
    ':status': 100,
    'content-type': 'text/plain'
  }
]
request is closed
[Object: null prototype] {
  ':status': 100,
  'content-type': 'text/plain'
}
server destroyed

```

**参考**:[https://nodejs . org/dist/latest-v 12 . x/docs/API/https 2 . html # https 2 _ event _ close _ 2](https://nodejs.org/dist/latest-v12.x/docs/api/http2.html#http2_event_close_2)