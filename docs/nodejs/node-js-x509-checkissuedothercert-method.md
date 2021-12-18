# node . js x509 . check issued(other cert)方法

> 原文:[https://www . geesforgeks . org/node-js-x509-checkissuedothercert-method/](https://www.geeksforgeeks.org/node-js-x509-checkissuedothercert-method/)

**x509.checkIssued()** 是加密模块中 x509 证书类的内置应用编程接口，用于检查该 PEM 编码的 X509 证书是否由其他证书颁发。

**语法:**

```js
const x509.checkIssued(otherCert)
```

**参数:**该方法以 PEM 编码的 X509 证书为自变量。

**返回值:**当且仅当此证书由其他证书颁发时，此方法返回布尔值 true。

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

**文件名:index . js**

## 【JavaScript】

```js
// Node.js program to demonstrate the 
// x509.checkIP() APi

// Importing crypto module
const {X509Certificate} = require('crypto')

// Importing fs module
const fs = require('fs')

// getting object of a PEM encoded X509 Certificate.
const x509 = new X509Certificate(fs.readFileSync('public-cert.pem'));

const x5091 = new X509Certificate(fs.readFileSync('public-cert.pem'));

// checking if passed ip address matches with the given one or not
// by using x509.checkIP() api
const value = x509.checkIssued(x5091)

// display the result
if(value)
  console.log("certificate is issued from other certificate")
else
  console.log("certificate is not issued from other certificate")
```

使用以下命令运行 index.js 文件。

```js
node index.js
```

**输出:**

```js
certificate is issued from other certificate
```

**例 2:**

**文件名:index . js**

## 【JavaScript】

```js
// Node.js program to demonstrate the 
// x509.checkIP() APi

// Importing crypto module
const {X509Certificate} = require('crypto')

// Importing fs module
const fs = require('fs')

// display the result
if((new X509Certificate(fs.readFileSync('public-cert.pem')))
    .checkIssued(new X509Certificate(fs.readFileSync('public-cert.pem'))))
  console.log("certificate is issued from other certificate")
else
  console.log("certificate is not issued from other certificate")
```

使用以下命令运行 index.js 文件。

```js
node index.js
```

**输出:**

```js
certificate is issued from other certificate
```

**参考:**[**https://nodejs . org/dist/latest-v 15 . x/docs/API/crypto . html # crypto _ x509 _ check issued _ other cert**](https://nodejs.org/dist/latest-v15.x/docs/api/crypto.html#crypto_x509_checkissued_othercert)