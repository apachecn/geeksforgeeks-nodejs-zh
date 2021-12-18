# Node.js x509 .发卡行属性

> 原文:[https://www.geeksforgeeks.org/node-js-x509-issuer-property/](https://www.geeksforgeeks.org/node-js-x509-issuer-property/)

**x509 .发卡行**是加密模块中 x509 类证书的内置应用编程接口，用于获取该证书中包含的发卡行标识。

**语法:**

```js
const x509.issuer
```

**参数**:该属性不接受任何参数作为参数。

**返回值**:该属性返回本证书中包含的发行人标识。

**如何生成公共证书？**

**公共证书:**打开记事本复制粘贴以下密钥，将文件保存为 ***公共证书 pem***

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

**例 1:**

## index . js

```js
// Node.js program to demonstrate the  
// x509.issuer APi

// Importing crypto module
const {X509Certificate} = require('crypto')

// Importing fs module
const fs = require('fs')

// Getting object of a PEM encoded X509 Certificate. 
const x509 = new X509Certificate(fs.readFileSync('public-cert.pem'));

// Getting issuer identification included in this certificate.
// by using x509.issuer api
const value = x509.issuer

// Display the result
console.log("issuer :- " + value)
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
issuer :- C=IN
ST=Westbengal
L=Kolkata
O=Panco, Inc.
CN=Rohit Prasad
emailAddress=rofofof@gmail.com
```

**例 2:**

## index . js

```js
// Node.js program to demonstrate the  
// x509.issuer APi

// Importing crypto module
const {X509Certificate} = require('crypto')

// Importing fs module
const fs = require('fs')

// Display the result
console.log("issuer :- " + 
(new X509Certificate(fs.readFileSync('public-cert.pem'))).issuer)
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
issuer :- C=IN
ST=Westbengal
L=Kolkata
O=Panco, Inc.
CN=Rohit Prasad
emailAddress=rofofof@gmail.com
```

**参考**:[https://nodejs . org/dist/latest-v 15 . x/docs/API/crypto . html # crypto _ x509 _ 发卡行](https://nodejs.org/dist/latest-v15.x/docs/api/crypto.html#crypto_x509_issuer)