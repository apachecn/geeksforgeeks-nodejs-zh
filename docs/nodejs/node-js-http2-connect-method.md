# Node.js http2.connect()方法

> 原文:[https://www.geeksforgeeks.org/node-js-http2-connect-method/](https://www.geeksforgeeks.org/node-js-http2-connect-method/)

**http2.connect()** 是 http2 模块中类 http2 的内置应用编程接口，用于返回 ClientHttp2Session 实例。

**语法:**

```js
const http2.connect(authority[, options][, listener])

```

**参数**:该方法以下面的参数作为参数:

*   **Permission** : is the URL that represents the connection of the remote HTTP/2 server.
*   **贺喜**:唉哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟 maxdeflate dynamictablesize maxsettings maxsession memory 阿悦，吴亚玲吴亚玲。
*   **Listener** : It is the primary listener of [[Connection]](https://nodejs.org/dist/latest-v12.x/docs/api/http2.html#http2_event_connect) event.

**返回值**:这个方法返回 ClientHttp2Session 实例的对象。

**如何生成私钥和公钥证书？**

**1。文件名:私钥**打开记事本复制粘贴以下密钥，将文件保存为 ***私钥***

**2。文件名:公共证书**打开记事本复制粘贴以下密钥，将文件保存为 ***公共证书 pem***

```js
-----BEGIN CERTIFICATE-----
MIICfzCCAegCCQDxxeXw914Y2DANBgkqhkiG9w0BAQsFADCBgzELMAkGA1UEBhMC
SU4xEzARBgNVBAgMCldlc3RiZW5nYWwxEDAOBgNVBAcMB0tvbGthdGExFDASBgNV
BAoMC1BhbmNvLCBJbmMuMRUwEwYDVQQDDAxSb2hpdCBQcmFzYWQxIDAeBgkqhkiG
9w0BCQEWEXJvZm9mb2ZAZ21haWwuY29tMB4XDTIwMDkwOTA1NTExN1oXDTIwMTAw
OTA1NTExN1owgYMxCzAJBgNVBAYTAklOMRMwEQYDVQQIDApXZXN0YmVuZ2FsMRAw
DgYDVQQHDAdLb2xrYXRhMRQwEgYDVQQKDAtQYW5jbywgSW5jLjEVMBMGA1UEAwwM
Um9oaXQgUHJhc2FkMSAwHgYJKoZIhvcNAQkBFhFyb2ZvZm9mQGdtYWlsLmNvbTCB
nzANBgkqhkiG9w0BAQEFAAOBjQAwgYkCgYEAt/EfcF3FG4TneOBWr4JhOUdyuCXm
Dhy5yO3VKtQfPxr+5d0joCSnn/5vYDNSr1MfedZmqVxrXFoMAdPCd71BNmDmeLVi
QK61WREtASP0ZhQMoUBT+R3Fpdy0jPS0YoT/fBd96CJCmgsQOS8Tq5IKVeB61MyC
kwAQ2Goe0T3sdVkCAwEAATANBgkqhkiG9w0BAQsFAAOBgQATe6ixdAjoV7BSHgRX
bXM2+IZLq8kq3s7ck0EZrRVhsivutcaZwDXRCCinB+OlPedbzXwNZGvVX0nwPYHG
BfiXwdiuZeVJ88ni6Fm6RhoPtu2QF1UExfBvSXuMBgR+evp+e3QadNpGx6Ppl1aC
hWF6W2H9+MAlU7yvtmCQQuZmfQ==
-----END CERTIFICATE-----
```

**示例 1:** **文件名:index . js**

## Javascript

```js
// Node.js program to demonstrate the
// http2.connect() method

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
// by using http2.connect() method
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
// http2.connect() method

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
  stream.end('world');

  // Stopping the server
  // by using the close() method
  server.close(() => {
    console.log("server closed");
  })
});

server.listen(8000);

// Creating and initializing client
// by using http2.connect() method
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
Received: world
client closed
server closed

```

**参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/https 2 . html # https 2 _ https 2 _ connect _ authority _ options _ listener](https://nodejs.org/dist/latest-v12.x/docs/api/http2.html#http2_http2_connect_authority_options_listener)