# Node.js x509.raw 属性

> 原文:[https://www.geeksforgeeks.org/node-js-x509-raw-property/](https://www.geeksforgeeks.org/node-js-x509-raw-property/)

**x509.raw** 是加密模块中 x509 类证书的内置应用程序编程接口，用于获取包含该证书的 DER 编码的缓冲区。

**语法:**

```js
const x509.raw
```

**参数:**该属性不接受任何参数作为参数。

**返回值:**该属性返回一个包含该证书的 DER 编码的 Buffer。

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

**例:**

## js

```js
// Node.js program to demonstrate the  
// x509.raw APi

// Importing crypto module
const {X509Certificate} = require('crypto')

// Importing fs module
const fs = require('fs')

// Getting object of a PEM encoded X509 Certificate. 
const x509 = new X509Certificate(fs.readFileSync('public-cert.pem'));

// Getting raw included in this certificate.
// by using x509.raw api
const value = x509.raw

// Display the result
console.log(value)
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
<Buffer 30 82 02 7f 30 82 01 e8 02 09 00 f1 c5 e5
f0 f7 5e 18 d8 30 0d 06 09 2a 86 48 86 f7 0d 01 01 0b 05 
00 30 81 83 31 0b 30 09 06 03 55 04 06 13 02 49 4e ...
 593 more bytes>
```

**例 2:**

## index . js

```js
// Node.js program to demonstrate the  
// x509.raw APi

// Importing crypto module
const {X509Certificate} = require('crypto')

// Importing fs module
const fs = require('fs')

// Display the result
console.log((new X509Certificate(
  fs.readFileSync('public-cert.pem'))).raw)
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
<Buffer 30 82 02 7f 30 82 01 e8 02 09 00 f1 c5
e5 f0 f7 5e 18 d8 30 0d 06 09 2a 86 48 86 f7 0d 01 01 
0b 05 00 30 81 83 31 0b 30 09 06 03 55 04 06 13 02 49 4e
 ... 593 more bytes>
```

**参考:**[https://nodejs . org/dist/latest-v 15 . x/docs/API/crypto . html # crypto _ x509 _ raw](https://nodejs.org/dist/latest-v15.x/docs/api/crypto.html#crypto_x509_raw)