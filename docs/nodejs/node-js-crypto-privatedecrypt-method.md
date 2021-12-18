# node . js crypto . private decrypt()方法

> 原文:[https://www . geesforgeks . org/node-js-crypto-private decrypt-method/](https://www.geeksforgeeks.org/node-js-crypto-privatedecrypt-method/)

**crypto.privateDecrypt()方法**用于使用 *privateKey.buffer* 解密缓冲区的内容，该缓冲区先前使用相应的公钥加密，即 crypto.publicEncrypt()。

**语法:**

```
crypto.privateDecrypt( privateKey, buffer )
```

**参数:**这个方法接受上面提到的和下面描述的两个参数:

*   **[private key:** It can store data of Object, string, Buffer or KeyObject type.
    1.  **OAEPhash** is a hash function for the type string filled by "oaep". The default value is "sha1".
    2.  **OAEPlabel:** is the label used for "oaep" filling. If not specified, the label is not used. Type *buffer, type [dArray] or data view* .
    3.  **填充:**是可选的填充值,在 crypto.constants 中定义,可以是密码。常数。RSA _ NO _ PADDING，加密。常数。RSA _ PKCS1 _ PADDING 或密码。常数。RSA _ PKCS1 _ OAEP _ PADDING .它是类型*密码常量*。
*   **Buffer:** type is *buffer, TypedArray or dataview* .

**返回值:**返回一个包含解密内容的新缓冲区。

下面的例子说明了在 Node.js 中使用 **crypto.privateDecrypt()方法**:

**例 1:**

```
// Node.js program to demonstrate the 
// crypto.privateDecrypt() method

// Including the crypto and fs modules
var crypto = require('crypto');
var fs = require('fs');

// Reading the Public Key
pubK = fs.readFileSync('pub.key').toString();

// Passing the text to be encrypted using private key
var buf = Buffer.from('This is secret code', 'utf8');

// Encrypting the text
secretData = crypto.publicEncrypt(pubK, buf);

// Printing the encrypted text
console.log(secretData);

// Reading the Private key
privK = fs.readFileSync('priv.key').toString();

// Decrypting the text using public key
origData = crypto.privateDecrypt(privK, secretData);
console.log();

// Printing the original content
console.log(origData);
```

**输出:**

```
<Buffer 58 dd 76 8f cb 25 52 2b e7 3a b2 1b
0f 43 aa e0 df 65 fa 1d 3b 31 6f b7 f9 47 06
d5 f7 72 19 cd 2f 67 66 27 00 bb 43 8e 64 38
07 38 28 aa07 59 b4 60 ... >

<Buffer 54 68 69 73 20 69 73 20 73 65 63 72
65 74 20 63 6f 64 65 >

```

**例 2:**

```
// Node.js program to demonstrate the 
// crypto.privateDecrypt() method

// Including crypto and fs module
const crypto = require('crypto');
const fs = require("fs");

// Using a function generateKeyFiles
function generateKeyFiles() {

    const keyPair = crypto.generateKeyPairSync('rsa', {
        modulusLength: 530,
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

    // Creating public and private key file 
    fs.writeFileSync("public_key", keyPair.publicKey);
    fs.writeFileSync("private_key", keyPair.privateKey);
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

// Creating a function to decrypt string
function decryptString (ciphertext, privateKeyFile) {
    const privateKey = fs.readFileSync(privateKeyFile, "utf8");

    // privateDecrypt() method with its parameters
    const decrypted = crypto.privateDecrypt(
      {
        key: privateKey,
        passphrase: '',
      },
      Buffer.from(ciphertext, "base64")
    );

    return decrypted.toString("utf8");
}

// Defining a text to be encrypted
const plainText = "Geeks!";

// Defining encrypted text
const encrypted = encryptString(plainText, "./public_key");

// Prints plain text
console.log("Plaintext:", plainText);
console.log();

// Prints buffer of encrypted content
console.log("Encrypted Text: ", encrypted);
console.log();

// Prints buffer of decrypted content
console.log("Decrypted Text: ", 
    decryptString(encrypted, "private_key"));
```

**输出:**

```
Plaintext: Geeks!

Encrypted Text:  ACks6H7InpaeGdI4w9MObyD73YB7N1V0nVsG5Jl10SNeH3no6gfgjeD4ZFsSFhCXzFkognMGbRNsg0BReVOHxRs7eQ==

Decrypted Text: Geeks!

```

**参考:**[https://nodejs . org/API/crypt . html # crypt _ crypt _ private decrypt _ private key _ buffer](https://nodejs.org/api/crypto.html#crypto_crypto_privatedecrypt_privatekey_buffer)