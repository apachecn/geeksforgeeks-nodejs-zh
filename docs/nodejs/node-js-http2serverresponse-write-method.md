# node . js http 2 server response . write()方法

> 原文:[https://www . geesforgeks . org/node-js-http2 server response-write-method/](https://www.geeksforgeeks.org/node-js-http2serverresponse-write-method/)

**http2 ServerResponse . write()**是 Http 2 模块中 Http2ServerResponse 类的内置应用程序编程接口，用于将响应主体的块发送给客户端。

**语法:**

```
response.write([data[, encoding]][, callback])
```

**参数**:该方法接受以下参数作为参数。

*   **Data** : This is the response header to be sent.
*   **Code** : it is the type of code and an optional parameter.
*   **Callback** : It is a callback function for further operation and an optional parameter.

**返回值**:这个方法没有什么可返回的。

**如何生成私钥和公钥证书？**

**1。文件名:私钥**

打开记事本，复制粘贴以下密钥，将文件保存为 ***私钥. PEM***T0】

**2。文件名:公共证书**

打开记事本，复制粘贴以下密钥，将文件保存为 ***公共证书***T0】

**示例 1:Filename:index . js**

## Javascript

```
// Node.js program to demonstrate the
// Http2ServerResponse.write() method
const http2 = require('http2');
const fs = require('fs');

// Private key and public certificate for access
const options = {
    key: fs.readFileSync('private-key.pem'),
    cert: fs.readFileSync('public-cert.pem'),
};

// Request and response handler
const http2Handlers = (request, response) => {

    // Sending the data to the client
    // by using response.write() method
    response.write("hi")

    // Sending the signal to client
    response.end("hello world")
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
status : 200
Received: hi
Received: hello world
client destroyed
server destroyed
```

**示例 2:Filename:index . js**

## Javascript

```
// Node.js program to demonstrate the
// Http2ServerResponse.write() method
const http2 = require('http2');
const fs = require('fs');

// Private key and public certificate for access
const options = {
    key: fs.readFileSync('private-key.pem'),
    cert: fs.readFileSync('public-cert.pem'),
};

// Request and response handler
const http2Handlers = (request, response) => {

    // Sending the data to the client
    // by using response.write() method
    response.write("GeeksForGeeks")
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
Received: GeeksForGeeks
Received: The sum weight of all Http2Stream : 0
client destroyed
server destroyed
```

**参考**:

[https://nodejs . org/dist/latest-v 12 . x/docs/API/https 2 . html # https 2 _ response _ write _ chunk _ encoding _ callback](https://nodejs.org/dist/latest-v12.x/docs/api/http2.html#http2_response_write_chunk_encoding_callback)