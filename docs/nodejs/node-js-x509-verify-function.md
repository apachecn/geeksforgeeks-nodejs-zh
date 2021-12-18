# Node.js x509.verify()函数

> 原文:[https://www.geeksforgeeks.org/node-js-x509-verify-function/](https://www.geeksforgeeks.org/node-js-x509-verify-function/)

**x509.verify()** 是加密模块中 x509 证书类的内置应用程序编程接口，用于检查证书是否由给定的公钥签名。

**语法:**

```js
const x509.verify(publicKey)
```

**参数**:该函数以公钥对象为参数。

**返回值:**当且仅当证书由给定的公钥签名时，该函数返回布尔值 true。

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

**文件名:index . js**

## 【JavaScript】

```js
// Node.js program to demonstrate the 
// x509.verify() function

// Importing crypto module
const {X509Certificate} = require('crypto')

// Importing fs module
const fs = require('fs')

// getting object of a PEM encoded X509 Certificate.
const x509 = new X509Certificate(fs.readFileSync('public-cert.pem'));

// checking if this certificate is signed by the given public key or not
// by using x509.verify() function
const value = x509.verify(x509.publicKey)

// display the result
if(value)
console.log("certificate is signed by the given public key")
else
console.log("certificate is not signed by the given public key")
```

使用以下命令运行 index.js 文件。

```js
node index.js
```

**输出:**

```js
certificate is signed by the given public key
```

**例 2:**

**文件名:index . js**

## 【JavaScript】

```js
// Node.js program to demonstrate the 
// x509.verify() function

// Importing crypto module
const {X509Certificate} = require('crypto')

// Importing fs module
const fs = require('fs')

// display the result
if((new X509Certificate(fs.readFileSync('public-cert.pem')))
    .verify((new X509Certificate(fs.readFileSync('public-cert.pem'))).publicKey))
console.log("certificate is signed by the given public key")
else
console.log("certificate is not signed by the given public key")
```

使用以下命令运行 index.js 文件。

```js
node index.js
```

**输出:**

```js
certificate is signed by the given public key
```

**参考**:[https://nodejs . org/dist/latest-v15 . x/docs/API/crypt . html # crypt _ x509 _ public keys](https://nodejs.org/dist/latest-v15.x/docs/api/crypto.html#crypto_x509_publickey)