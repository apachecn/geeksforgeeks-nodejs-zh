# Node.js http2session.destroy()方法

> 原文:[https://www . geesforgeks . org/node-js-http2 session-destroy-method/](https://www.geeksforgeeks.org/node-js-http2session-destroy-method/)

**http2session.destroy()** 是 http2 模块中类 http2session 的内置应用程序编程接口，用于销毁该特定会话。

**语法:**

```
const http2session.destroy([error][, code])
```

**参数:**该方法采用以下两个可选参数作为参数:

*   **错误:**如果由于错误导致 Http2Session 被销毁，则为错误对象。

*   **代码:**为 HTTP/2 错误代码，否则为 NO_ERROR 代码。

**返回值:**这个方法没有什么可返回的。
**如何生成私钥和公钥证书？**

1.  **私钥:**打开记事本，如下图复制粘贴如下密钥:

```
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

1.  现在保存为*公共证书*T2】

**示例 1:文件名:index.js**

## java 描述语言

```
// Node.js program to demonstrate the
// http2session.destroy() method

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

   // Getting session object
   // by using session method
   const http2session = stream.session;

   // Getting alpnProtocol of this session
   // by using alpnProtocol method
   const alpnProtocol = http2session.alpnProtocol;

   stream.end("session protocol : " + alpnProtocol);

   // If any error occur
   http2session.on('error', (code) => {
     console.log(code);
   })

   // Callback for close event
   http2session.on('close', () => {
     console.log("session is destroyed");
   })

   // Stopping the server
   // by using the close() method
   server.close(() => {
      console.log("server destroyed");
      http2session.destroy();
  })
});

server.listen(8000);

// Creating and initializing client
// by using tls.connect() method
const client = http2
  .connect('http://localhost:8000');

const req = client.request({
  ':method': 'GET', ':path': '/'
});

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
    console.log("client destroyed");
  })
});
```

使用以下命令运行 index.js 文件:

```
node index.js
```

**输出:**

```
status : 200
Received: hello
Received: session protocol : h2c
client destroyed
server destroyed
session is destoryed
```

**示例 2:** **文件名:index.js**

## java 描述语言

```
// Node.js program to demonstrate the
// http2session.destroy() method

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

   // Getting session object
   // by using session method
   const http2session = stream.session;

   // Destroying session
   // by using destroy() method
   http2session.destroy();

   console.log("session is closed");

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
  .connect('http://localhost:8000');

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

```
node index.js
```

**输出:**

```
session is closed
server destroyed
```

**参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/https 2 . html # https 2 _ https 2 session _ destroy _ error _ code](https://nodejs.org/dist/latest-v12.x/docs/api/http2.html#http2_http2session_destroy_error_code)