# Node.js x509.checkHost(名称[，选项])方法

> 原文:[https://www . geesforgeks . org/node-js-x509-check hostname-options-method/](https://www.geeksforgeeks.org/node-js-x509-checkhostname-options-method/)

**x509.checkHost()** 是加密模块中 x509 证书类的内置应用程序编程接口，用于检查该 PEM 编码的 X509 证书是否与给定的主机名匹配。

**语法:**

```js
const x509.checkHost(name[, options])
```

**参数**:该方法以下列参数为参数。

*   **名称:**保存主机名称。
*   **选项:**将影响该 api 操作的任何选项。

**返回值:**如果与证书主机名匹配，则该方法返回名称，否则返回未定义。

**如何生成公共证书？**

**公共证书**打开记事本，复制粘贴以下密钥，将文件保存为 ***公共证书 pem***

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

## index.js

```js
// Node.js program to demonstrate the  
// x509.checkHost() APi

// Importing crypto module
const {X509Certificate} = require('crypto')

// Importing fs module
const fs = require('fs')

// getting object of a PEM encoded X509 Certificate. 
const x509 = new X509Certificate(fs.readFileSync('public-cert.pem'));

// checking if passed host name matches with the given one or not
// by using x509.checkHost() api
const value = x509.checkHost("ROHIT PRASAD")

// display the result
if(value)
  console.log("host name matched")
else
  console.log("host name did't match")
```

```js
node index.js
```

**输出:**

```js
host name matched
```

**例 2:**

## index.js

```js
// Node.js program to demonstrate the  
// x509.checkHost() APi

// Importing crypto module
const {X509Certificate} = require('crypto')

// Importing fs module
const fs = require('fs')

// display the result
if((new X509Certificate(fs.readFileSync('public-cert.pem'))).checkHost("ROHITPRASAD"))
  console.log("host name matched")
else
  console.log("host name did't match")
```

使用以下命令运行 index.js 文件:

```js
node index.js
```

**输出:**

```js
host name did't match
```

**参考**:[https://nodejs . org/dist/latest-v 15 . x/docs/API/crypto . html # crypto _ x509 _ checkhost _ name _ options](https://nodejs.org/dist/latest-v15.x/docs/api/crypto.html#crypto_x509_checkhost_name_options)