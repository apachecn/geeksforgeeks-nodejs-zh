# node . js diffihellman . computesecret()方法

> 原文:[https://www . geesforgeks . org/node-js-diffihellman-computesecret-method/](https://www.geeksforgeeks.org/node-js-diffiehellman-computesecret-method/)

**diffieHellman . computesecrete()**方法是加密模块内 DiffieHellman 类的内置应用编程接口，用于计算 DiffieHellman (dh)密钥。

**语法:**

```
diffieHellman.computeSecret(otherPublicKey[, 
        inputEncoding][, outputEncoding])
```

**参数:**该方法接受以下参数。

*   **Other public key:** This method takes the public key of the other party as the first parameter.
*   **Enter code:** Specify the code of *or* . If *other public key* is not provided, it should be buffer, type data area or data view.
*   **Output code:** If provided, the string will be returned; otherwise, the buffer will be returned.

**返回值:**此方法返回 diffieHellman 共享密钥。

**例 1:**

## index . js

```
// Node.js program to demonstrate the
// diffieHellman.computeSecret() method

const crypto = require('crypto')

// Instance of diffieHellman class...
const alice = crypto.createDiffieHellman(512);
const bob = crypto.createDiffieHellman(
        alice.getPrime(), alice.getGenerator());

// Generate otherPublicKey
// Pass 'base64' as encoding parameter
const aliceKey = alice.generateKeys('base64');
const bobKey = bob.generateKeys('base64');

// Exchange and generate the secret...
// inputEncoding = 'base64' because otherPublicKey
// is 'base64' encoded
// Return value should be 'hex' encoded because 
// outputEncoding = 'hex' 
const aliceSecret = alice.computeSecret(bobKey, 'base64', 'hex');
const bobSecret = bob.computeSecret(aliceKey, 'base64', 'hex');

if( aliceSecret === bobSecret ) 
    console.log(`Symmetric key : ${ aliceSecret }`)
```

使用以下命令运行**文件:**

```
**node index.js**
```

****输出:****

```
**Symmetric key : da884ccb0e24bf7e748f66998550b
f21f96b887e1f936478cdbc63b7806bd2403fd3aa28e5dbf58
bbabeb6f829dd86453eb0985b5ff593fcf7a8e1da20256b2a**
```

****例 2:** 再举一个不提供*输出编码的例子。***

## 

```
**// Node.js program to demonstrate the
// diffieHellman.computeSecret() method

const crypto = require('crypto')

// Instances of diffieHellman class
const alice = crypto.createDiffieHellman('modp15');
const bob = crypto.createDiffieHellman('modp15');

// Pass 'base64' as encoding parameter
const aliceKey = alice.generateKeys('base64');

// Pass 'hex' as encoding parameter
const bobKey = bob.generateKeys('hex');

// Pass inputEncoding = 'hex' because Bob's key 
// 'hex' encocded
// No outputEncoding provided
// Return Buffer 
const aliceSecret = alice.computeSecret(bobKey, 'hex');

// Pass inputEncoding = 'base64' because Alice's
// key 'base64' encocded 
// No outputEncoding provided
// Return Buffer
const bobSecret = bob.computeSecret(aliceKey, 'base64');

const isSymmetric = aliceSecret.equals(bobSecret)

if ( isSymmetric )
    console.log('Symmetric key : ', aliceSecret)**
```

**使用以下命令运行**文件:****

```
***node index.js***
```

*****输出:*****

```
***Symmetric key :  <Buffer 6d 1a 6c 00 34 6c>***
```

*****例 3:** 不提供*输入编码的另一个例子。*通过*输入编码*为**空**。***

****文件名:index . js****

## **【JavaScript】**

```
**// Node.js program to demonstrate the
// diffieHellman.computeSecret() method

const crypto = require('crypto')

// Instances of diffieHellman class
const alice = crypto.createDiffieHellman('modp15');
const bob = crypto.createDiffieHellman('modp15');

// Generate Key
alice.generateKeys();
bob.generateKeys();

// Compute Secret
// inputEncoding is null
// otherPublicKey expected to be Buffer 
const aliceSecret = alice.computeSecret(
        bob.getPublicKey() , null, 'base64');

const bobSecret = bob.computeSecret(
        alice.getPublicKey(), null, 'base64');

if (aliceSecret === bobSecret)
    console.log(`Symmetric key : ${ aliceSecret }`)**
```

**使用以下命令运行**文件:****

```
***node index.js***
```

*****输出:*****

```
***Symmetric key : abLoALX9***
```

*****参考:*****

***[https://nodejs . org/API/crypto . html # crypto _ diffihellman _ computesecret _ other public key _ input encoding _ output en coding](https://nodejs.org/api/crypto.html#crypto_diffiehellman_computesecret_otherpublickey_inputencoding_outputencoding)***