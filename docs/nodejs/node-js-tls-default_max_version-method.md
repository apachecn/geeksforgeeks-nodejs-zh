# Node.js tls。DEFAULT_MAX_VERSION 方法

> 原文:[https://www . geesforgeks . org/node-js-TLS-default _ max _ version-method/](https://www.geeksforgeeks.org/node-js-tls-default_max_version-method/)

**tls。DEFAULT_MAX_VERSION** 是 tls 模块内 TLS 类的内置应用编程接口，用于返回 tls.createSecureContext()的 maxVersion 选项的默认值。

**语法:**

```js
const tls.DEFAULT_MAX_VERSION

```

**参数:**此方法不接受任何参数。

**返回值:**此方法返回 tls.createSecureContext()的 maxVersion 选项的默认值。

**如何生成私钥和公钥证书？**

1.  **Private key:** Open notepad and copy paste the following key:

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

    现在将文件保存为*私钥. pem*

2.  **公共证书:**打开记事本复制粘贴以下密钥:

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

    现在将文件保存为*公钥. pem*

**示例 1:** **文件名:index.js**

```js
// Node.js program to demonstrate the
// tls.DEFAULT_MAX_VERSION method

var tls = require('tls'),
    fs = require('fs'),

    // Port and host address for server    
    PORT = 1337,
    HOST = '127.0.0.1',
    value = null;

// Private key and public certificate
// for access
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

// Start listening on a specific port and
// address by using listen() method
server.listen(PORT, HOST, function () {
    console.log("I'm listening at %s, on "
        + "port %s", HOST, PORT);
});

// Creating and initializing client
var client = tls.connect(PORT, HOST,
    options, function () {

        // Getting max version by using
        // tls.DEFAULT_MAX_VERSION method
        value = tls.DEFAULT_MAX_VERSION;

        client.write(" max version : " + value);

        client.end(() => {
            console.log("Client closed successfully");
        });
    });
```

使用以下命令运行 index.js 文件:

```js
node index.js

```

**输出:**

```js
I'm listening at 127.0.0.1, on port 1337
Client closed successfully

Received:  max version : TLSv1.3
Server closed successfully

```

**示例 2:** **文件名:**

```js
// Node.js program to demonstrate the
// tls.DEFAULT_MAX_VERSION method

var tls = require('tls'),
    fs = require('fs'),

    // Port and host address for server    
    PORT = 1337,
    HOST = '127.0.0.1';

// Private key and public certificate
// for access
var options = {
    key: fs.readFileSync('private-key.pem'),
    cert: fs.readFileSync('public-cert.pem'),
    rejectUnauthorized: false
};

// Creating and initializing server
var server = tls.createServer(options,
    function (socket) {

        // Getting max version by using
        // tls.DEFAULT_MAX_VERSION method
        value = tls.DEFAULT_MAX_VERSION;

        socket.write(" max version : " + value);

        // Stopping the server
        // by using the close() method
        server.close(() => {
            console.log("Server closed successfully")
        });
    });

// Start listening on a specific port and address
// by using listen() method
server.listen(PORT, HOST, function () {
    console.log(
        "I'm listening at %s, on port %s",
        HOST, PORT);
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

```js
node index.js

```

**输出:**

```js
I'm listening at 127.0.0.1, on port 1337
client is connected
Received:  max version : TLSv1.3
client closed successfully
Server closed successfully

```

**参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/TLS . html # TLS _ TLS _ default _ max _ version](https://nodejs.org/dist/latest-v12.x/docs/api/tls.html#tls_tls_default_max_version)