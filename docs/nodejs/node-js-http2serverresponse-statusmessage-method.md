# node . js htp2server response . statusmessage 方法

> 原文:[https://www . geesforgeks . org/node-js-http2 server response-status message-method/](https://www.geeksforgeeks.org/node-js-http2serverresponse-statusmessage-method/)

**http2 server response . statusmessage**是 HTTP 2 模块内 Http2ServerResponse 类的内置应用程序编程接口，用于返回空字符串，因为它不受 HTTP/2 (RFC 7540 8.1.2.4)的支持。

**语法:**

```
response.statusMessage
```

**参数**:此方法不接受任何参数作为参数。

**返回值**:这个方法返回一个空字符串。

**如何生成私钥和公钥证书？**

**1。文件名:私钥**

打开记事本，复制粘贴以下密钥，将文件保存为 ***私钥. PEM***T0】

**2。文件名:公共证书**

打开记事本，复制粘贴以下密钥，将文件保存为 ***公共证书***T0】

**示例 1:Filename:index . js**

## Javascript

```
// Node.js program to demonstrate the
// Http2ServerResponse.statusMessage method
const http2 = require('http2');
const fs = require('fs');

// Private key and public certificate for access
const options = {
    key: fs.readFileSync('private-key.pem'),
    cert: fs.readFileSync('public-cert.pem'),
};

// Request and response handler
const http2Handlers = (request, response) => {

    // Getting status code
    // using response.statusMessage method
    const value = response.statusMessage;

    // Display the display
    console.log("status message : " + value)
};

// Creating and initializing server
// by using http2.createServer() method
const server = http2.createServer(options, http2Handlers);

server.on('stream', (stream, requestheader) => {
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

req.on('data', (data) => {
    console.log('Received: %s ',
    data.toString().replace(/(\n)/gm, ""));
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
status message :
(node:656) UnsupportedWarning: Status message is 
not supported by HTTP/2 (RFC7540 8.1.2.4)
Received: hello
Received: priority weight : 16
client destroyed
server destroyed
```

**示例 2:Filename:index . js**

## Javascript

```
// Node.js program to demonstrate the
// Http2ServerResponse.statusMessage method
const http2 = require('http2');
const fs = require('fs');
const { RSA_NO_PADDING } = require('constants');

// Private key and public certificate for access
const options = {
    key: fs.readFileSync('private-key.pem'),
    cert: fs.readFileSync('public-cert.pem'),
};

// Request and response handler
const http2Handlers = (request, response) => {

    // Getting status code
    // using response.statusMessage method
    const value = response.statusMessage;

    // Display the display
    response.end("status message : " + value)
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

const req = client.request({ ':method': 'GET', 
':path': '/www.geeksforgeeks.org' });

req.on('data', (data) => {
    console.log('Received: %s ',
    data.toString().replace(/(\n)/gm, ""));
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
(node:8360) UnsupportedWarning: Status message is not supported 
by HTTP/2 (RFC7540 8.1.2.4)
Received: status message :
client destroyed
server destroyed
```

**参考**:[https://nodejs . org/dist/latest-v 12 . x/docs/API/https 2 . html # https 2 _ response _ statusmessage](https://nodejs.org/dist/latest-v12.x/docs/api/http2.html#http2_response_statusmessage)