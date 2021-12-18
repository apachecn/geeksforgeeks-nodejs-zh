# node . js http 2 session . pending settingsack 方法

> 原文:[https://www . geesforgeks . org/node-js-http 2 session-pending settingsack-method/](https://www.geeksforgeeks.org/node-js-http2session-pendingsettingsack-method/)

**http2session . pending settingsack**是 http2 模块内类 http2 session 的内置应用编程接口，用于指示 http2session 当前是否正在等待对发送的 SETTINGS 帧的确认。

**语法:**

```js
const http2session.pendingSettingsAck
```

**参数:**此方法不接受任何参数。

**返回值:**此方法在调用 **http2session.settings()** 方法后返回 true，否则如果所有发送的 settings 帧都已被确认，则返回 false。

**如何生成私钥和公钥证书**

**私钥**

**第一步:**打开记事本，复制粘贴如下键

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

**步骤 2:** 另存为*私钥. pem*

**公共证书**

**第一步:**打开记事本，复制粘贴如下键

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

**步骤 2:** 另存为*公共证书*

**示例 1:** **文件名:index . js**

## Javascript

```js
// Node.js program to demonstrate the
// http2session.pendingSettingsAck API
const http2 = require('http2');
const fs = require('fs');

// Private key and public certificate
// for access
const options = {
  key: fs.readFileSync('private-key.pem'),
  cert: fs.readFileSync('public-cert.pem'),
};

// Creating and initializing server
// by using http2.createServer() api
const server = http2.createServer(options);

server.on('stream', (stream, requestHeaders) => {
  stream.respond({ 
    ':status': 200, 
    'content-type': 'text/plain' 
  });

  stream.write('hello ');

   const http2session = stream.session;

   // Checking if the acknowledgement is received
   // or not by using pendingSettingsAck API
   const status = http2session.pendingSettingsAck;

   if(status)
   stream.end("all frame is not  acknowledged")
   else
   stream.end("all frames are acknowledged")

  // Stopping the server by
  // using the close() method
  server.close(()=>{
    console.log("server localSettings");
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
    console.log("client localSettings");
  })
});
```

**输出:**

```js
status : 200
Received: hello
Received: all frame is not  acknowledged
client localSettings
server localSettings
```

使用以下命令运行 index.js 文件:

```js
node index.js
```

**示例 2:** **文件名:index . js**

## Javascript

```js
// Node.js program to demonstrate the
// http2session.pendingSettingsAck API
const http2 = require('http2');
const fs = require('fs');

// Private key and public certificate
// for access
const options = {
  key: fs.readFileSync('private-key.pem'),
  cert: fs.readFileSync('public-cert.pem'),
};

// Creating and initializing server
// by using http2.createServer() api
const server = http2.createServer(options);

server.on('stream', (stream, requestHeaders) => {

   // Getting session object
   // by using session api
   const http2session = stream.session;

   // Checking if the acknowledgement is received
   // or not by using pendingSettingsAck API
   const status = http2session.pendingSettingsAck;

   if(status)
     stream.end("all frame is not  acknowledged")
   else
     stream.end("all frames are acknowledged")

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

```js
Received: all frame is not  acknowledged
client destroyed
server destroyed
```

使用以下命令运行 index.js 文件:

```js
node index.js
```

**参考:**T2】https://nodejs . org/dist/latest-v 12 . x/docs/API/https 2 . html # https 2 _ https 2 session _ pendingsettingsack