# node . js tlssocket . getpeerffinished()方法

> 原文:[https://www . geesforgeks . org/node-js-tlssocket-getpeerffinished-method/](https://www.geeksforgeeks.org/node-js-tlssocket-getpeerfinished-method/)

**tlsSocket . GetPeerFinished()**方法是 TLS 模块内 tlsSocket 类的内置应用程序编程接口，用于返回作为 SSL/TLS 握手的一部分发送到套接字的最新已完成消息，如果尚未发送已完成消息，则返回未定义的消息。

**语法:**

```
const tlsSocket.getPeerFinished()
```

**参数:**此方法不接受任何参数。

**返回值:**这个方法返回一个包含完整握手消息摘要的缓冲区对象。

**如何生成私钥和公钥证书？**

1.  **私钥:**打开记事本复制粘贴以下密钥:

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

1.  将文件另存为*私钥. PEM*T2】
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

1.  将文件保存为*公共证书*T2】

**示例 1:** **文件名:index.js**

## java 描述语言

```
// Node.js program to demonstrate the
// tlsSocket.getPeerFinished() method

var tls = require('tls'),
    fs = require('fs'),

    // Port and host address for server   
    PORT = 1337,
    HOST = '127.0.0.1',
    value = null;

// Private key and public
// certificate for access
var options = {
    key: fs.readFileSync('private-key.pem'),
    cert: fs.readFileSync('public-cert.pem'),
    rejectUnauthorized: false
};

// Creating and initializing server
var server = tls.createServer(options,
                    function (socket) {

    // Print the data that we received
    socket.on('data', function (data) {
        console.log('\nReceived: %s ',
            data.toString().replace(/(\n)/gm, ""));
    });

    // Stopping the server
    // by using the close() method
    server.close(() => {
        console.log("Server closed successfully");
    });
});

// Start listening on a specific port
// and address by using listen() method
server.listen(PORT, HOST, function () {
    console.log("I'm listening at %s, "
        + "on port %s", HOST, PORT);
});

// Creating and initializing client
var client = tls.connect(PORT, HOST,
                options, function () {

    // Getting finished message digest
    // by using tlsSocket.getPeerFinished()
    // method
    value = client.getPeerFinished();

    client.write("Finisher message : "
            + value.toJSON().data);

    client.end(() => {
        console.log("Client closed successfully");
    });
});
```

**输出:**

> 我正在 127.0.0.1 监听端口 1337
> 客户端成功关闭
> 收到:整理器消息:133、120、218、179、42、34、167、40、96、3、66、211、61、190、255、206、180、162、245、65、237、69、57、234、179、149

**示例 2:** **文件名:index.js**

## java 描述语言

```
// Node.js program to demonstrate the
// tlsSocket.getPeerFinished() method

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
var server = tls.createServer(options,
                function (socket) {

    // Getting finished message digest
    // by using tlsSocket.getPeerFinished()
    // method
    value = socket.getPeerFinished();

    socket.write("Finisher message : "
            + value.toJSON().data);

    // Stopping the server
    // by using the close() method
    server.close(() => {
        console.log(
        "Server closed successfully")
    });
});

// Start listening on a specific
// port and address by using
// listen() method
server.listen(PORT, HOST, function () {
    console.log("I'm listening at %s, "
        + "on port %s", HOST, PORT);
});

// Creating and initializing client
var client = tls.connect(PORT, HOST,
            options, function () {
    console.log("client is connected");
});

client.on("data", function (data) {

    console.log('Received: %s',
        data.toString().replace(/(\n)/gm, ""));

    // Close the connection after
    // receiving the message
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

> 我正在 127.0.0.1 监听端口 1337
> 客户端已连接
> 收到:整理器消息:114、99、193、23、71、139、48、221、208、160、177、63、186、157、188、76、188、83、85、24、2、10、53、8、21、150、189

**参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/TLS . html # TLS _ tlssocket _ getpeerffinished](https://nodejs.org/dist/latest-v12.x/docs/api/tls.html#tls_tlssocket_getpeerfinished)