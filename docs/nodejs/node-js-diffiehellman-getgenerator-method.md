# node . js diffihellman . getgenerator()方法

> 原文:[https://www . geesforgeks . org/node-js-diffihellman-get generator-method/](https://www.geeksforgeeks.org/node-js-diffiehellman-getgenerator-method/)

**DiffieHellman . GetGenerator()**方法是加密模块中类 **diffieHellman** 的内置应用编程接口，用于获取 DiffieHellman (dh)对象的生成器值。

**语法:**

```js
diffieHellman.getGenerator([encoding])
```

**参数:**该方法以编码为参数。

**返回值:**返回指定编码的 DiffieHellman 生成器值。如果不返回缓冲区提供的编码，则返回字符串。

**例 1:**

## index . js

```js
// Node.js program to demonstrate the
// diffieHellman.getGenerator() method

// Destructure createDiffieHellman method from crypto
const { createDiffieHellman } = require('crypto');

// Instances of the DiffieHellman class
const dh = createDiffieHellman(512);

// Generate dh's Generator

// No encoding specified
// Return Buffer
let dhGenerator = dh.getGenerator()
console.log('\nIs Buffer return ( encoding not specified ) : ' +
    Buffer.isBuffer(dhGenerator)) // true
console.log('Return value :')
console.log(dhGenerator)

// Encoding specified 
// Return String
dhGenerator = dh.getGenerator('base64')
console.log('\nIs Buffer return ( encoding specified ): ' +
    Buffer.isBuffer(dhGenerator)) // true
console.log('Return value :')
console.log(dhGenerator)
```

使用以下命令运行 *index.js* 文件:

```js
node index.js
```

**输出:**

```js
Is Buffer return ( encoding not specified ) : true
Return value :
<Buffer 02>

Is Buffer return ( encoding specified ): false
Return value :
Ag==
```

**例 2:**

## index . js

```js
// Node.js program to demonstrate the
// diffieHellman.getGenerator() method

// Destructure createDiffieHellman method from crypto
const { createDiffieHellman } = require('crypto');

// Generate Alice's keys...
const alice = createDiffieHellman(512);

// Generate Alices's Prime
const alicePrime = alice.getPrime();

// Generate Alice's Generator
const aliceGenerator =  alice.getGenerator()

// Generate Alice's Key
const aliceKey = alice.generateKeys();

// Generate Bob's keys...
const bob = createDiffieHellman( alicePrime, aliceGenerator );

// Generate Bobs's Prime
const bobPrime = bob.getPrime();

// Generate Bob's Generator
const bobGenerator =  bob.getGenerator()

// Generate Bob's Key
const bobKey = bob.generateKeys();

// Exchange and generate the secret...
const aliceSecret = alice.computeSecret(bobKey);
const bobSecret = bob.computeSecret(aliceKey);

let isSymmetric = aliceSecret.toString('hex') == bobSecret.toString('hex')

console.log( `Is Symmetric key generation 
              successful : ${ isSymmetric }` ); // true
```

使用以下命令运行 *index.js* 文件:

```js
node index.js
```

**输出:**

```js
Is Symmetric key generation successful : true
```

**参考:**[https://nodejs . org/API/crypto . html # crypto _ diffihellman _ getgenerator _ encoding](https://nodejs.org/api/crypto.html#crypto_diffiehellman_getgenerator_encoding)