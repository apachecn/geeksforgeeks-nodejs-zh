# node . js http 2 server response . settimeout()方法

> 原文:[https://www . geesforgeks . org/node-js-http2 server response-settimeout-method/](https://www.geeksforgeeks.org/node-js-http2serverresponse-settimeout-method/)

**Http2ServerResponse . settimeout()**是 http2 模块内的类 http2 server response 的内置应用程序编程接口，用于设置特定操作发生后的持续时间。

**语法:**

```js
const response.response.setTimeout(msecs[, callback])
```

**参数**:该方法取持续时间的整数值。

**返回值**:这个方法只返回一个回调函数，用于在超时后开始特定的活动。

**如何生成** **私钥和公钥证书？**

**1。文件名:** **私钥**

**第一步**:打开记事本复制粘贴以下密钥，将文件保存为*私钥. pem*

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

**2。文件名:** **公共证书**

**第一步**:打开记事本，复制粘贴以下密钥，保存为*公共证书*T0

**示例 1:Filename:index . js**

## Javascript

```js
// Node.js program to demonstrate the
// Http2ServerResponse.setTimeout() API
const http2 = require('http2');
const fs = require('fs');

// Private key and public certificate for access
const options = {
  key: fs.readFileSync('private-key.pem'),
  cert: fs.readFileSync('public-cert.pem'),
};

// Request and response handler
const http2Handlers = (request, response) => {

  // Setting timeout for the stream
  response.setTimeout(3000,()=>{
    response.end("surprise!!!")
 })

 };

// Creating and Initializing server using
// http2.createServer() method

const server = http2.createServer(options, http2Handlers);

server.on('stream', (stream, requestHeaders) => {

  // Stopping the server by using close method
  server.close(()=>{
    console.log("server destroyed");
  })
});
server.listen(8000);

// Creating and initializing client by
// using tls.connect() method

const client = http2.connect('http://localhost:8000');

// Handling the request
const req = client.request({
  ':method': 'GET', ':path': '/' });

req.on('response', (responseHeaders) => {

  // Showing the response 
  console.log("status : " + responseHeaders[":status"]);
});

req.on('data', (data) => {

  // Showing the data
  console.log('Received: %s ',
          data.toString().replace(/(\n)/gm,""));
});

req.on('end', () => {

  // Closing the client
  client.close(()=>{
    console.log("client destroyed");
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
Received: surprise!!!
client destroyed
server destroyed
```

**示例 2:Filename:index . js**

## Javascript

```js
// Node.js program to demonstrate the
// Http2ServerResponse.setTimeout() method
const http2 = require('http2');
const fs = require('fs');

// Private key and public certificate for access
const options = {
  key: fs.readFileSync('private-key.pem'),
  cert: fs.readFileSync('public-cert.pem'),
};

// Request and response handler
const http2Handlers = (request, response) => {

  // Setting timeout for the stream
  response.setTimeout(3000,()=>{
    response.end("surprise!!!")
  })
};

// Creating and initializing server
// by using http2.createServer() method
const server = http2.createServer(options, http2Handlers);

server.on('stream', (stream, requestHeaders) => {

  // Closing stream before timeout
  stream.close()

  // Stopping the server
  // by using the close() method
  server.close(()=>{
    console.log("server destroyed");
  })
});

// Listing the server on port 8000
server.listen(8000);

// Creating and Initializing client
// by using tls.connect() method
const client = http2.connect('http://localhost:8000');

// Handling the GET Request
const req = client.request({
  ':method': 'GET', ':path': '/' });

req.on('response', (responseHeaders) => {

  // Showing the response
  console.log("status : " + responseHeaders[":status"]);
});

req.on('data', (data) => {

  // Showing the data
  console.log('Received: %s ',
          data.toString().replace(/(\n)/gm,""));
});

req.on('end', () => {

  // Closing the client
  client.close(()=>{
    console.log("client destroyed");
  })
});
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
client destroyed
server destroyed
```

**参考**:[https://nodejs . org/dist/latest-v 12 . x/docs/API/https 2 . html # https 2 _ response _ settimeout _ msecs _ callback](https://nodejs.org/dist/latest-v12.x/docs/api/http2.html#http2_response_settimeout_msecs_callback)