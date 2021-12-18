# Node.js crypto.publicEncrypt()方法

> 原文:[https://www . geesforgeks . org/node-js-crypto-public encrypt-method/](https://www.geeksforgeeks.org/node-js-crypto-publicencrypt-method/)

**crypto.publicEncrypt()方法**是加密模块的内置应用程序编程接口，用于使用参数“密钥”加密缓冲区的指定内容。

**语法:**

```js
crypto.publicEncrypt( key, buffer )
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **Key:** This parameter holds data of object, string, buffer or key object type, and contains the following five parameters:
    1.  **Key:** It is a PEM-encoded public or private key. String of type *, buffer and key object* .
    2.  **OAEPhash:** is a hash function of type string, used for "oaep" filling. The default value is "sha1".
    3.  **Label:** is a label for "OAEP" filling. If not specified, the label is not used. Type *buffer, type [dArray] or data view* .
    4.  **Passphrase:** It is an optional passphrase of the private key, which can be a string or a buffer.
    5.  **填充:**是可选的填充值,在 crypto.constants 中定义,可以是密码。常数。RSA _ NO _ PADDING，加密。常数。RSA _ PKCS1 _ PADDING 或密码。常数。RSA _ PKCS1 _ OAEP _ PADDING .它是类型*密码常量*。
*   **Buffer:** type is *buffer, TypedArray or dataview* .

**返回值:**返回一个包含加密内容的新缓冲区。

下面的例子说明了 **crypto.publicEncrypt()方法**在 Node.js 中的使用:

**例 1:**

```js
// Node.js program to demonstrate the 
// crypto.publicEncrypt() method

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

    // Creating public key file 
    fs.writeFileSync("public_key", keyPair.publicKey);
}

// Generate keys
generateKeyFiles();

// Creating a function to encrypt string
function encryptString (plaintext, publicKeyFile) {
    const publicKey = fs.readFileSync(publicKeyFile, "utf8");

    // publicEncrypt() method with its parameters
    const encrypted = crypto.publicEncrypt(
         publicKey, Buffer.from(plaintext));
    return encrypted.toString("base64");
}

// Defining a text to be encrypted
const plainText = "GfG";

// Defining encrypted text
const encrypted = encryptString(plainText, "./public_key");

// Prints plain text
console.log("Plaintext:", plainText);

// Prints encrypted text
console.log("Encrypted: ", encrypted);
```

**输出:**

```js
Plaintext: GfG
Encrypted:  l0touwFaNv1DIgPE365VQD0G4rg+IbRD5G6IBQ1arLgWtFOStKO7duYJ6/JzlOJl3eBG7obqzAEJ0V2WrxtYRTg=

```

**例 2:**

```js
// Node.js program to demonstrate the 
// crypto.publicEncrypt() method

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

    // Creating public key file 
    fs.writeFileSync("public_key", keyPair.publicKey);
}

// Generate keys
generateKeyFiles();

// Creating a function to encrypt string
function encryptString (plaintext, publicKeyFile) {
    const publicKey = fs.readFileSync(publicKeyFile, "utf8");

    // publicEncrypt() method with its parameters
    const encrypted = crypto.publicEncrypt(
             publicKey, Buffer.from(plaintext));
    return encrypted;
}

// Defining a text to be encrypted
const plainText = "Hello!";

// Defining encrypted text
const encrypted = encryptString(plainText, "./public_key");

// Prints plain text
console.log("Plaintext:", plainText);

// Prints buffer
console.log("Buffer: ", encrypted);
```

**输出:**

```js
Plaintext: Hello!
Buffer: <Buffer 1b 2a c7 4d 10 44 45 8e 9d e6
53 9d 8a 5e 39 0f ea e2 96 00 d7 d3 b3 eb 54 7e
74 7d a4 62 b8 eb 68 85 cb 8e 85 a5 f7 71 2f b7
93 d6 14 1c 38 cd 45 85 ... >

```

**参考:**[https://nodejs . org/API/crypt . html # crypt _ crypt _ public encrypt _ key _ buffer](https://nodejs.org/api/crypto.html#crypto_crypto_publicencrypt_key_buffer)