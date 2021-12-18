# node . js crypto . private encrypt()方法

> 原文:[https://www . geesforgeks . org/node-js-crypto-private encrypt-method/](https://www.geeksforgeeks.org/node-js-crypto-privateencrypt-method/)

**crypto.privateEncrypt()方法**用于使用参数“privateKey”加密缓冲区的指定内容。

**语法:**

```js
crypto.privateEncrypt( privateKey, buffer )
```

**参数:**这个方法接受上面提到的和下面描述的两个参数:

*   **[private key:** It can store data of Object, string, Buffer or KeyObject type.
    1.  **Key:** is a' PEM' encoded private key. String of type *, buffer and key object* .
    2.  **Passphrase:** It is an optional passphrase of the private key, which can be a string or a buffer.
    3.  **padding** is an optional padding value defined in crypto.constants, which can be crypto. constants. RSA _ no _ padding, or crypto. constants. RSA _ pkcs1 _ padding. It is a password constant of type .
*   **buffer:** It contains data of buffer, TypedArray or DataView type.

**返回值:**返回一个包含加密内容的新缓冲区。

下面的例子说明了 **crypto.privateEncrypt()方法**在 Node.js 中的使用:

**例 1:**

```js
// Node.js program to demonstrate the 
// crypto.privateEncrypt() method

// Including crypto and fs module
const crypto = require('crypto');
const fs = require("fs");

// Using a function generateKeyFiles
function generateKeyFiles() {

    const keyPair = crypto.generateKeyPairSync('rsa', {
        modulusLength: 520,
        publicKeyEncoding: {
            type: 'spki',
            format: 'pem'
        },
        privateKeyEncoding: {
        type: 'pkcs8',
        format: 'pem',
        cipher: 'aes-256-cbc',
        passphrase: ''
        }
    });

    // Creating private key file 
    fs.writeFileSync("private_key", keyPair.privateKey);
}

// Generate keys
generateKeyFiles();

// Creating a function to encrypt string
function encryptString (plaintext, privateKeyFile) {
    const privateKey = fs.readFileSync(privateKeyFile, "utf8");

    // privateEncrypt() method with its parameters
    const encrypted = crypto.privateEncrypt(
          privateKey, Buffer.from(plaintext));

    return encrypted.toString("base64");
}

// Defining a text to be encrypted
const plainText = "GfG";

// Defining encrypted text
const encrypted = encryptString(plainText, "./private_key");

// Prints plain text
console.log("Plaintext:", plainText);

// Prints encrypted text
console.log("Encrypted: ", encrypted);
```

**输出:**

```js
Plaintext: GfG
Encrypted:  c60eR17GTQFkTI1ipTq5qFbYS58lIQqpDiou2UlYeOUE+u7agbtHvvwKaBpzBx4SvTCh5abpaqmyXCyGcUpGc7s=

```

**例 2:**

```js
// Node.js program to demonstrate the 
// crypto.privateEncrypt() method

// Including crypto and fs module
const crypto = require('crypto');
const fs = require("fs");

// Using a function generateKeyFiles
function generateKeyFiles() {

    const keyPair = crypto.generateKeyPairSync('rsa', {
        modulusLength: 520,
        publicKeyEncoding: {
            type: 'spki',
            format: 'pem'
        },
        privateKeyEncoding: {
        type: 'pkcs8',
        format: 'pem',
        cipher: 'aes-256-cbc',
        passphrase: ''
        }
    });

    // Creating private key file 
    fs.writeFileSync("private_key", keyPair.privateKey);
}

// Generate keys
generateKeyFiles();

// Creating a function to encrypt string
function encryptString (plaintext, privateKeyFile) {
    const privateKey = fs.readFileSync(privateKeyFile, "utf8");

    // privateEncrypt() method with its parameters
    const encrypted = crypto.privateEncrypt(
         privateKey, Buffer.from(plaintext));

    // Returns buffer as its not encoded
    return encrypted;
}

// Defining a text to be encrypted
const plainText = "GfG";

// Defining encrypted text
const encrypted = encryptString(plainText, "./private_key");

// Prints plain text
console.log("Plaintext:", plainText);

// Prints encrypted text
console.log("Encrypted buffer: ", encrypted);
```

**输出:**

```js
Plaintext: GfG
Encrypted buffer:  <Buffer 14 e5 84 05 2f b5 59 64
22 d2 19 99 f9 66 e5 18 50 76 27 df 0b e6 9f 50 1d a2
51 6a 93 21 04 7b 8f 50 ba 11 82 fd 3c 6e c0 81 be 58
f9 d6 a6 c7 19 da ... >

```

**参考:**[https://nodejs . org/API/crypt . html # crypt _ crypt _ private encrypt _ private key _ buffer](https://nodejs.org/api/crypto.html#crypto_crypto_privateencrypt_privatekey_buffer)