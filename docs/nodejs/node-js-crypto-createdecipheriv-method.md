# node . js crypto . createdecipheriv()方法

> 原文:[https://www . geesforgeks . org/node-js-crypto-createdecipheriv-method/](https://www.geeksforgeeks.org/node-js-crypto-createdecipheriv-method/)

**crypto . createdecidepheriv()方法**是一个内置的加密模块应用编程接口，用于创建一个*解密*对象，具有所述的*算法*、*密钥*和*初始化向量*，即(iv)。

**语法:**

```
crypto.createDecipheriv( algorithm, key, iv, options )
```

**参数:**该方法接受上述四个参数，描述如下:

*   **Algorithm:** It is a string type value that depends on *OpenSSL* . Examples include *AE192* , *AE256* , etc.
*   **key:** is the original key used by algorithm and iv. It holds *string* , *buffer* , *type* or *data view* . The key can be an optional secret type *key object* .
*   **IV:** It is an initialization vector and must be uncertain and unique. However, the ideal intravenous injection will be password random. No need to keep secret. It can store data of type *string* , *buffer* , *or data of type *data view* . If the password does not need *IV* , it can be *null* .*
*   **option:** is an optional parameter used to control the popular behavior. It is optional unless the password is used in CCM or OCB mode (for example, "aes-128-ccm"). In this case, the *authtaglength* option is needed to define the length (bytes) of the authentication tag. In the *GCM* mode, the *authtaglength* option is not needed, but it can be used to set the length of the authentication tag to be returned by the getAuthTag () method, with the default value of 16 bytes.

**返回值:**返回**破译**对象。

以下示例说明了在 Node.js 中使用 **crypto.createDecipheriv()方法**:

**例 1:**

```
// Node.js program to demonstrate the     
// crypto.createDecipheriv() method

// Includes crypto module
const crypto = require('crypto');

// Defining algorithm
const algorithm = 'aes-192-cbc';

// Defining password
const password = 'bncaskdbvasbvlaslslasfhj';

// Defining key
const key = crypto.scryptSync(password, 'GfG', 24);

// Defininf iv
const iv = Buffer.alloc(16, 0); 

// Creating decipher
const decipher = 
    crypto.createDecipheriv(algorithm, key, iv);

// Declaring decrypted
let decrypted = '';

// Reading data
decipher.on('readable', () => {
  let chunk;
  while (null !== (chunk = decipher.read())) {
    decrypted += chunk.toString('utf8');
  }
});

// Handling end event
decipher.on('end', () => {
console.log(decrypted);
});

// Encrypted data which is to be decrypted
const encrypted =
  'MfHwhG/WPv+TIbG/qM78qA==';

decipher.write(encrypted, 'base64');
decipher.end();

console.log("done");
```

**输出:**

```
done
CS-Portal

```

**例 2:**

```
// Node.js program to demonstrate the     
// crypto.createDecipheriv() method

// Includes crypto module
const crypto = require('crypto');

// Difining algorithm
const algorithm = 'aes-256-cbc';

// Defining key
const key = crypto.randomBytes(32);

// Defining iv
const iv = crypto.randomBytes(16);

// An encrypt function
function encrypt(text) {

 // Creating Cipheriv with its parameter
 let cipher = 
    crypto.createCipheriv('aes-256-cbc', Buffer.from(key), iv);

 // Updating text
 let encrypted = cipher.update(text);

 // Using concatenation
 encrypted = Buffer.concat([encrypted, cipher.final()]);

 // Returning iv and encrypted data
 return { iv: iv.toString('hex'),
     encryptedData: encrypted.toString('hex') };
}

// A decrypt function
function decrypt(text) {

 let iv = Buffer.from(text.iv, 'hex');
 let encryptedText =
    Buffer.from(text.encryptedData, 'hex');

 // Creating Decipher
 let decipher = crypto.createDecipheriv(
        'aes-256-cbc', Buffer.from(key), iv);

 // Updating encrypted text
 let decrypted = decipher.update(encryptedText);
 decrypted = Buffer.concat([decrypted, decipher.final()]);

 // returns data after decryption
 return decrypted.toString();
}

// Encrypts output
var output = encrypt("GeeksforGeeks");
console.log(output);

// Decrypts output
console.log(decrypt(output));
```

**输出:**

```
{ iv: '6bbc47a2756d6d6bf315cfd3cc0b711a',  encryptedData: 'fae9a6fb31c0b0668da8c3be1b1da81a' }
GeeksforGeeks

```

**参考:**[https://nodejs . org/API/crypto . html # crypto _ crypto _ createdecipheriv _ algorithm _ key _ iv _ options](https://nodejs.org/api/crypto.html#crypto_crypto_createdecipheriv_algorithm_key_iv_options)