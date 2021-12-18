# node . js x509 . issuer certificate Property

> 原文:[https://www . geesforgeks . org/node-js-x509-issuercertificate-property/](https://www.geeksforgeeks.org/node-js-x509-issuercertificate-property/)

**x509.issuerCertificate** 是加密模块中 X509Certificate 类的内置应用程序编程接口，用于获取颁发者证书，如果颁发者证书不可用，则为未定义。

**语法:**

```
const x509.issuerCertificate
```

**参数:**该属性不接受任何参数作为参数。

**返回值:**该属性返回发行者证书，如果发行者证书不可用，则返回未定义。

**如何生成公共证书？**

**公共证书**打开记事本，复制粘贴以下密钥，将文件保存为 ***公共证书***

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

**例 1:**

## index . js

```
// Node.js program to demonstrate the  
// x509.issuerCertificate function

// Importing crypto module
const {X509Certificate} = require('crypto')

// Importing fs module
const fs = require('fs')

// getting object of a PEM encoded X509 Certificate. 
const x509 = new X509Certificate(fs.readFileSync('public-cert.pem'));

// getting issuerCertificate included in this certificate.
// by using x509.issuerCertificate function
const value = x509.issuerCertificate

// display the result
console.log("issuerCertificate :- " + value)
```

使用以下命令运行 index.js 文件。

```
node index.js
```

**输出:**

```
issuerCertificate :- undefined
```

**例 2:**

## index . js

```
// Node.js program to demonstrate the  
// x509.issuerCertificate function

// Importing crypto module
const {X509Certificate} = require('crypto')

// Importing fs module
const fs = require('fs')

// display the result
console.log("issuerCertificate :- " + (new X509Certificate(
             fs.readFileSync('public-cert.pem'))).issuerCertificate)
```

使用以下命令运行 index.js 文件。

```
node index.js
```

**输出:**

```
issuerCertificate :- undefined
```

**参考:**[https://nodejs . org/dist/latest-v 15 . x/docs/API/crypto . html # crypto _ x509 _ issuer certificate](https://nodejs.org/dist/latest-v15.x/docs/api/crypto.html#crypto_x509_issuercertificate)