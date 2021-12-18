# node . js htp2stream . sentinfoheaders 方法

> 原文:[https://www . geesforgeks . org/node-js-http2 stream-sentinfoheaders-method/](https://www.geeksforgeeks.org/node-js-http2stream-sentinfoheaders-method/)

**http2 stream . sentinfoheaders**是 Http 2 模块中 http2stream 类的内置应用程序编程接口，用于获取包含发送到该 Http2Stream 的出站信息(附加)头的对象。

**语法:**

```js
http2stream.sentInfoHeaders
```

**参数:**此方法不接受任何参数。

**返回值:**这个方法返回一个包含发送到这个 Http2Stream 的出站信息(附加)头的对象。

**如何生成私钥和公钥证书？**

1.  **私钥:**打开记事本，如下图复制粘贴如下密钥:

```js
-----BEGIN RSA PRIVATE KEY-----
MIICXQIBAAKBgQC38R9wXcUbhOd44FavgmE5R3K4JeYOHLnI7dUq1B8/Gv7l3SOg
JKef/m9gM1KvUx951mapXGtcWgwB08J3vUE2YOZ4tWJArrVZES0BI/RmFAyhQFP5
HcWl3LSM9LRihP98F33oIkKaCxA5LxOrkgpV4HrUzIKTABDYah7RPex1WQIDAQAB
AoGBAIXR71xxa9gUfc5L7+TqBs+EMmrUb6Vusp8CoGXzQvRHMJCMrMFySV0131Nu
o0YYRDsAh1nJefYLMNcXd1BjqI+qY8IeRsxaY+9CB2KKGVVDO2uLdurdC2ZdlWXT
Vwr3dDoyR0trnXJMmH2ijTeO6bush8HuXxvxJBjvEllM5QYxAkEA3jwny9JP+RFu
0rkqPBe/wi5pXpPl7PUtdNAGrh6S5958wUoR4f9bvwmTBv1nQzExKWu4EIp+7vjJ
fBeRZhnBvQJBANPjjge8418PS9zAFyKlITq6cxmM4gOWeveQZwXVNvav0NH+OKdQ
sZnnDiG26JWmnD/B8Audu97LcxjxcWI8Jc0CQEYA5PhLU229lA9EzI0JXhoozIBC
TlcKFDuLm88VSmlHqDyqvF9YNOpEdc/p2rFLuZS2ndB4D+vu6mjwc5iZ3HECQCxy
GBHRclQ3Ti9w76lpv+2kvI4IekRMZWDWnnWfwta+DGxwCgw2pfpleBZkWqdBepb5
JFQbcxQJ0wvRYXo8qaUCQQCgTvWswBj6OTP7LTvBlU1teAN2Lnrk/N5AYHZIXW6m
nUG9lYvH7DztWDTioXMrruPF7bdXfZOVJD8t0I4OUzvC
-----END RSA PRIVATE KEY-----
```

1.  现在将文件保存为*私钥。PEM*T2】
2.  **公共证书:**打开记事本，复制粘贴以下密钥:

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

1.  现在保存为*公共证书*T2】

**示例 1:文件名:index.js**

## java 描述语言

```js
// Node.js program to demonstrate the
// Http2Stream.sentInfoHeaders method

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

   stream.additionalHeaders({
      ':status': 100,
      'content-type': 'text/plain'
   });

   // Getting rst stream code
   // by using sentInfoHeaders api
   const status = stream.sentInfoHeaders;

   console.log(status)

   stream.end("the end");

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
   ':method': 'GET', ':path': '/'
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

使用以下命令运行 index.js 文件:

```js
node index.js
```

**输出:**

```js
[
  [Object: null prototype] {
    ':status': 100,
    'content-type': 'text/plain'
  }
]
Received: the end 
client destroyed
server destroyed
```

**示例 2:** **文件名:index.js**

## java 描述语言

```js
// Node.js program to demonstrate the
// Http2Stream.sentInfoHeaders method

const http2 = require('http2');
const fs = require('fs');

// Private key and public certificate for access
const options = {
   key : fs.readFileSync('private-key.pem'),
   cert : fs.readFileSync('public-cert.pem'),
};

// Creating and initializing server
// by using http2.createServer() method
const server = http2.createServer(options);

server.on('stream', (stream, requestHeaders) => {

    // Getting rst stream code
    // by using sentInfoHeaders api
    const status = stream.sentInfoHeaders;

    stream.end("header object: " + status);

    // Stopping the server
    // by using the close() method
    server.close(() => {
       console.log("server destroyed");
    })
});

server.listen(8000);

// Creating and initializing client
// by using tls.connect() method
const client = http2
    .connect('http:// localhost:8000');

const req = client.request({
    ':method' : 'GET', ':path' : '/'
});

req.on('data', (data) => {
    console.log('Received: %s ',
    data.toString().replace(/ (\n) / gm, ""));
});

req.on('end', () => {
  client.close(() => {
     console.log("client destroyed");
  })
});
```

使用以下命令运行 index.js 文件:

```js
node index.js
```

**输出:**

```js
Received: header object: undefined
client destroyed
server destroyed
```

**参考:**T2】https://nodejs . org/dist/latest-v 12 . x/docs/API/https 2 . html # https 2 _ http2 stream _ additional headers _ headers