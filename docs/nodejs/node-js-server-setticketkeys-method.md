# node . js server . settickeys()方法

> 原文:[https://www . geesforgeks . org/node-js-server-settickets-method/](https://www.geeksforgeeks.org/node-js-server-setticketkeys-method/)

**server . settickeys(keys)**是 tls 模块内 Socket 类的内置应用编程接口，用于设置包含会话票证密钥的 48 字节缓冲区。

**语法:**

```js
server.setTicketKeys(keys)

```

**参数:**该方法接受包含会话票证密钥的 48 字节缓冲区作为参数。

**返回值**:这个方法没有什么可返回的。

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

    将文件保存为*私钥*

2.  **Public certificate:** Open notepad and copy paste the following key:

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

    将文件保存为*公共证书*

**示例 1:** **文件名:index.js**

```js
// Node.js program to demonstrate the
// server.close() method

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

    // Print the data that we received
    socket.on('data', function (data) {
        console.log('\nReceived: %s ',
            data.toString().replace(/(\n)/gm, ""));
    });

    // Stopping the server
    // by using the close() method
    server.close();

});

// Getting session key 
// by using getTicketKeys() method
var value1 = server.getTicketKeys();
console.log("old Session key  : ")
console.log(value1)

var buf = Buffer.from([
    0x00, 0x00, 0x00, 0x00, 0xff, 0xff, 0xff, 0xff,
    0x00, 0x00, 0x00, 0x00, 0xff, 0xff, 0xff, 0xff,
    0x00, 0x00, 0x00, 0x00, 0xff, 0xff, 0xff, 0xff,
    0x00, 0x00, 0x00, 0x00, 0xff, 0xff, 0xff, 0xff,
    0x00, 0x00, 0x00, 0x00, 0xff, 0xff, 0xff, 0xff,
    0x00, 0x00, 0x00, 0x00, 0xff, 0xff, 0xff, 0xff,]);

// Setting up the new session key
// by using setTicketKeys() method
server.setTicketKeys(buf)

// Getting session key 
// by using getTicketKeys() method
var value1 = server.getTicketKeys();
console.log("new Session key  : ")
console.log(value1)

// Close event
server.on('close', () => {
    console.log("Server closed successfully");
})

// Start listening on a specific port and address
server.listen(PORT, HOST, function () {
    console.log("I'm listening at %s, "
            + "on port %s", HOST, PORT);
});

// Creating and initializing client
var client = tls.connect(PORT, 
        HOST, options, function () {

    // Getting the bound address 
    // by using address method
    const value = client.address();
    client.write("Bound address : " + value)

    client.end();
});
```

**输出:**

> 旧会话密钥:
> 缓冲区 5a b5 7a 5e d4f 0 2993 f6dd 2 E1 d37c B9 302a 7a 7e 09 178c 32 0e d0 B2 d6d FD ed 40c 1 ab D1 20a 57d e 4f 4a 44 4554 b FD cf FD 99>新会话密钥:
> 
> 收到:绑定地址:[对象对象]
> 服务器成功关闭

**示例 2:** **文件名:index.js**

```js
// Node.js program to demonstrate the
// server.close() method

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
var server = tls.createServer(options, 
                    function (socket) {

    // Print the data that we received
    socket.on('data', function (data) {
        console.log('\nReceived: %s ',
            data.toString());
    });

    // Stopping the server
    // by using the close() method
    server.close();
});

var buf = Buffer.from([
    0x11, 0x00, 0x00, 0x00, 0xff, 0xff, 0xff, 0xff,
    0x00, 0x00, 0x00, 0x00, 0xff, 0xff, 0xff, 0xff,
    0x00, 0x00, 0x00, 0x00, 0xff, 0xff, 0xff, 0xff,
    0x00, 0x00, 0x00, 0x00, 0xff, 0xff, 0xff, 0xff,
    0x00, 0x00, 0x00, 0x00, 0xff, 0xff, 0xff, 0xff,
    0x00, 0x00, 0x00, 0x00, 0xff, 0xff, 0xff, 0xff,]);

// Setting up the new session key
// by using setTicketKeys() method
server.setTicketKeys(buf)

// Getting session key 
// by using getTicketKeys() method
var value = server.getTicketKeys();

// Start listening on a specific port and address
server.listen(PORT, HOST, function () {
    console.log("I'm listening at %s, "
            + "on port %s", HOST, PORT);
});

// Creating and initializing client
var client = tls.connect(PORT, 
        HOST, options, function () {
    client.write("Session key : " + value[0])
    client.end();
});
```

使用以下命令运行 index.js 文件:

```js
node index.js

```

**输出:**

```js
I'm listening at 127.0.0.1, on port 1337

Received: Session key : 17

```

**参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/TLS . html # TLS _ server _ settickeys _ keys](https://nodejs.org/dist/latest-v12.x/docs/api/tls.html#tls_server_setticketkeys_keys)