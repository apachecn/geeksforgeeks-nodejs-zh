# node . js http 2 server manager . remove header()方法

> 原文:[https://www . geesforgeks . org/node-js-http2 server response-remove header-method/](https://www.geeksforgeeks.org/node-js-http2serverresponse-removeheader-method/)

**Http2ServerResponse . remove header()**是 http2 模块中类 http2 server response 的内置应用程序编程接口，用于删除已排队等待隐式发送的标头。

**语法:**

```
response.removeHeader(name)
```

**参数**:该方法以表头名称为参数。

**返回值**:此方法不返回值。

**如何生成私钥和公钥证书？**

**1。文件名:私钥**

打开记事本，复制粘贴以下密钥，将文件保存为 ***私钥. PEM***T0】

**2。文件名:公共证书**

打开记事本，复制粘贴以下密钥，将文件保存为 ***公共证书***T0】

**示例 1:Filename:index . js**

## Javascript

```
// Node.js program to demonstrate the
// Http2ServerResponse.removeHeader() method
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

    console.log("Before operation")
    console.log(response.getHeaders());

    // Removing particular header
    // by using removeHeader() method
    const value = response.removeHeader('Content-Type')

    console.log("\nAfter operation")
    console.log(response.getHeaders());
};

// Creating and initializing server
// by using http2.createServer() method
const server = http2.createServer(options,http2Handlers);

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

const req = client.request({ ':method': 'GET', ':path': '/'});

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
Before operation
{ 'content-type': 'hello world; charset=utf-8' }

After operation
{}
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
// Http2ServerResponse.removeHeader() method
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
    response.setHeader('Set-Cookie', ['foo=bar', 'bar=baz']);

    console.log("Before operation")
    console.log(response.getHeaders());

    // Removing particular header
    // by using removeHeader() method
    const value = response.removeHeader('Foo')

    console.log("\nAfter operation")
    console.log(response.getHeaders());
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
Before operation
{ foo: 'bar', 'set-cookie': [ 'foo=bar', 'bar=baz' ] }

After operation
{ 'set-cookie': [ 'foo=bar', 'bar=baz' ] }
Received: The sum weight of all Http2Stream : 0       
client destroyed
server destroyed
```

**参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/https 2 . html # https 2 _ response _ removeheader _ name](https://nodejs.org/dist/latest-v12.x/docs/api/http2.html#http2_response_removeheader_name)