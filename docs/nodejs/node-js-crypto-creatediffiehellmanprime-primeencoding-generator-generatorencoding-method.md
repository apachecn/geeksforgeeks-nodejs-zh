# node . js crypto . creatediffihellman(prime，primeEncoding，generatorEncoding，generator encoding)方法

> 原文:[https://www . geesforgeks . org/node-js-crypto-creatediffeiehellman prime-prime encoding-generator encoding-method/](https://www.geeksforgeeks.org/node-js-crypto-creatediffiehellmanprime-primeencoding-generator-generatorencoding-method/)

**crypto.createDiffieHellman()方法**用于通过使用所述质数和可选的指定生成器来创建 DiffieHellman 密钥交换对象。
**语法:**

```js
crypto.createDiffieHellman( prime, primeEncoding,
                        generator, generatorEncoding )
```

**参数:**该方法接受上述四个参数，描述如下:

*   **prime:** 它可以保存字符串、Buffer、TypedArray 或 DataView 类型的元素。
*   **质数编码:**是质数串的编码，为类型串。

*   **生成器:**它可以保存数字、字符串、缓冲区、类型数据或数据视图类型的数据。它的默认值是 2。
*   **generatorEncoding:** 是生成器字符串的编码，返回字符串。

**返回值:**返回*diffihellman*密钥交换对象。
以下示例说明了在 Node.js:
**示例 1:**
中使用**crypto . creatediffehellman()方法**

## java 描述语言

```js
// Node.js program to demonstrate the 
// crypto.createDiffieHellman() method

// Including crypto module
const crypto = require('crypto');

// Creating DiffieHellman with prime
const alice = crypto.createDiffieHellman(20);

// Generate keys
alice.generateKeys();

// Creating DiffieHellman to get
// prime and generator
const bob= crypto.createDiffieHellman(
      alice.getPrime(), alice.getGenerator());
bob.generateKeys();

// Prints prime and generator for
// Alice with encoding
console.log("Alice prime (p):",
    alice.getPrime().toString('hex'), 
    "\nAlice generator (G):", 
    alice.getGenerator().toString('hex')
);
```

**输出:**

```js
Alice prime (p): 0a134b
Alice generator (G): 02
```

**例 2:**

## java 描述语言

```js
// Node.js program to demonstrate the 
// crypto.createDiffieHellman() method

// Including crypto module
const crypto = require('crypto');

// Creating DiffieHellman with prime
const k = crypto.createDiffieHellman(30);

// Accessing prime value
const p = k.getPrime();

// Accessing generator value
const g = k.getGenerator();

// Prints prime value
console.log(p);

// Prints generator value
console.log(g);
```

**输出:**

```js
// Buffer 22 4a 58 5b
// Buffer 02
```

因此，素数和生成器都返回缓冲区。
**参考:**[https://nodejs . org/API/crypto . html # crypto _ crypto _ createdfiehellman _ prime _ prime encoding _ generator encoding](https://nodejs.org/api/crypto.html#crypto_crypto_creatediffiehellman_prime_primeencoding_generator_generatorencoding)