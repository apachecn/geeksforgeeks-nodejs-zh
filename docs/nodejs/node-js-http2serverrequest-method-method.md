# node . js http 2 server request . Method

方法

> 原文:[https://www . geesforgeks . org/node-js-http2 server request-method-method/](https://www.geeksforgeeks.org/node-js-http2serverrequest-method-method/)

**http2 ServerRequest . method**是 Http 2 模块内 Http2ServerRequest 类的内置应用程序编程接口，用于获取请求方法的字符串表示。

**语法:**

```
const request.method

```

**参数**:该方法不接受任何参数作为参数。

**返回值**:该方法返回请求方法的字符串表示形式。

**如何生成私钥和公钥证书？**

**1。文件名:私钥**

打开记事本，复制粘贴以下密钥，将文件保存为 ***私钥. PEM***T0】

**2。文件名:公共证书**

打开记事本，复制粘贴以下密钥，将文件保存为 ***公共证书***T0】

**示例 1:** **文件名:index . js**

## Javascript

```
// Node.js program to demonstrate the
// Http2ServerRequest.method method

const http2 = require('http2');
const fs = require('fs');

// Private key and public certificate for access
const options = {
  key: fs.readFileSync('private-key.pem'),
  cert: fs.readFileSync('public-cert.pem'),
};

// Request and response handler
const http2Handlers = (request, response) => {

  // Getting method of http2 
  // by using request.method method
  const auth = request.method;
  console.log("request method :- " + auth)
};

// Creating and initializing server
// by using http2.createServer() method
const server = http2.createServer(options, http2Handlers);

server.on('stream', (stream, requestmethod) => {
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
  ':method': 'GET', ':path': '/' });

req.on('response', (responsemethod) => {
  console.log("status : " 
  + responsemethod[":status"]);
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
request method :- GET
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
// Http2ServerRequest.method method

const http2 = require('http2');
const fs = require('fs');

// Private key and public certificate for access
const options = {
  key: fs.readFileSync('private-key.pem'),
  cert: fs.readFileSync('public-cert.pem'),
};

// Request and response handler
const http2Handlers = (request, response) => { {

  // Getting method of http2 
  // by using request.method method
  const auth = request.method;
  response.end("request method :- " + auth)
}};

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
Received: request method :- GET
client destroyed
server destroyed

```

**参考**:[https://nodejs . org/dist/latest-v 12 . x/docs/API/https 2 . html # https 2 _ request _ method](https://nodejs.org/dist/latest-v12.x/docs/api/http2.html#http2_request_method)