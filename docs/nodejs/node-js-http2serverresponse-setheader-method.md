# node . js http 2 server response . setheader()方法

> 原文:[https://www . geesforgeks . org/node-js-http2 server response-set header-method/](https://www.geeksforgeeks.org/node-js-http2serverresponse-setheader-method/)

**Http2ServerResponse . setheader()**是 http2 模块内的类 http2 server response 的内置应用程序编程接口，用于设置头名称和该数据头的特定值。

**语法:**

```
response.setHeader(name, value)
```

**参数**:该方法以下列参数为参数。

*   **Name:** Header name.
*   **Value: the value of** header.

**返回值**:这个方法没有什么可返回的。

**如何生成** **私钥和公钥证书？**

**文件名:私钥**

**第 1 步**:打开记事本复制粘贴以下密钥，将文件另存为*私钥. pem.*

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

**2:文件名:公共证书**

打开记事本复制粘贴以下密钥将文件保存为*公共证书*T0】

**示例 1:Filename:index . js**

## Javascript

```
// Node.js program to demonstrate the
// Http2ServerResponse.setHeader() method
// Importing the http2 module
const http2 = require('http2');

// Importing the fs module
const fs = require('fs');

// Private key and public certificate for access
const options = {

  // Reading the file private.key.pem file synchronously
  key: fs.readFileSync('private-key.pem'),

  // Reading the file public.cert.pem file synchronously
  cert: fs.readFileSync('public-cert.pem'),
};

// Request and response handler
const http2Handlers = (request, response) => {

  // Setting new header by using response.setHeader()
  response.setHeader('Content-Type', 'hello world; charset=utf-8');

  // Getting header's object by using getHeaders() method
  const value = response.getHeaders()

  // Display the header
  console.log(value);
};

// Creating and Initializing server by
// using http2.createServer() method
const server = http2.createServer(options,http2Handlers);

server.on('stream', (stream, requestheader) => {
  stream.write('hello ');

   // Getting all information of this http2stream
   // object by using state api
   const status = stream.state;

   stream.end("priority weight : " + status.weight);

   // Stopping the server by
   // using the close() method
   server.close(()=>{
     console.log("server destroyed");
  })
});
server.listen(8000);

// Creating and initializing client  by
// using tls.connect() method
const client = http2.connect('http://localhost:8000');

// Handling the request
const req = client.request({ ':method': 'GET', ':path': '/'});

req.on('response', (responsesocket) => {
  console.log("status : " + responsesocket[":status"]);
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

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
{ 'content-type': 'hello world; charset=utf-8' }
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
// Http2ServerResponse.setHeader() method
// Importing http2 module
const http2 = require('http2');

// Importing fs module
const fs = require('fs');

// Private key and public certificate for access
const options = {

  // Reading the private-key.pem file synchronously
  key: fs.readFileSync('private-key.pem'),

  // Reading the public-cert.pem file synchronously
  cert: fs.readFileSync('public-cert.pem'),
};

// Request and response handler
const http2Handlers = (request, response) => {

  // Setting new header
  response.setHeader('Foo', 'bar');
  response.setHeader('Set-Cookie', ['foo=bar', 'bar=baz']);

  // Getting header's object
  // by using getHeaders() method
  const value = response.getHeaders()

 // Display the header
 console.log(value);
};

// Creating and initializing server
// by using http2.createServer() method
const server = http2.createServer(options, http2Handlers);

server.on('stream', (stream, requestHeaders) => {

   // Getting all information of this http2stream object
   // by using state api
   const status = stream.state;

   stream.end("The sum weight of all Http2Stream : "
       + status.sumDependencyWeight);

  // Stopping the server
  // by using the close() method
  server.close(()=>{
    console.log("server destroyed");
  })
});
server.listen(8000);

// Creating and initializing client
// by using tls.connect() method
const client = http2.connect('http://localhost:8000');

const req = client.request({
  ':method': 'GET', ':path': '/www.geeksforgeeks.org' });

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

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
{ foo: 'bar', 'set-cookie': [ 'foo=bar', 'bar=baz' ] }
Received: The sum weight of all Http2Stream : 0
client destroyed
server destroyed
```

**参考**:[https://nodejs . org/dist/latest-v 12 . x/docs/API/https 2 . html # https 2 _ response _ set header _ name _ value](https://nodejs.org/dist/latest-v12.x/docs/api/http2.html#http2_response_setheader_name_value)