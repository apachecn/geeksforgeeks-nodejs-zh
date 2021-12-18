# Node.js tlsSocket.getSession()方法

> 原文:[https://www . geesforgeks . org/node-js-tlssocket-get session-method/](https://www.geeksforgeeks.org/node-js-tlssocket-getsession-method/)

**tlsSocket.getSession()** 是 tls 模块中类 tlsSocket 的内置应用编程接口，用于返回 TLS 会话数据，如果没有协商会话，则返回未定义。

**语法:**

```
const tlsSocket.getSession()

```

**参数:**此方法不接受任何参数。

**返回值:**如果没有协商会话，该方法返回 TLS 会话数据或未定义。

**如何生成私钥和公钥证书？**

1.  **Private key:** Open notepad and copy paste the following key:

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

    将文件保存为*私钥*

2.  **Public certificate:** Open notepad and copy paste the following key:

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

    将文件保存为*公共证书*

**示例 1:** **文件名:index.js**

```
// Node.js program to demonstrate the
// tlsSocket.getSession() method

var tls = require('tls'),
    fs = require('fs'),

// Port and host address for server    
PORT = 1337,
HOST = '127.0.0.1',
value = null;

// Private key and public certificate for access
var options = {
  key: fs.readFileSync('private-key.pem'),
  cert: fs.readFileSync('public-cert.pem'),
  rejectUnauthorized: false
};

// Creating and initializing server
var server = tls.createServer(options, function(socket) {

  // Print the data that we received
  socket.on('data', function(data) {
     console.log('\nReceived: %s ',
     data.toString().replace(/(\n)/gm, ""));
  });

  // Stopping the server
  // by using the close() method
  server.close(() => {
    console.log("Server closed successfully");
  });
});

// Start listening on a specific port and address
// by using listen() method
server.listen(PORT, HOST, function() {
   console.log("I'm listening at %s, on port %s", HOST, PORT);
});

// Creating and initializing client
var client = tls.connect(PORT, HOST, options, function() {

  // Getting session date
  // by using tlsSocket.getSession() method
  value = client.getSession();

  client.write("TLS session data : " + value.toJSON().data);

  client.end(() => {
     console.log("Client closed successfully");
  });
});
```

**输出:**

> 我在 127.0.0.1 监听，端口 1337
> 客户端关闭成功
> 
> 收到:TLS 会话数据:48、130、2、173、2、1、1、2、2、3、4、4、2、19、2、4、0、4、0、161、6、2、4、95、94、43、77、162、4、2、2、28、32、163、130、2、131、48、130、2、127、48、130、1、220

**示例 2:** **文件名:index.js**

```
// Node.js program to demonstrate the
// tlsSocket.getSession() method

var tls = require('tls'),
    fs = require('fs'),

// Port and host address for server    
PORT = 1337,
HOST = '127.0.0.1';

// Private key and public certificate for access
var options = {
  key: fs.readFileSync('private-key.pem'),
  cert: fs.readFileSync('public-cert.pem'),
  rejectUnauthorized: false
};

// Creating and initializing server
var server = tls.createServer(options, function(socket) {

  // Getting session date
  // by using tlsSocket.getSession() method
  value = socket.getSession();

  socket.write("TLS session data : " + value.toJSON().data);

  // Stopping the server
  // by using the close() method
  server.close(() => {
    console.log("Server closed successfully")
  });
});

// Start listening on a specific port and address
// by using listen() method
server.listen(PORT, HOST, function() {
  console.log("I'm listening at %s, on port %s", HOST, PORT);
});

// creating and initializing client
var client = tls.connect(PORT, HOST, options, function() {
   console.log("client is connected");
});

client.on("data", function(data) {

  console.log('Received: %s',
  data.toString().replace(/(\n)/gm, ""));

  // Close the connection after receiving the message
  client.end(() => {
     console.log("client closed successfully")
  });
});
```

使用以下命令运行 index.js 文件:

```
node index.js

```

**输出:**

> 我在 127.0.0.1 监听，端口 1337
> 客户端已连接
> 收到:TLS 会话数据:48、65、2、1、1、2、2、3、4、4、2、19、2、4、0、4、0、161、6、2、4、95、94、44、214、162、4、2、28、32、164、34、4、32、112

**参考:**[https://nodejs . org/dist/latest-v1 . x/docs/API/TLS . html # TLS _ tlssoket _ get session](https://nodejs.org/dist/latest-v12.x/docs/api/tls.html#tls_tlssocket_getsession)