# Node.js x509 .指纹属性

> 原文:[https://www . geesforgeks . org/node-js-x509-指纹-property/](https://www.geeksforgeeks.org/node-js-x509-fingerprint-property/)

**x509 .指纹**是加密模块中 x509 类证书的内置应用编程接口，用于获取该证书的 SHA-1 指纹。

**语法:**

```js
const x509.fingerprint
```

**参数:**该属性不接受任何参数作为参数。

**返回值:**该属性返回该证书的 SHA-1 指纹。

**如何生成公共证书？**

**公共证书**打开记事本，复制粘贴以下密钥，将文件保存为 ***公共证书***

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
// x509.fingerprint function

// Importing crypto module
const {X509Certificate} = require('crypto')

// Importing fs module
const fs = require('fs')

// getting object of a PEM encoded X509 Certificate. 
const x509 = new X509Certificate(fs.readFileSync('public-cert.pem'));

// getting the SHA-1 fingerprint of this certificate.
// by using x509.fingerprint function
const value = x509.fingerprint

// display the result
console.log("SHA-1 fingerprint of this certificate :- " + value)
```

使用以下命令运行 index.js 文件。

```js
node index.js
```

**输出:**

```js
SHA-1 fingerprint of this certificate :- 
78:55:AE:43:DC:ED:2F:2D:31:EA:D5:17:1A:22:
D3:8A:35:76:66:0D
```

**示例 2:**

## index.js

```js
// Node.js program to demonstrate the  
// x509.fingerprint function

// Importing crypto module
const {X509Certificate} = require('crypto')

// Importing fs module
const fs = require('fs')

// display the result
console.log("SHA-1 fingerprint of this certificate :- " + 
           (new X509Certificate(fs.readFileSync('public-cert.pem')))
           .fingerprint)
```

使用以下命令运行 index . js 文件。

```js
node index.js
```

**输出:**

```js
SHA-1 fingerprint of this certificate :- 
78:55:AE:43:DC:ED:2F:2D:31:EA:D5:17:1A:22:D3:
8A:35:76:66:0D
```

**参考:**[https://nodejs . org/dist/latest-v 15 . x/docs/API/crypto . html # crypto _ x509 _ 指纹](https://nodejs.org/dist/latest-v15.x/docs/api/crypto.html#crypto_x509_fingerprint)