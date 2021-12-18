# node . js x509 . check email(email[，options])方法

> 原文:[https://www . geesforgeks . org/node-js-x509-check email-options-method/](https://www.geeksforgeeks.org/node-js-x509-checkemailemail-options-method/)

**x509.checkEmail()** 是加密模块中 x509 证书类的内置应用程序编程接口，用于检查该 PEM 编码的 X509 证书是否与给定的电子邮件地址匹配。

**语法:**

```
x509.checkEmail(email[, options])
```

**参数:**该方法采用以下参数作为参数。

*   **E-mail:** A string for saving mail.
*   **Option:** Any option that will affect the operation of this api.

**返回值:**如果与证书电子邮件匹配，则该 api 返回电子邮件字符串，否则将返回未定义。

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
// x509.checkEmail() APi

// Importing crypto module
const {X509Certificate} = require('crypto')

// Importing fs module
const fs = require('fs')

// getting object of a PEM encoded X509 Certificate. 
const x509 = new X509Certificate(fs.readFileSync('public-cert.pem'));

// checking if passed email matches with the given one or not
// by using x509.checkEmail() api
const value = x509.checkEmail("rprrprp@gmail.com")

// display the result
if(value)
  console.log("email matched")
else
  console.log("email did't match")
```

使用以下命令运行 index.js 文件。

```
node index.js
```

**输出:**

```
email did't match
```

**例 2:**

## index . js

```
// Node.js program to demonstrate the  
// x509.checkEmail() APi

// Importing crypto module
const {X509Certificate} = require('crypto')

// Importing fs module
const fs = require('fs')

// display the result
if((new X509Certificate(fs.readFileSync('public-cert.pem'))).checkEmail("rofofof@gmail.com"))
  console.log("email matched")
else
  console.log("email did't match")
```

使用以下命令运行 index.js 文件。

```
node index.js
```

**输出:**

```
email matched
```

**参考:**[https://nodejs . org/dist/latest-v 15 . x/docs/API/crypto . html # crypto _ x509 _ check email _ email _ options](https://nodejs.org/dist/latest-v15.x/docs/api/crypto.html#crypto_x509_checkemail_email_options)