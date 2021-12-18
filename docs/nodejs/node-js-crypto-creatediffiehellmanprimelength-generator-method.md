# node . js crypto . creatediffihellman(prime length，生成器)方法

> 原文:[https://www . geesforgeks . org/node-js-crypto-creatediffeiehellman prime length-generator-method/](https://www.geeksforgeeks.org/node-js-crypto-creatediffiehellmanprimelength-generator-method/)

**crypto.createDiffieHellman()方法**用于创建 DiffieHellman 密钥交换对象。此外，在可选的特定数字生成器的帮助下，创建*素数*位的素数。此外，如果没有定义生成器，则使用值 2。

**语法:**

```
crypto.createDiffieHellman( primeLength, generator )
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **Prime number:** This parameter holds multiple prime numbers.
*   **Generator:** It can store numbers, strings, buffers, type data or data view type data. Its default value is 2.

**返回值:**返回 DiffieHellman 密钥交换对象。

以下示例说明了在 Node.js 中使用**crypto . creatediffihellman()方法**:

**例 1:**

```
// Node.js program to demonstrate the     
// crypto.createDiffieHellman() method

// Includes crypto module
const crypto = require('crypto');

// Defining prime length
var prime_length = 60;

// Creating DiffieHellman keyexchange object
var diffHell = crypto.createDiffieHellman(prime_length);

// Displays keys which are encoded
console.log(diffHell.generateKeys('base64'));
```

**输出:**

```
CoWIWpiwbCE=

```

**例 2:**

```
// Node.js program to demonstrate the     
// crypto.createDiffieHellman() method

// Includes crypto module
const crypto = require('crypto');

// Defining prime length and generator
var prime_length = 21;
var generator = 12;

// Creating DiffieHellman keyexchange
// object with all its parameter
var diffHell = crypto.createDiffieHellman(
               prime_length, generator);

// Displays keys which are encoded
console.log(diffHell.generateKeys('hex'));

// Displays public and private keys
console.log("Public Key : ",
      diffHell.getPublicKey('base64'));
console.log("Private Key : ",
      diffHell.getPrivateKey('base64'));
```

**输出:**

```
086501
Public Key :  CGUB
Private Key :  C1rL

```

**参考:**[https://nodejs . org/API/crypt . html # crypt _ crypt _ create diff llman _ primelistgth _ generator](https://nodejs.org/api/crypto.html#crypto_crypto_creatediffiehellman_primelength_generator)