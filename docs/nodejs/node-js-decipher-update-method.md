# Node.js 破译. update()方法

> 原文:[https://www . geesforgeks . org/node-js-decrypt-update-method/](https://www.geeksforgeeks.org/node-js-decipher-update-method/)

**decrypt . update()**方法是加密模块内一个内置的 decrypt 类应用编程接口，用于根据给定的编码格式用数据更新解密。

**语法:**

```
const dicipher.update(data[, inputEncoding][, outputEncoding])
```

**参数:**该方法取以下参数:

*   **Data:** Used to update and decrypt with new content.
*   **Enter code:** Enter the code format.
*   **Output code:** Output code format.

**返回值:**此方法不返回值。

**示例 1:** **文件名:index.js**

## java 描述语言

```
// Node.js program to demonstrate the
// decipher.update() method

// importing crypto module
const crypto = require('crypto');

// Creating and initializing algorithm and password
const algorithm = 'aes-192-cbc';
const password = 'Password used to generate key';

// Getting key for the decipher object
const key = crypto.scryptSync(password, 'salt', 24);

// Creating and initializing the static iv
const iv = Buffer.alloc(16, 0);

// Creating and initializing the decipher object
const decipher = crypto.createDecipheriv(algorithm, key, iv);

// Encrypted using same algorithm, key and iv.
const encrypted =
'e5f79c5915c02171eec6b212d5520d44480993d7d622a7c4c2da32f6efda0ffa';

// Updating the data into decipher object
let decrypted = decipher.update(encrypted, 'hex', 'utf8');

// Getting decrypted data
decrypted += decipher.final('utf8');

// Display the result
console.log("buffer :- " + decrypted);
```

**输出:**

```
buffer :- some clear text data
```

**示例 2:** **文件名:index . js**

## Javascript

```
// Node.js program to demonstrate the
// decipher.update() method

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

        // Creating and initializing the decipher object
        const decipher = crypto
            .createDecipheriv(algorithm, key, iv);

        // Encrypted using same algorithm, key and iv.
        const encrypted =
'e5f79c5915c02171eec6b212d5520d44480993d7d622a7c4c2da32f6efda0ffa';

        // updating the data into decipher object
        const decrypted = decipher.update(encrypted, 'hex', 'utf8');

        console.log("buffer :- " + decipher);
    });
```

**输出:**

```
buffer :- [object Object]
```

使用以下命令运行 index.js 文件:

```
node index.js
```

**参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/crypto . html # crypto _ decrypt _ update _ data _ input encoding _ output encoding](https://nodejs.org/dist/latest-v12.x/docs/api/crypto.html#crypto_decipher_update_data_inputencoding_outputencoding)