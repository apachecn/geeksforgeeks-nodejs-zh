# Node.js crypto.verify()函数

> 原文:[https://www . geesforgeks . org/node-js-crypto-verify-function/](https://www.geeksforgeeks.org/node-js-crypto-verify-function/)

**crypto.verify()** 是 node.js crypto 内置模块的一种方法，用于验证使用不同类型的散列函数(如 [SHA256 算法](https://www.geeksforgeeks.org/difference-between-sha1-and-sha256/)等)散列的数据的签名。

**语法:**

```
crypto.verify(algorithm, data, publicKey, signature)
```

**参数:**

*   **算法:**是字符串类型的值。签名可以通过应用签名算法的名称来验证，如“SHA256”。算法必须与创建签名的算法相同。
*   **数据:**数据参数必须是缓冲区、类型化数组或数据视图的实例。
*   **密钥:**应该是密钥对象的公钥。如果您没有任何公钥，那么您可以使用 [crypto.generateKeyPairSync()方法](https://www.geeksforgeeks.org/node-js-crypto-generatekeypairsync-method/)创建私钥和公钥。
*   **签名:**签名参数必须是缓冲区、类型化数组或数据视图的实例。

**返回值:**该函数返回一个布尔值。如果签名通过验证，返回**真**否则返回**假**。

**示例:**

**文件名:index.js**

## java 描述语言

```
// Importing Required Modules
const crypto = require('crypto');
const buffer = require('buffer');

// Creating a private key
const { privateKey, publicKey } = crypto.generateKeyPairSync('rsa', {
  modulusLength: 2048,
});
// Using Hashing Algorithm
const algorithm = "SHA256";

// Converting string to buffer
const data = Buffer.from("I Love GeeksForGeeks");

// Sign the data and returned signature in buffer
const signature = crypto.sign(algorithm, data , privateKey);

// Verifying signature using crypto.verify() function
const isVerified = crypto.verify(algorithm, data, publicKey, signature);

// Printing the result
console.log(`Is signature verified: ${isVerified}`);
```

使用以下命令运行 **index.js** :

```
node index.js
```

**输出:**

![](img/824f0142530817710369249b05ae20a5.png)

**参考**[:https://nodejs . org/API/crypto . html # crypto _ crypto _ verify _ algorithm _ data _ key _ signature](https://nodejs.org/api/crypto.html#crypto_crypto_verify_algorithm_data_key_signature)