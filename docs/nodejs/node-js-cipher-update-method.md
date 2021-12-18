# Node.js cipher.update()方法

> 原文:[https://www.geeksforgeeks.org/node-js-cipher-update-method/](https://www.geeksforgeeks.org/node-js-cipher-update-method/)

**cipher.update()** 方法是加密模块内一个内置的类 cipher 应用编程接口，用于根据给定的编码格式用数据更新密码。

**语法:**

```js
const cipher.update(data[, inputEncoding][, outputEncoding])
```

**参数:**该方法取以下参数:

*   **Data:** Used to update the password according to the new content.
*   **Enter code:** Enter the code format.
*   **Output code:** Output code format.

**返回值:**该方法返回包含密码值的缓冲区对象。

**示例 1:** **文件名:index.js**

## java 描述语言

```js
// Node.js program to demonstrate the
// cipher.update() method

// Importing crypto module
const crypto = require('crypto');

// Creating and initializing algorithm and password
const algorithm = 'aes-192-cbc';
const password = 'Password used to generate key';

// Getting key for the cipher object
const key = crypto.scryptSync(password, 'salt', 24);

// Creating and initializing the static iv
const iv = Buffer.alloc(16, 0);

// Creating and initializing the cipher object
const cipher = crypto.createCipheriv(algorithm, key, iv);

// Updating the cipher with the data
// by using update() method
let encrypted = cipher.update(
    'some clear text data', 'utf8', 'hex');

// Getting the buffer data of cipher
encrypted += cipher.final('hex');

// Display the result
console.log(encrypted);
```

**输出:**

```js
e5f79c5915c02171eec6b212d5520d44480993d7d622a7c4c2da32f6efda0ffa
```

**示例 2:** **文件名:index . js**

## Javascript

```js
// Node.js program to demonstrate the
// cipher.update() method

// Importing crypto module
const crypto = require('crypto');

// Creating and initializing algorithm and password
const algorithm = 'aes-192-cbc';
const password = 'Password used to generate key';

// Getting key for cipher object
crypto.scrypt(password, 'salt', 24,
    { N: 512 }, (err, key) => {
        if (err) throw err;

        // Creating and initializing the static iv
        const iv = Buffer.alloc(16, 0);

        // Creating and initializing the cipher object
        const cipher = crypto
            .createCipheriv(algorithm, key, iv);

        // Updating the cipher with the data
        // by using update() method
        let encrypted = cipher.update(
            'some clear text data', 'utf8', 'hex');

        // Getting the buffer data of cipher 
        encrypted += cipher.final('hex');

        // Display the result
        console.log(encrypted);
    });
```

**输出:**

```js
5850288b1848440f0c410400403f7b456293229b5231c17d2b83b602f252714b
```

使用以下命令运行 index.js 文件:

```js
node index.js
```

**参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/crypto . html # crypto _ cipher _ update _ data _ input encoding _ output encoding](https://nodejs.org/dist/latest-v12.x/docs/api/crypto.html#crypto_cipher_update_data_inputencoding_outputencoding)