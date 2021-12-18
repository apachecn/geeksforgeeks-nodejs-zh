# Node.js 新增 X509Certificate()功能

> 原文:[https://www . geesforgeks . org/node-js-new-x509 certificate-function/](https://www.geeksforgeeks.org/node-js-new-x509certificate-function/)

**新的 X509 证书(缓冲区)**是加密模块中 X509 证书类的内置构造函数，用于提供 PEM 编码的 X509 证书。

**语法:**

```js
new X509Certificate(buffer)
```

**参数**:该函数取代表公共证书的字符串的缓冲区。

**返回值**:该函数返回 PEM 编码的 X509 证书的对象。

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
// new X509Certificate(buffer) constructor function

// Importing crypto module
const {X509Certificate} = require('crypto')

// Importing fs module
const fs = require('fs')

// getting object of a PEM encoded X509 Certificate. 
const x509 = new X509Certificate(fs.readFileSync('public-cert.pem'));

// getting subject included in this certificate.
// by using x509.subject function
const value = x509.subject

// display the result
console.log("subject :- " + value)
```

**使用以下命令运行 index.js 文件:**

```js
node index.js
```

**输出:**

```js
subject :- C=IN
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
// new X509Certificate(buffer) constructor function

// Importing crypto module
const {X509Certificate} = require('crypto')

// Importing fs module
const fs = require('fs')

// display the result
console.log((new X509Certificate(
             fs.readFileSync('public-cert.pem'))).subject)
```

**使用以下命令运行 index.js 文件:**

```js
node index.js
```

**输出:**

```js
C=IN
ST=Westbengal
L=Kolkata
O=Panco, Inc.
CN=Rohit Prasad
emailAddress=rofofof@gmail.com
```

**参考**:[https://nodejs . org/dist/latest-v 15 . x/docs/API/crypto . html # crypto _ new _ x509 certificate _ buffer](https://nodejs.org/dist/latest-v15.x/docs/api/crypto.html#crypto_new_x509certificate_buffer)