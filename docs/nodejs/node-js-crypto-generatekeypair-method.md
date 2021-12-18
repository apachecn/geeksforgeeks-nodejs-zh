# node . js crypto . generatekeypair()方法

> 原文:[https://www . geesforgeks . org/node-js-crypto-generatekeypair-method/](https://www.geeksforgeeks.org/node-js-crypto-generatekeypair-method/)

**crypto.generateKeyPair()方法**是加密模块的内置应用编程接口，用于生成指定类型的新非对称密钥对。例如，目前支持的密钥类型有 *RSA、DSA、EC、Ed25519、Ed448、X25519、X448、DH* 。此外，如果选项的*公共密钥编码*或*私有密钥编码*在此处被声明，则此函数的作用就像在其输出中调用了*密钥对象.导出()*一样。否则，密钥的特定部分作为*密钥对象*返回。
但建议将公钥编码为‘spki’，私钥编码为‘pkcs8’，加密后长期保存。

**语法:**

```js
crypto.generateKeyPair( type, options, callback )
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **类型:**它保存一个字符串，并且必须包含以下一个或多个算法:*‘RSA’‘DSA’‘EC’‘ed 25519’‘ed 448’‘x 25519’‘x448’或‘DH’*。
*   **选项:**属于对象类型。它可以保存以下参数:
    1.  **modulusLength:** 它保存一个数字。它是以位为单位的密钥大小，仅适用于 RSA 和 DSA 算法。
    2.  **public index:**它保存一个数字。它是 RSA 算法的公开指数。其默认值为 0x10001。
    3.  **除数长度:**它保存一个数字。这是数字减影算法中 *q* 的大小。
    4.  **namedCurve:** 它保存一个字符串。它是用于 EC 算法的曲线的名称。
    5.  **prime:** 它保存一个缓冲区。它是 DH 算法的首要参数。
    6.  **质数长度:**它保存一个数字。它是 DH 算法的质数长度，以位为单位。
    7.  **发生器:**它保存一个数字。是 DH 算法的自定义生成器。它的默认值是 2。
    8.  **groupName:** 保存字符串。是 DH 算法的 Diffie-Hellman 组名。
    9.  **publicKeyEncoding:** 它保存一个字符串。
    10.  **privateKeyEncoding:** 它保存一个对象。
*   **回调:**是一个函数，参数 *publicKey，privateKey，err* 。
    1.  **错误:**保存错误。
    2.  **公钥:**它保存字符串、缓冲区或密钥对象。
    3.  **privateKey:** 保存字符串、缓冲区或 KeyObject。

**返回值:**返回给定类型的新非对称密钥对。

下面的例子说明了 **crypto.generateKeyPair()方法**在 Node.js 中的使用:

**例 1:**

```js
// Node.js program to demonstrate the
// crypto.generateKeyPair() method

// Including generateKeyPair from crypto module
const { generateKeyPair } = require('crypto');

// Calling generateKeyPair() method
// with its parameters
generateKeyPair('rsa', {
  modulusLength: 530,    // options
  publicExponent: 0x10101,
  publicKeyEncoding: {
    type: 'pkcs1',
    format: 'der'
  },
  privateKeyEncoding: {
    type: 'pkcs8',
    format: 'der',
    cipher: 'aes-192-cbc',
    passphrase: 'GeeksforGeeks is a CS-Portal!'
  }
}, (err, publicKey, privateKey) => { // Callback function
       if(!err)
       {
         // Prints new asymmetric key pair
         console.log("Public Key is : ", publicKey);
         console.log();
         console.log("Private Key is: ", privateKey);
       }
       else
       {
         // Prints error
         console.log("Errr is: ", err);
       }

  });
```

**输出:**

```js
Public Key is : <Buffer 30 4a 02 43 03 12 b9
4c 1a 3f 96 07 51 c6 31 02d7 11 e2 e3 a5 2b 0c
7c 18 55 88 39 04 4c 86 e2 77 c4 29 47 82 2c 5b
4b 9e f3 e8 83 4b 5d 4b 31 e7 d5 ... >

Private Key is: <Buffer 30 82 01 cd 30 57 06
09 2a 86 48 86 f7 0d 01 050d 30 4a 30 29 06 09
2a 86 48 86 f7 0d 01 05 0c 30 1c 04 08 e0 31 2b
a0 38 82 e1 db 02 02 08 00 30 0c ... >

```

**例 2:**

```js
// Node.js program to demonstrate the
// crypto.generateKeyPair() method

// Including generateKeyPair from crypto module
const { generateKeyPair } = require('crypto');

// Calling generateKeyPair() method
// with its parameters
generateKeyPair('ec', {
  namedCurve: 'secp256k1',   // Options
  publicKeyEncoding: {
    type: 'spki',
    format: 'der'
  },
  privateKeyEncoding: {
    type: 'pkcs8',
    format: 'der'
  }
},
 (err, publicKey, privateKey) => { // Callback function
       if(!err)
       {
         // Prints new asymmetric key
         // pair after encoding
         console.log("Public Key is: ",
                  publicKey.toString('hex'));
         console.log();
         console.log("Private Key is: ",
                 privateKey.toString('hex'));
       }
       else
       {
         // Prints error
         console.log("Errr is: ", err);
       }

  });
```

**输出:**

```js
Public Key is:  3056301006072a8648ce3d020106052b8104000a0342000499c5f442c3264bcdfb093b0bc820e3f0f6546972856ebec2f8ccc03f49abdb47ffcfcaf4f37e0ec53050760e74014767e30a8a3e891f4db8c83fa27627898f15

Private Key is:  308184020100301006072a8648ce3d020106052b8104000a046d306b0201010420326b340a964512bfc3e010850ff05e077b2f016fce9eded11f40643e4231efc4a1440342000499c5f442c3264bcdfb093b0bc820e3f0f6546972856ebec2f8ccc03f49abdb47ffcfcaf4f37e0ec53050760e74014767e30a8a3e891f4db8c83fa27627898f15

```

**参考:**[https://nodejs . org/API/crypt . html # crypt _ crypt _ generate keypair _ type _ options _ callback](https://nodejs.org/api/crypto.html#crypto_crypto_generatekeypair_type_options_callback)