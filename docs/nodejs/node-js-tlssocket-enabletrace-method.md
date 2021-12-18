# node . js tlssocket . enabletrace()方法

> 原文:[https://www . geesforgeks . org/node-js-tlssocket-enable trace-method/](https://www.geeksforgeeks.org/node-js-tlssocket-enabletrace-method/)

tlsSocket.enableTrace()方法是 tls 模块中类 tlsSocket 的内置应用程序编程接口，用于调试 TLS 连接问题。

**语法:**

```
tlsSocket.enableTrace()
```

**参数:**此方法不接受任何参数。

**返回值:**此方法将在 stderr 中显示 TLS 数据包跟踪信息。

**如何生成私钥和公钥证书？**

*   **私钥**
    **第一步:**打开记事本复制粘贴如下密钥:

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

*   **步骤 2:** 另存为*私钥. PEM*T4】
*   **公共证书**
    **第一步:**打开记事本复制粘贴以下密钥:

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

*   **步骤 2:** 另存为*公共证书*T4】

**示例 1:** **文件名:index.js**

## java 描述语言

```
// Node.js program to demonstrate the
// tlsSocket.enableTrace() method
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

  // Display TLS packet trace information
  // by using tlsSocket.disableRenegotiation() method
  client.enableTrace();

  client.end(() => {
    console.log("Client closed successfully");
  });

});
```

使用以下命令运行 index.js 文件:

```
node index.js
```

**输出:**

> 我正在 127.0.0.1 端口监听 1337
> 发送记录
> 标头:
> 版本= TLS 1.2 (0x303)
> 内容类型=应用程序数据(23)
> 长度= 19
> 内部内容类型=警报(21)
> 级别=警告(1)，描述=关闭通知(0)
> 客户端成功关闭
> 服务器成功关闭
> 接收记录
> 标头:【T11 长度=245
> 票证 _ 寿命 _ 提示=7200
> 票证 _ 年龄 _ 添加=1553580394
> 票证 _ 现时(len = 8):000000000000
> 票证(len = 224):7c 75222 CD 19446 a 54 ce……2f 1948461 E4 f 43 c 6 db 54 a 6
> 无分机
> 接收记录

**示例 2:** **文件名:index.js**

## java 描述语言

```
// Node.js program to demonstrate the
// tlsSocket.enableTrace() method
var tls = require('tls'),
    fs = require('fs'),

// Port and host address for server
PORT = 1337,
HOST = '127.0.0.1';

// Private key and public certificate for access
var options = {
   key : fs.readFileSync('private-key.pem'),
   cert : fs.readFileSync('public-cert.pem'),
   rejectUnauthorized : false
};

// Creating and initializing server
var server = tls.createServer(options, function(socket) {

    // Display TLS packet trace information
    // by using tlsSocket.disableRenegotiation() method
    client.enableTrace();

    // Stopping the server
    // by using the close() method
    server.close(() => {
      console.log("Server closed successfully") });
    });

// Start listening on a specific port and address
// by using listen() method
server.listen(PORT, HOST, function() {
    console.log("I'm listening at %s, on port %s", HOST, PORT);
});

// Creating and initializing client
var client = tls.connect(PORT, HOST, options, function() {
  console.log("client is connected");
});

client.on("data", function(data) {
    console.log('\nReceived: %s ',
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

> 我在 127.0.0.1 监听，在端口 1337
> 客户端已连接
> 接收记录
> 头:
> 版本= TLS 1.2 (0x303)
> 内容类型=应用程序数据(23)
> 长度= 266
> 内部内容类型=握手(22)
> 新闻会话持续时间，长度=245
> 票证 _lifetime_hint=7200
> 票证 _ age _ add = 1288..5 dd7b 580 c29 d 366 b 3447 b 85121593 c9c
> 无分机

**参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/TLS . html # TLS _ tlssocket _ enable trace](https://nodejs.org/dist/latest-v12.x/docs/api/tls.html#tls_tlssocket_enabletrace)