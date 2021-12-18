# Node.js Http2Stream 关闭事件

> 原文:[https://www . geesforgeks . org/node-js-http2 stream-close-event/](https://www.geeksforgeeks.org/node-js-http2stream-close-event/)

当 http2 流被破坏时，Http 2 服务器中的**“关闭”事件**被发出。

**语法:**

```
Event: 'close'
```

**参数:**此事件不接受任何参数作为参数。

**返回值:**这个事件只返回一个回调函数。

**如何生成私钥和公钥证书？**

**私钥:**

**第一步:**打开记事本，复制粘贴如下按键。

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

**步骤 2:** 另存为*私钥. pem*

**公共证书:**

**第一步:**打开记事本，复制粘贴如下按键。

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

**步骤 2:** 另存为*公共证书*

**示例 1:** **文件名:index . js**

## Javascript

```
// Node.js program to demonstrate the
// close Event API
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

server.on('stream', (stream, requestHeaders) => {
  stream.respond({ 
    ':status': 200, 
    'content-type': 'text/plain' 
  });
  stream.write('hello ');

   // Getting rst stream code
   // by using rstCode api
   const status = stream.rstCode;

   stream.end("RST_STREAM error code : "
     + status);

   stream.destroy();

   // Close event is emitted
   stream.on('close',()=>{
     console.log("stream is destroyed")
   })

  // Stopping the server by
  // using the close() method
  server.close(()=>{
    console.log("server destroyed");
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
  client.close(()=>{
    console.log("client destroyed");
  })
});
```

**输出:**

```
stream is destroyed
status : 200
Received: hello
client destroyed
server destroyed
```

使用以下命令运行 index.js 文件:

```
node index.js
```

**示例 2:** **文件名:index . js**

## Javascript

```
// Node.js program to demonstrate the
// close Event
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

server.on('stream', (stream, requestHeaders) => {

   // Getting rst stream code
   // by using rstCode api
   const status = stream.rstCode;

   stream.end("RST_STREAM error code : " + status);

   stream.destroy();

   // Close event is emitted
   stream.on('close',()=>{
     console.log("stream is destroyed")
   })

  // Stopping the server by
  // using the close() method
  server.close(()=>{
    console.log("server destroyed");
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
  client.close(()=>{
    console.log("client destroyed");
  })
});
```

**输出:**

```
stream is destroyed
Received: RST_STREAM error code : 0
client destroyed
server destroyed
```

使用以下命令运行 index.js 文件:

```
node index.js
```

**参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/https 2 . html # https 2 _ event _ close _ 1](https://nodejs.org/dist/latest-v12.x/docs/api/http2.html#http2_event_close_1)