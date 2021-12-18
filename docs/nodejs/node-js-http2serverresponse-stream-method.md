# node . js http 2 server response . stream 方法

> 原文:[https://www . geesforgeks . org/node-js-http2 server response-stream-method/](https://www.geeksforgeeks.org/node-js-http2serverresponse-stream-method/)

**http2 server response . stream**是 Http 2 模块中类 Http2ServerResponse 的内置应用编程接口，用于获取支持该响应的 Http 流的对象。

**语法:**

```
response.stream
```

**参数**:此方法不接受任何参数作为参数。

**返回值**:这个方法返回一个支持这个响应的 HTTP 流的对象。

**如何生成私钥和公钥证书？**

**1。文件名:私钥**

打开记事本，复制粘贴以下密钥，将文件保存为 ***私钥. PEM***T0】

**2。文件名:公共证书**

打开记事本，复制粘贴以下密钥，将文件保存为 ***公共证书***T0】

**示例 1:Filename:index . js**

## Javascript

```
// Node.js program to demonstrate the
// Http2ServerResponse.stream method
const http2 = require('http2');
const fs = require('fs');

// Private key and public certificate for access
const options = {
    key: fs.readFileSync('private-key.pem'),
    cert: fs.readFileSync('public-cert.pem'),
};

// Request and response handler
const http2Handlers = (request, response) => {

    // Getting http2 stream reference by 
    // using response.stream method
    const value = response.stream;

    // Display the display
    console.log("id of stream :- " + value.id)
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

const req = client.request({ ':method': 'GET', ':path': '/' });

req.on('response', (responsesocket) => {
    console.log("status : " + responsesocket[":status"]);
});

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
id of stream :- 1
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
// Http2ServerResponse.stream method
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

    // Getting http2 stream reference by 
    // using response.stream method
    const value = response.stream;

    // Display the display
    response.end("id of stream :- " + value.id)
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
Received: id of stream :- 1
client destroyed
server destroyed
```

**参考**:[https://nodejs . org/dist/latest-v 12 . x/docs/API/https 2 . html # https 2 _ response _ stream](https://nodejs.org/dist/latest-v12.x/docs/api/http2.html#http2_response_stream)