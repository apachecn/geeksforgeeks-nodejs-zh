# node . js diffihellman . getprivatekey()方法

> 原文:[https://www . geesforgeks . org/node-js-diffihellman-getprivate key-method/](https://www.geeksforgeeks.org/node-js-diffiehellman-getprivatekey-method/)

**DiffieHellman . GetPrivateKey()**方法是加密模块中类 **DiffieHellman** 的内置应用编程接口，用于返回 *dh* 对象的*私钥*。

**语法:**

```js
diffieHellman.getPrivateKey([encoding])
```

**参数:**该方法以编码为参数。

**返回值:**返回 diffieHellman 私钥。如果指定了编码，则返回字符串，否则返回缓冲区。

**例 1:**

## index . js

```js
// Node.js program to demonstrate the
// diffieHellman.getPrivateKey() Method

const crypto = require( 'crypto' )

// Instance of  diffieHellman class
const dh = crypto.createDiffieHellman( 512 );

// Generate Keys
dh.generateKeys()

// Without encoding, return Buffer
let privateKey = dh.getPrivateKey()
let isBuffer = Buffer.isBuffer( privateKey )

console.log( 'Private Key : ', privateKey )
console.log( 'Return value is Buffer :', isBuffer )
```

使用以下命令运行**文件:**

```js
**node index.js**
```

****输出:****

```js
**Private Key :  <Buffer 4b 6a b1 c8 85 0e 94 dd d9 32 9d 59 a9 31 55 
b0 56 1c b2 6c 6d 37 90 17 15 72 4a a8 f4 01 45 7c 6f 27 2f 47 9d 
6d 5f c9 a6 e0 bb e7 0d 33 84 44 13 12 ... 14 more bytes>
Return value is Buffer : true**
```

****例 2:****

## **index . js**

```js
**// Node.js program to demonstrate the
// diffieHellman.getPrivateKey() Method

const crypto = require( 'crypto' )

// Instance of  diffieHellman class
const dh = crypto.createDiffieHellman( 512 );

// Generate Keys
dh.generateKeys()

// Pass 'base64' as encoding, return String
let privateKey = dh.getPrivateKey( 'base64' )

console.log( 'Private Key : ', privateKey )
console.log( 'Return value is :', typeof privateKey )**
```

**使用以下命令运行**文件:****

```js
***node index.js***
```

*****输出:*****

```js
***Private Key :  fG5wx60xqnulSgUaRM3J2IsBrtWN5ySbrph8mdzakZ/bMTfG+K
SY1P58sENdPjBbmoXHGy7RAfwFPa0kHHgslA==
Return value is : string***
```

*****参考:**[https://nodejs . org/API/crypto . html # crypt _ differently man _ get rivtekey _ encoding](https://nodejs.org/api/crypto.html#crypto_diffiehellman_getprivatekey_encoding)***