# node . js http 2 server response . header sent 属性

> 原文:[https://www . geesforgeks . org/node-js-http2 server response-header sent-property/](https://www.geeksforgeeks.org/node-js-http2serverresponse-headerssent-property/)

**Http2ServerResponse . header sent**是 http2 模块内的类 http2 server response 的内置应用程序编程接口，用于检查是否发送了标头。

**语法:**

```js
response.headersSent
```

**参数**:该属性不接受任何参数作为参数。

**返回值**:当且仅当发送了报头时，该属性返回真，否则返回假。

**如何生成私钥和公钥证书？**

**1。文件名:私钥**

打开记事本，复制粘贴以下密钥，将文件保存为 ***私钥. PEM***T0】

**2。文件名:公共证书**

打开记事本，复制粘贴以下密钥，将文件保存为 ***公共证书***T0】

**示例 1:Filename:index . js**

## Javascript

```js
// Node.js program to demonstrate the
// Http2ServerResponse.headersSent
const http2 = require('http2');
const fs = require('fs');

// Private key and public certificate for access
const options = {
  key: fs.readFileSync('private-key.pem'),
  cert: fs.readFileSync('public-cert.pem'),
};

// Request and response handler
const http2Handlers = (request, response) => {
    // Setting new header
    response.setHeader(
      'Content-Type', 
      'hello world; charset=utf-8'
    );

    // Checking if the header is sent or not
    // by using headersSent method
    const value = response.headersSent

    // Display the header
    if(value) {
        console.log("header is sent")
    } else {
        console.log("header is not sent")
    }
};

// Creating and initializing server
// by using http2.createServer() method
const server = http2.createServer(options, http2Handlers);

server.on('stream', (stream, requestheader) => {
    stream.write('hello ');

    // Getting all information of this http2stream
    // object by using state method
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

```js
node index.js
```

**输出:**

```js
header is not sent
status : 200
Received: hello
Received: priority weight : 16
client destroyed
server destroyed
```

**示例 2:Filename:index . js**

## Javascript

```js
// Node.js program to demonstrate the
// Http2ServerResponse.headersSent method
const http2 = require('http2');
const fs = require('fs');

// Private key and public certificate for access
const options = {
  key: fs.readFileSync('private-key.pem'),
  cert: fs.readFileSync('public-cert.pem'),
};

// Request and response handler
const http2Handlers = (request, response) => {
    // Setting new header
    response.setHeader('Foo', 'bar');
    response.setHeader(
      'Set-Cookie', ['foo=bar', 'bar=baz']);

    // Sending the header
    response.end("hello");

    // Checking if the header is sent or not
    // by using headersSent method
    const value = response.headersSent

    // Display the header
    if(value) console.log("header is sent")
    else console.log("header is not sent")
};

// Creating and initializing server
// by using http2.createServer() method
const server = http2.createServer(options, http2Handlers);

server.on('stream', (stream, requestHeaders) => {

    // Getting all information of this http2stream
    // object by using state method
    const status = stream.state;

    stream.end("The sum weight of all Http2Stream : "
        + status.sumDependencyWeight);

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

```js
node index.js
```

**输出:**

```js
header is sent
Received: hello
client destroyed
server destroyed
```

**参考**:[https://nodejs . org/dist/latest-v 12 . x/docs/API/https 2 . html # https 2 _ response _ header sent](https://nodejs.org/dist/latest-v12.x/docs/api/http2.html#http2_response_headerssent)