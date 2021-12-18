# node . js http 2 . getdefaultsettings()方法

> 原文:[https://www . geesforgeks . org/node-js-http2-getdefaultsettings-method/](https://www.geeksforgeeks.org/node-js-http2-getdefaultsettings-method/)

**http2 . getdefaultsettings()**是 http2 模块中类 http2 的内置应用程序编程接口，用于提供包含 Http2Session 实例默认设置的对象。

**语法:**

```js
const http2.getDefaultSettings()

```

**参数:**此方法不接受任何参数作为参数。

**返回值:**该方法返回一个包含 Http2Session 实例默认设置的对象。

**如何生成私钥和公钥证书？**

**1。文件名:私钥**

打开记事本，复制粘贴以下密钥，将文件保存为 ***私钥. PEM***T0】

**2。文件名:公共证书**

打开记事本，复制粘贴以下密钥，将文件保存为 ***公共证书***T0】

**示例 1:** **文件名:index . js**

## Javascript

```js
// Node.js program to demonstrate the
// http2.getDefaultSettings() 

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

// Getting default setting 
// by using getDefaultSetting() method
const value =  http2.getDefaultSettings()

console.log("header table size : " 
    + value.headerTableSize)

server.on('stream', (stream, requestHeaders) => {
  stream.respond({ 
    ':status': 200, 
    'content-type': 'text/plain' 
  });

  stream.write('hello ');
  stream.end('world');

  // Stopping the server
  // by using the close() method
  server.close(() => {
    console.log("server closed");
  })
});

server.listen(8000);

// Creating and initializing client
// by using tls.connect() method
const client = http2.connect(
    'http://localhost:8000');

const req = client.request({ 
  ':method': 'GET', ':path': '/' });

req.on('response', (responseHeaders) => {
  console.log("status : " 
  + responseHeaders[":status"]);
});

req.on('data', (data) => {
  console.log('Received: %s ',
  data.toString().replace(/(\n)/gm,""));
});

req.on('end', () => {
  client.close(() => {
    console.log("client closed");
  })
});
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
header table size : 4096
status : 200
Received: hello
Received: world
client closed
server closed

```

**示例 2:** **文件名:index . js**

## Javascript

```js
// Node.js program to demonstrate the
// http2.getDefaultSettings() method

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

// Getting default setting 
// by using getDefaultSetting() method
const value =  http2.getDefaultSettings()

console.log("initial window size : " 
    + value.initialWindowSize)

server.on('stream', (stream, requestHeaders) => {
  stream.end('world');

  // Stopping the server
  // by using the close() method
  server.close(() => {
    console.log("server closed");
  })
});

server.listen(8000);

// Creating and initializing client
// by using tls.connect() method
const client = http2.connect(
    'http://localhost:8000');

const req = client.request({ 
  ':method': 'GET', ':path': '/' });

req.on('data', (data) => {
  console.log('Received: %s ',
  data.toString().replace(/(\n)/gm,""));
});

req.on('end', () => {
  client.close(() => {
    console.log("client closed");
  })
});
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
initial window size : 65535
Received: world
client closed
server closed

```

**参考**:[https://nodejs . org/dist/latest-v 12 . x/docs/API/https 2 . html # https 2 _ https 2 _ getdefaultsettings](https://nodejs.org/dist/latest-v12.x/docs/api/http2.html#http2_http2_getdefaultsettings)