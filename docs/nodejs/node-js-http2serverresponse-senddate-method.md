# node . js http 2 server response . send date 方法

> 原文:[https://www . geesforgeks . org/node-js-http2 server response-send date-method/](https://www.geeksforgeeks.org/node-js-http2serverresponse-senddate-method/)

**Http2ServerResponse . send Date**是 http2 模块内一个内置的类 http2 server response 的应用编程接口，用于检查响应中是否自动生成并发送了 Date 头。

**语法:**

```
response.sendDate
```

**参数**:该方法不接受任何参数作为参数。

**返回值**:当且仅当响应中自动生成并发送日期头时，该方法返回真。

**如何生成私钥和公钥证书？**

**1。文件名:私钥**

打开记事本，复制粘贴以下密钥，将文件保存为 ***私钥. PEM***T0】

**2。文件名:公共证书**

打开记事本，复制粘贴以下密钥，将文件保存为 ***公共证书***T0】

**示例 1:Filename:index . js**

## Javascript

```
// Node.js program to demonstrate the
// Http2ServerResponse.sendDate method
const http2 = require('http2');
const fs = require('fs');

// Private key and public certificate for access
const options = {
    key: fs.readFileSync('private-key.pem'),
    cert: fs.readFileSync('public-cert.pem'),
};

// Request and response handler
const http2Handlers = (request, response) => {

    // Checking if the data header is sent or not
    const value = response.sendDate

    if (value)
        console.log("data header is sent")
    else
        console.log("data header is not sent")
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
data header is sent
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
// Http2ServerResponse.sendDate method
const http2 = require('http2');
const fs = require('fs');

// Private key and public certificate for access
const options = {
    key: fs.readFileSync('private-key.pem'),
    cert: fs.readFileSync('public-cert.pem'),
};

// Request and response handler
const http2Handlers = (request, response) => {

    // Checking if the data header is sent or not
    const value = response.sendDate

    if (value)
        response.end("data header is sent")
    else
        response.end("data header is not sent")
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
Received: data header is sent
client destroyed
server destroyed
```

**参考**:[https://nodejs . org/dist/latest-v 12 . x/docs/API/https 2 . html # https 2 _ response _ send date](https://nodejs.org/dist/latest-v12.x/docs/api/http2.html#http2_response_senddate)