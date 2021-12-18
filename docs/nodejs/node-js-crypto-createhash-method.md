# Node.js crypto.createHash()方法

> 原文:[https://www . geesforgeks . org/node-js-crypto-create hash-method/](https://www.geeksforgeeks.org/node-js-crypto-createhash-method/)

**crypto.createHash()方法**用于创建一个 *Hash* 对象，该对象可用于使用所述算法创建哈希摘要。

**语法:**

```
crypto.createHash( algorithm, options )
```

**参数:**该方法接受两个参数，如 avobe 所述，描述如下:

*   **algorithm:** It depends on the accessible algorithm favored by *OpenSSL* version on the platform. It returns a string. Examples are *sha256* , *sha512* and so on.
*   **option:** is an optional parameter, which is used to control the popular behavior. It returns an object. In addition, for a **XOF** hash function like "shake256", you can use the option *Output Length* to determine the required output length (in bytes).

**返回类型:**返回**哈希**对象。

下面的例子说明了 **crypto.createHash()方法**在 Node.js 中的使用:

**例 1:**

```
// Node.js program to demonstrate the     
// crypto.createHash() method

// Includes crypto module
const crypto = require('crypto');

// Defining key
const secret = 'Hi';

// Calling createHash method
const hash = crypto.createHash('sha256', secret)

                   // updating data
                   .update('How are you?')

                   // Encoding to be used
                   .digest('hex');

// Displays output
console.log(hash);
```

**输出:**

```
df287dfc1406ed2b692e1c2c783bb5cec97eac53151ee1d9810397aa0afa0d89
```

**例 2:**

```
// Node.js program to demonstrate the     
// crypto.createHash() method

// Defining filename
const filename = process.argv[2];

// Includes crypto and  fs module
const crypto = require('crypto');
const fs = require('fs');

// Creating Hash 
const hash = crypto.createHash('sha256', 'Geeksforgeeks');

// Creating read stream
const input = fs.createReadStream(filename);

input.on('readable', () => {

 // Calling read method to read data
  const data = input.read();
  if (data)

    // Updating
    hash.update(data);
  else
   {
    // Encoding and displaying filename
    console.log(`${hash.digest('base64')} ${filename}`);
  }
});
console.log("Program done!");
```

**输出:**

```
Program done!
n95mt3468ZzAIwu/bbNU7dej6CoFkDRcNaJo7rGpLF4= index.js
```

**参考:**[https://nodejs . org/API/crypto . html # crypto _ crypto _ createhash _ algorithm _ options](https://nodejs.org/api/crypto.html#crypto_crypto_createhash_algorithm_options)