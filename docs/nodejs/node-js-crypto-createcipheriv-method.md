# node . js crypto . createcipheriv()方法

> 原文:[https://www . geesforgeks . org/node-js-crypto-createcipheriv-method/](https://www.geeksforgeeks.org/node-js-crypto-createcipheriv-method/)

**crypto.createCipheriv()方法**是加密模块的内置应用编程接口，用于使用所述算法、密钥和初始化向量(iv)创建密码对象。
**语法:**

```
crypto.createCipheriv( algorithm, key, iv, options )
```

**参数:**该方法接受如上所述和如下所述的四个参数:

*   **算法:**是依赖于 *OpenSSL* 的字符串类型值。例如 *aes192* 、 *aes256* 等。
*   **密钥:**是算法和 iv 使用的原始密钥。它持有*字符串*、*缓冲区*、*类型*或*数据视图*。密钥可以是*密钥对象*，可选类型为秘密。
*   **iv:** 它是一个初始化向量，必须是不确定且非常唯一的。然而，理想的静脉注射将是密码随机的。不需要保密。它可以保存*字符串*、*缓冲区*、*类型的数据或者*数据视图*类型的数据。如果密码不需要 *iv* ，则可以是 *null* 。*
*   **选项:**是一个可选参数，用于控制流行为。它是可选的，除非在 CCM 或 OCB 模式下使用密码(例如“aes-128-ccm”)。在这种情况下，需要*身份验证标签长度*选项来定义身份验证标签的长度(字节)，而在 *GCM* 模式下，不需要*身份验证标签长度*选项，但它可以用于设置将由 getAuthTag()方法返回的身份验证标签的长度，默认值为 16 字节。

**返回值:**返回**密码**对象。
以下示例说明了在 Node.js:
**中使用 **crypto.createCipheriv()方法**示例 1:**

## java 描述语言

```
// Node.js program to demonstrate the    
// crypto.createCipheriv() method

// Includes crypto module
const crypto = require('crypto');

// Defining algorithm
const algorithm = 'aes-256-cbc';

// Defining key
const key = crypto.randomBytes(32);

// Defining iv
const iv = crypto.randomBytes(16);

// An encrypt function
function encrypt(text) {

 // Creating Cipheriv with its parameter
 let cipher = crypto.createCipheriv(
      'aes-256-cbc', Buffer.from(key), iv);

 // Updating text
 let encrypted = cipher.update(text);

 // Using concatenation
 encrypted = Buffer.concat([encrypted, cipher.final()]);

 // Returning iv and encrypted data
 return { iv: iv.toString('hex'),
    encryptedData: encrypted.toString('hex') };
}

// Displays output
var output = encrypt("GeeksforGeeks");
console.log(output);
```

**输出:**

```
{ iv: 'fb1f4b0a7daaada6cae678df32fad0f0',
  encryptedData: '41aad2618892aa3d1850d336ad15b50e' }
```

**例 2:**

## java 描述语言

```
// Node.js program to demonstrate the    
// crypto.createCipheriv() method

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

// Creating cipher
const cipher = crypto.createCipheriv(algorithm, key, iv);

// Declaring encrypted
let encrypted = '';

// Reading data
cipher.on('readable', () => {
  let chunk;
  while (null !== (chunk = cipher.read())) {
    encrypted += chunk.toString('base64');
  }
});

// Handling end event
cipher.on('end', () => {
console.log(encrypted);
});

// Writing data
cipher.write('CS-Portal');
cipher.end();
console.log("done");
```

**输出:**

```
done
MfHwhG/WPv+TIbG/qM78qA==
```

**参考:**[https://nodejs . org/API/crypto . html # crypto _ crypto _ createcipheriv _ algorithm _ key _ iv _ options](https://nodejs.org/api/crypto.html#crypto_crypto_createcipheriv_algorithm_key_iv_options)