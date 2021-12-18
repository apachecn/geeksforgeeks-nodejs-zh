# node . js diffihellman . getprime()方法

> 原文:[https://www . geesforgeks . org/node-js-diffihellman-get prime-method/](https://www.geeksforgeeks.org/node-js-diffiehellman-getprime-method/)

**diffieHellman.getPrime()** 方法是加密模块中类 **diffieHellman** 的内置应用程序编程接口，用于获取 DiffieHellman (dh)对象的素数。

**语法:**

```
diffieHellman.getPrime([encoding])
```

**参数:**该方法以编码为参数。

**返回值:**返回指定编码的 DiffieHellman 质数。如果不提供编码，则返回缓冲区，否则返回字符串。

**例 1:**

## index . js

```
// Node.js program to demonstrate the
// diffieHellman.getPrime() method

// Destructure createDiffieHellman method from crypto
const { createDiffieHellman } = require('crypto');

// Instances of the DiffieHellman class
const dh = createDiffieHellman(512);

// Generate dh's Prime

// No encoding specified
// Return Buffer
let dhPrime = dh.getPrime()
console.log('\nIs Buffer return ( encoding not specified ) : ' +
    Buffer.isBuffer(dhPrime)) // true
console.log('Return value :')
console.log(dhPrime)

// Encoding specified 
// Return String
dhPrime = dh.getPrime('base64')
console.log('\nIs Buffer return ( encoding specified ): ' +
    Buffer.isBuffer(dhPrime)) // true
console.log('Return value :')
console.log(dhPrime)
```

使用以下命令运行 *index.js* 文件:

```
node index.js
```

**输出:**

```
Is Buffer return ( encoding not specified ) : true
Return value :
<Buffer d9 10 5a 20 70 0e 9c 19 53 1d 74 bc 93 ac 9e 1d 00 65 cb 2b 7f 
13 fd b5 67 cd ba 42 69 fc 2c 4c 44 5c 72 a7 45 26 2d d7 ff 2e 
ee c1 a9 ad 21 bf c4 3a ... 14 more bytes>

Is Buffer return ( encoding specified ): false
Return value :
2RBaIHAOnBlTHXS8k6yeHQBlyyt/E/21Z826Qmn8LExEXHKnRSYt1/
8u7sGprSG/xDqF/zTVe5r9vQ+O0Q5PAw==
```

**例 2:**

## index . js

```
// Node.js program to demonstrate the
// diffieHellman.getPrime() method

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

let isSymmetric = 
    aliceSecret.toString('hex') == bobSecret.toString('hex')

console.log( `Is Symmetric key generation 
    successful : ${ isSymmetric }` ); // true
```

使用以下命令运行 *index.js* 文件:

```
node index.js
```

**输出:**

```
Is Symmetric key generation successful : true
```

**参考:**[https://nodejs . org/API/crypto . html # crypto _ differently _ get rime _ encoding](https://nodejs.org/api/crypto.html#crypto_diffiehellman_getprime_encoding)