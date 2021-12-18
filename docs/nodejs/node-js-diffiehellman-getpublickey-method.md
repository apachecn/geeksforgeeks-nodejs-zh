# node . js diffihellman . getpublickey()方法

> 原文:[https://www . geesforgeks . org/node-js-diffihellman-getpublic key-method/](https://www.geeksforgeeks.org/node-js-diffiehellman-getpublickey-method/)

**DiffieHellman . GetPublicKey()**方法是加密模块中类 **DiffieHellman** 的内置应用编程接口，用于返回 *dh* 对象的*公钥*。

**语法:**

```js
diffieHellman.getPublicKey([encoding])
```

**参数:**该方法以*编码*为参数。

**返回值:**返回 diffieHellman 公钥。如果指定了*编码*，则返回一个字符串，否则返回一个缓冲区。

**例 1:**

## index . js

```js
// Node.js program to demonstrate the
// diffieHellman.getPublicKey() Method

const crypto = require('crypto')
// Instance of  diffieHellman class
const dh = crypto.createDiffieHellman(512);
let publicKey = null

// Generate Keys
dh.generateKeys()

// Pass 'base64' as encoding, return String
publicKey = dh.getPublicKey('base64')
console.log('Public Key ( with encoding ): ', publicKey, '\n')

// Without encoding, return Buffer
publicKey = dh.getPublicKey()
console.log('Public Key ( without encoding ): ', publicKey, '\n')
```

使用以下命令运行**文件:**

```js
**node index.js**
```

****输出:****

```js
**Public Key ( with encoding ):  m/tuBRWr1mHOT4VzjRvcgZ+9Vtp925GS78Mdu
E7DfTxAm5750700EbWzVgLZWZ8N0AQoN1xQLlgDtBsdDo1wnQ== 

Public Key ( without encoding ):  <Buffer 9b fb 6e 05 15 ab d6 61 ce 
4f 85 73 8d 1b dc 81 9f bd 56 da 7d db 91 92 ef c3 1d b8 4e c3 7d 
3c 40 9b 9e f9 d3 bd 34 11 b5 b3 56 02 d9 59 9f 0d d0 04 ... >**
```

****例 2:****

## **index . js**

```js
**// Node.js program to demonstrate the
// diffieHellman.getPublicKey() Method

const crypto = require('crypto')

// Instances of diffieHellman class
const alice = crypto.createDiffieHellman(512);
const bob = crypto.createDiffieHellman( 
    alice.getPrime(), alice.getGenerator() );

// Generate Keys
alice.generateKeys()
bob.generateKeys()

// Alice's publicKey
let aliceKey = alice.getPublicKey('base64')

// Bob's publicKey 
let bobKey = bob.getPublicKey('base64')

// Compute secret
let aliceSecret = alice.computeSecret(bobKey, 'base64', 'base64')
let bobSecret = bob.computeSecret(aliceKey, 'base64', 'base64')

if( aliceSecret === bobSecret )
    console.log('Symmetric key :', aliceSecret)**
```

**使用以下命令运行**文件:****

```js
***node index.js***
```

*****输出:*****

```js
***Symmetric key : VyeZOZm+hZQtZVp6HQdhWTkrHfZb8tR/yRiD99ljFWsnVHJNULdjnc
5oN5/mMSNqEWFqiJ0U14JYngJwXL008A==***
```

*****参考:**[https://nodejs . org/API/crypto . html # crypt _ differently llman _ get publicly _ encoding](https://nodejs.org/api/crypto.html#crypto_diffiehellman_getpublickey_encoding)***