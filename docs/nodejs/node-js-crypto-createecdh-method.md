# Node.js crypto.createECDH()方法

> 原文:[https://www . geesforgeks . org/node-js-crypto-createecdh-method/](https://www.geeksforgeeks.org/node-js-crypto-createecdh-method/)

**crypto.createECDH()方法**是加密模块的内置应用编程接口，用于借助于由*曲线名称*字符串定义的预定义曲线来创建*椭圆曲线差分-赫尔曼*即(ECDH)密钥交换对象。此外，您可以使用 crypto.getCurves()方法来返回可用曲线名称的列表。

**语法:**

```js
crypto.createECDH( curveName )
```

**参数:**该方法接受单参数**曲线名称**，类型为字符串。

**返回值:**返回 *ECDH* 密钥交换对象。

下面的例子说明了 **crypto.createECDH()方法**在 Node.js 中的使用:

**例 1:**

```js
// Node.js program to demonstrate the 
// crypto.createECDH() method

// Including crypto module
const crypto = require('crypto');

// Creating ECDH with curve name
const curv = crypto.createECDH('secp521r1');

// Prints keys
console.log(curv.generateKeys());
```

**输出:**

```js
<Buffer 04 01 0a cd d0 94 80 31 e8 ... >

```

**例 2:**

```js
// Node.js program to demonstrate the 
// crypto.createECDH() method

// Including crypto module
const crypto = require('crypto');

// Creating ECDH with curve name
const curv = crypto.createECDH('secp521r1');
curv.generateKeys();

// Prints Public key
console.log("Public Key: ", curv.getPublicKey());

// Prints Private Key
console.log("Private Key :", curv.getPrivateKey());
```

**输出:**

```js
Public Key: <Buffer 04 01 68 25 14 c8 ... >
Private Key : <Buffer 01 7a ab 4d 71 60 ... >

```

**参考:**[https://nodejs . org/API/crypt . html # crypt _ crypt _ create ecdh _ curve name](https://nodejs.org/api/crypto.html#crypto_crypto_createecdh_curvename)