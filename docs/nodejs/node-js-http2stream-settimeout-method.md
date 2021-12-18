# node . js http 2 stream . settimeout()方法

> 原文:[https://www . geesforgeks . org/node-js-http2 stream-settimeout-method/](https://www.geeksforgeeks.org/node-js-http2stream-settimeout-method/)

**http2stream.setTimeout()** 方法是 http2 模块内 http2stream 类的内置应用程序编程接口，用于设置特定动作发生后的持续时间。

**语法:**

```js
const http2stream.setTimeout(msecs, callback)
```

**参数:**该方法取持续时间的整数值。

**返回值:**这个方法只返回一个回调函数，用于在超时后开始特定的活动。

**如何生成私钥和公钥证书？**

1.  **私钥:**打开记事本，复制粘贴以下密钥:

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

1.  现在将文件保存为*私钥*
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

1.  现在将文件保存为*公共证书*

**示例 1:** **文件名:index.js**

## java 描述语言

```js
// Node.js program to demonstrate the
// Http2Stream.setTimeout() API
const http2 = require('http2');
const fs = require('fs');

// private key and public certificate for access
const options = {
  key: fs.readFileSync('private-key.pem'),
  cert: fs.readFileSync('public-cert.pem'),
};

// creating and initializing server
// by using http2.createServer() api
const server = http2.createServer(options);

server.on('stream', (stream, requestHeaders) => {

   // setting time out for the stream
   // by using setTimeout()
   stream.setTimeout(3000, ()=>{
     stream.respond({
       ':status': 200,
       'content-type': 'text/plain'
     });

     stream.end("surprise !!!");
   })

  // stopping the server
  // by using the close() method
  server.close(()=>{
    console.log("server destroyed");
  })
});
server.listen(8000);

// creating and initializing client
// by using tls.connect() method
const client = http2.connect(
    'http://localhost:8000');

const req = client.request(
  { ':method': 'GET', ':path': '/' });

req.on('response', (responseHeaders) => {

  console.log("status : "
  + responseHeaders[":status"]);
});

req.on('data', (data) => {

  console.log('Received: %s ',
          data.toString().replace(/(\n)/gm, ""));
});

req.on('end', () =>
{
  client.close(()=>{
    console.log("client destroyed");
  })

});
```

**输出:**

```js
status : 200
Received: surprise !!!
client destroyed
server destroyed
```

使用以下命令运行 index.js 文件:

```js
node index.js
```

**例 2:**

**文件名:index.js**

## java 描述语言

```js
// Node.js program to demonstrate the
// Http2Stream.setTimeout() API
const http2 = require('http2');
const fs = require('fs');

// private key and public certificate for access
const options = {
  key: fs.readFileSync('private-key.pem'),
  cert: fs.readFileSync('public-cert.pem'),
};

// creating and initializing client
// by using tls.connect() method
const client = http2.connect(
    'http://localhost:8000');

const req = client.request(
  { ':method': 'GET', ':path': '/' });

req.on('response', (responseHeaders) => {

  console.log("status : "
  + responseHeaders[":status"]);
});

req.on('data', (data) => {

  console.log('Received: %s ',
  data.toString().replace(/(\n)/gm, ""));
});

req.on('end', () =>
{
  client.close(()=>{
    console.log("client destroyed");
  })

  // Cancel the stream if there's
  // no activity after 3 seconds
  req.setTimeout(3000, ()=>{

    req.close(NGHTTP2_CANCEL);
  })

});
```

**输出:**

> events.js:292
> 投 er；//未处理的“错误”事件
> ^
> 错误【ERR_HTTP2_STREAM_CANCEL】:挂起的流已被取消(原因:connect econrefed 127 . 0 . 0 . 1:8000)
> 在 ClientHttp2Session.destroy(内部/http2/core.js:1379:20)
> 在 Socket.socketOnError(内部/http2/core.js:2758:13)
> 在 Socket.emit(事件. js:330 . 0 . 0 . 0 . 0 . 0 . 0 . 0 . 0 . 0 . 0 . 0 . 0 . 0 . 0 . 0
> 代码:【ECONNREFUSED】，
> syscall:【connect】，
> 地址:【127.0.0.1】，
> 端口:8000
> }，
> 代码:【ERR _ HTTP2 _ STREAM _ CANCEL】
> }

使用以下命令运行 index.js 文件:

```js
node index.js
```

**参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/http2 . html # http2 _ http2 stream _ settimeout _ msecs _ callback](https://nodejs.org/dist/latest-v12.x/docs/api/http2.html#http2_http2stream_settimeout_msecs_callback)