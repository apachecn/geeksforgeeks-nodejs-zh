# Node.js cipher.final()方法

> 原文:[https://www.geeksforgeeks.org/node-js-cipher-final-method/](https://www.geeksforgeeks.org/node-js-cipher-final-method/)

**cipher.final()** 方法是加密模块内一个内置的类 cipher 应用编程接口，用于返回包含密码对象值的缓冲区。

**语法:**

```
const cipher.final([outputEncoding])
```

**参数:**该方法以输出编码为参数。

**返回值:**该方法返回包含密码值的缓冲区对象。

**示例 1:** **文件名:index.js**

## java 描述语言

```
// Node.js program to demonstrate the
// cipher.final() method

// Importing crypto module
const crypto = require('crypto');

// Creating and initializing algorithm and password
const algorithm = 'aes-192-cbc';
const password = 'Password used to generate key';

// Getting key for the cipher object
const key = crypto.scryptSync(password, 'salt', 24);

// Creating and initializg the static iv
const iv = Buffer.alloc(16, 0);

// Creating and initializing the cipher object
const cipher = crypto.createCipheriv(algorithm, key, iv);

// Getting buffer value
// by using final() method
let value = cipher.final('hex');

// Display the result
console.log("buffer :- " + value);
```

**输出:**

```
buffer :- b9be42878310d599e4e49e040d1badb9
```

**示例 2:** **文件名:index . js**

## Javascript

```
// Node.js program to demonstrate the
// cipher.final() method

// Importing crypto module
const crypto = require('crypto');

// Creating and initializing algorithm and password
const algorithm = 'aes-192-cbc';
const password = 'Password used to generate key';

// Getting key for cipher object
crypto.scrypt(password, 'salt', 24,
    { N: 512 }, (err, key) => {

        if (err) throw err;

        // Creating and initializg the static iv
        const iv = Buffer.alloc(16, 0);

        // Creating and initializing the cipher object
        const cipher = crypto
            .createCipheriv(algorithm, key, iv);

        // Getting buffer value
        // by using final() method
        let value = cipher.final('hex');

        // Display the result
        console.log("buffer :- " + value);
    });
```

**输出:**

```
buffer :- 726cccfc7d80ca473d8d4de1a0a42675
```

使用以下命令运行 index.js 文件:

```
node index.js
```

**参考:**[**https://nodejs . org/dist/latest-v 12 . x/docs/API/crypto . html # crypto _ cipher _ final _ outputen coding**](https://nodejs.org/dist/latest-v12.x/docs/api/crypto.html#crypto_cipher_final_outputencoding)