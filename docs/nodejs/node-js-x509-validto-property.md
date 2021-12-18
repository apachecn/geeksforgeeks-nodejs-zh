# Node.js x509.validTo 属性

> 原文:[https://www . geesforgeks . org/node-js-x509-valid to-property/](https://www.geeksforgeeks.org/node-js-x509-validto-property/)

**x509 . validato**是加密模块中 x509 类证书的内置应用程序编程接口，用于获取该证书被视为有效的日期/时间。

**语法:**

```
const x509.validTo
```

**参数**:此函数不接受任何参数作为参数。

**返回值**:该函数返回该证书被认为有效的日期/时间。

**如何生成公共证书？**

**公共证书:**打开记事本复制粘贴以下密钥，将文件保存为 ***公共证书 pem***

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
// x509.validTo function

// Importing crypto module
const {X509Certificate} = require('crypto')

// Importing fs module
const fs = require('fs')

// getting object of a PEM encoded X509 Certificate. 
const x509 = new X509Certificate(fs.readFileSync('public-cert.pem'));

// getting date of expiry of this certificate.
// by using x509.validTo function
const value = x509.validTo

// display the result
console.log( value)
```

使用以下命令运行 index.js 文件。

```
node index.js
```

**输出:**

```
Oct  9 05:51:17 2020 GMT
```

**例 2:**

## index . js

```
// Node.js program to demonstrate the  
// x509.validTo function

// Importing crypto module
const {X509Certificate} = require('crypto')

// Importing fs module
const fs = require('fs')

// display the result
console.log((new X509Certificate
            (fs.readFileSync('public-cert.pem'))).validTo)
```

使用以下命令运行 index.js 文件。

```
node index.js
```

**输出:**

```
Oct  9 05:51:17 2020 GMT
```

**参考:**[https://nodejs . org/dist/latest-v 15 . x/docs/API/crypto . html # crypto _ x509 _ validato](https://nodejs.org/dist/latest-v15.x/docs/api/crypto.html#crypto_x509_validto)