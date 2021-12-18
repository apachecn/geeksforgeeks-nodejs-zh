# node . js http 2 . getunpackedsettings()方法

> 原文:[https://www . geeksforgeeks . org/node-js-http2-getunpackedsettings-method/](https://www.geeksforgeeks.org/node-js-http2-getunpackedsettings-method/)

**http2 . getunpackedsettings()**是 http2 模块中类 HTTP 2 的内置应用程序编程接口，用于提供 HTTP/2 设置对象，该对象包含由 http2.getPackedSettings()生成的来自给定缓冲区的反序列化设置。

**语法:**

```
const http2.getUnpackedSettings(buf)
```

**参数:**该功能以 http2 设置为参数。

**返回值:**该函数返回一个 HTTP/2 设置对象，该对象包含由 http2.getPackedSettings()生成的来自给定缓冲区的反序列化设置。

**如何生成私钥和公钥证书？**

**1。文件名:私钥**打开记事本复制粘贴以下密钥，将文件保存为 ***私钥***

**2。文件名:公共证书**打开记事本复制粘贴以下密钥，将文件保存为 ***公共证书 pem***

```
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

```
// Node.js program to demonstrate the
// http2.getPackedSettings() method

const http2 = require('http2');
const fs = require('fs');

// Private key and public certificate 
// for access
const options = {
    key: fs.readFileSync('private-key.pem'),
    cert: fs.readFileSync('public-cert.pem'),
};

// Creating and initializing server
// by using http2.createServer() method
const server = http2.createServer(options);

// Getting packed setting by using
// getPackedSettings() method
const value = http2.getPackedSettings(
        { maxFrameSize: 163955 })

const unpacked = http2.getUnpackedSettings(value);

console.log("max frame size :- " 
    + unpacked.maxFrameSize);

server.on('stream', (stream, requestHeaders) => {
    stream.respond({
        ':status': 200, 'content-type':
            'text/plain'
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
        data.toString().replace(/(\n)/gm, ""));
});

req.on('end', () => {
    client.close(() => {
        console.log("client closed");
    })
});
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
max frame size :- 163955
status : 200
Received: hello
Received: world
client closed
server closed
```

**示例 2:** **文件名:index . js**

## Javascript

```
// Node.js program to demonstrate the
// http2.getUnpackedSettings() method

const http2 = require('http2');
const fs = require('fs');

// Private key and public certificate
// for access
const options = {
    key: fs.readFileSync('private-key.pem'),
    cert: fs.readFileSync('public-cert.pem'),
};

// Creating and initializing server
// by using http2.createServer() method
const server = http2.createServer(options);

// Getting packed setting by using
// getPackedSettings() method
const value = http2.getPackedSettings({ 
        maxHeaderListSize: 655353 })

const unpacked = http2.getUnpackedSettings(value);

console.log("max Header list Size :- " 
    + unpacked.maxHeaderListSize);

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
        data.toString().replace(/(\n)/gm, ""));
});

req.on('end', () => {
    client.close(() => {
        console.log("client closed");
    })
});
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
max Header list Size :- 655353
Received: world
client closed
server closed

```

**参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/http2 . html # http2 _ http2 _ getunpackedsettings _ buf](https://nodejs.org/dist/latest-v12.x/docs/api/http2.html#http2_http2_getunpackedsettings_buf)