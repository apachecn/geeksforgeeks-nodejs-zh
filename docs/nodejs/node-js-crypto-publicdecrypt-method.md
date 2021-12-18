# Node.js crypto.publicDecrypt()方法

> 原文:[https://www . geesforgeks . org/node-js-crypto-public decrypt-method/](https://www.geeksforgeeks.org/node-js-crypto-publicdecrypt-method/)

**crypto.publicDecrypt()方法**用于使用**密钥**对缓冲区的内容进行解密，该密钥先前使用相应的私钥进行了加密，即 crypto.privateEncrypt()方法。

**语法:**

```js
crypto.publicDecrypt( key, buffer )
```

**参数:**该方法接受两个参数，如 avobe 所述，描述如下:

*   **Key:** Its type is *object, string, buffer or keyobject* , which contains two parameters, as shown below:
    1.  **Passphrase:** It is an optional type of private key, which can be a string or a buffer.
    2.  **padding:** is an optional padding value defined in crypto.constants, which can be crypto. constants.rsa _ no _ padding, or crypto. constants.rsa _ pkcs1 _ padding. Its type is *password constant* .
*   **buffer** Its type is *buffer, TypedArray or dataview* .

**返回类型:**返回一个包含解密内容的新缓冲区。

下面的例子说明了 **crypto.publicDecrypt()方法**在 Node.js 中的使用:

**例 1:**

```js
// Node.js program to demonstrate the 
// crypto.publicDecrypt() method

// Including crypto, path, and fs module
var crypto = require('crypto');
var fs = require('fs');
const path = require('path');

// Generating key files
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

    // Creating public and private key file 
    fs.writeFileSync("public_key", keyPair.publicKey);
    fs.writeFileSync("private_key", keyPair.privateKey);
}

// Generate keys
generateKeyFiles();

// Reading private key file
var PRIVKEY = fs.readFileSync(path.join(__dirname,
                          'private_key'), 'utf8');

// Reading public key file
var PUBKEY = fs.readFileSync(path.join(__dirname,
                          'public_key'), 'utf8');

// Defining my msg
myMSG = "GeeksforGeeks!";
console.log("Original msg is : "+myMSG);

// RSA PRIVATE ENCRYPT -> PUBLIC DECRYPT
function privENC_pubDEC(originMSG){

  // Encrypting msg with privateEncrypt method
 encmsg = crypto.privateEncrypt(PRIVKEY,
               Buffer.from(originMSG, 'utf8') )
.toString('base64');

 // Decrypting msg with publicDecrypt method
 msg = crypto.publicDecrypt(PUBKEY,
              Buffer.from(encmsg, 'base64'));

 console.log();

 // Prints encrypted msg
 console.log("Encrypted with private key: "
                      + encmsg);

 console.log();

 // Prints decrypted msg
 console.log("Decrypted with public key: "
                     + msg.toString());
}

// Calling privENC_pubDEC() method
privENC_pubDEC(myMSG);
```

**输出:**

```js
Original msg is : GeeksforGeeks!

Encrypted with private key:
knwqke0ZrpJj1sLtL978OyqBMnJUEAEgTy1qJbyEnJyWbjoQ6hO7f
2FPnVhJnZwpZlxLbFQZCV1GMmr6WWJenFo=

Decrypted with public key: GeeksforGeeks!

```

**例 2:**

```js
// Node.js program to demonstrate the 
// crypto.publicDecrypt() method

// Including the fs and crypto modules
var crypto = require('crypto');
var fs = require('fs');

// Reading the Private Key
privK = fs.readFileSync('priv.key').toString();

// Passing the text to be encrypted
// using private key
var buf = Buffer.from('rishabh', 'utf8');

// Encrypting the text
secretData = crypto.privateEncrypt(privK, buf);

// Printing the encrypted text
console.log(secretData);

// Reading the Public key
pubK = fs.readFileSync('pub.key').toString();

// Decrypting the text using public key
origData = crypto.publicDecrypt(pubK, secretData);

// Printing the original content
console.log(origData);
```

**输出:**

```js
// Buffer 27 62 a1 2a 53 8d 0d 52 c7 3f e8 cc 89 42 c6
3e 8e 60 cd d3 57 06 d4 c9 1e 31 ba e6 23 8b 2c 10 be 
c1 fc ed 53 a4 9f f9 e0 5b da 74 d7 c2ca d0 98 f4 ... 
// Buffer 72 69 73 68 61 62 68

```

**参考:**[https://nodejs . org/API/crypto . html # crypt _ crypt _ publicdecrypt _ key _ buffer](https://nodejs.org/api/crypto.html#crypto_crypto_publicdecrypt_key_buffer)