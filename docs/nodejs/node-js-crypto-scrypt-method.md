# Node.js crypto.scrypt()方法

> 原文:[https://www.geeksforgeeks.org/node-js-crypto-scrypt-method/](https://www.geeksforgeeks.org/node-js-crypto-scrypt-method/)

**crypto.scrypt()方法**是加密模块的内置应用程序编程接口，用于实现异步加密。其中，**加密**是一个基于密码的密钥派生函数。它的计算成本和内存成本都很高。因此，暴力攻击是不成功的。

**语法:**

```js
crypto.scrypt( password, salt, keylen, options, callback )
```

**参数:**该方法接受五个参数，如上所述，如下所述:

*   **密码:**可以保存字符串、Buffer、TypedArray 或 DataView 类型的数据。
*   **salt:** 它保存字符串、缓冲区、类型数据或数据视图类型的数据。它必须尽可能独特。此外，建议 salt 应该是随机的，并且至少有 16 个字节长。
*   **keylen:** 是键的长度，必须是数字。
*   **选项:**类型为*对象*，有七个参数，即`cost, blockSize, parallelization, N, r, p,`和`maxmem`。
    哪里，
    1.  **成本:**是 CPU 或内存的成本参数。它是一个数字，必须是二的幂，但大于一，默认情况下，它的值是 16384。
    2.  **块大小:**是分配块大小的参数。它是一个数字，缺省值是 8。
    3.  **并行化:**是*并行化*的参数。它是一个数字，默认值为 1。
    4.  **N:** 是成本的别名。它是一个数字，只能定义两者中的一个。
    5.  **r:** 是 blockSize 的别名。它是一个数字，只能定义两者中的一个。
    6.  **p:** 是并行化的别名。它是一个数字，只能定义两者中的一个。
    7.  **maxmem:** 是要使用的内存的上限。这是一个数字，当 **128 * N * r** (近似值)大于 maxmem 时会出现错误。默认值为(32 * 1024 * 1024)。
*   **回调**是一个有两个参数的函数，即 err 和派生键。

**返回值:**返回一个缓冲区。

下面的例子说明了 **crypto.scrypt()方法**在 Node.js 中的使用:

**例 1:**

```js
// Node.js program to demonstrate the
// crypto.scrypt() method

// Including crypto module
var crypto = require('crypto');

// Calling scrypt method with some of its parameter
crypto.scrypt('GfG', 'ffdgsg', 32, (err, derivedKey) => {

  if (err) throw err;

  // Prints derived key as buffer
  console.log("The derived key1 is :", derivedKey);
});

// Calling scrypt method with the parameter N
crypto.scrypt('GeeksforGeeks', 'tfytdx', 128,
           { N: 512 }, (err, derivedKey) => {

  if (err) throw err;

  // Prints derived key as buffer
  console.log("The derived key2 is :", derivedKey);
  console.log();
});
```

**输出:**

```js
The derived key2 is : <Buffer b3 f8 72 5f 58 df
98 d9 c0 8a ba 0c 2c 50 85 b1 76 de 39 35 40 27 7d
57 f1 6a a1 07 54 dc c9 63 65 32 f2 db 29 95 dc ee
0b 9f e3 d5 0a 9e 3a d0 f6 b4 ... >

The derived key1 is : <Buffer dd 47 ee 3e a8 2e
f2 5b eb 18 7d 35 1b fd f5 a8 e5 f5 38 ef a7 ff 05
53 1e 86 69 ad cd e8 89 76 >

```

**例 2:**

```js
// Node.js program to demonstrate the
// crypto.scrypt() method

// Including crypto module
var crypto = require('crypto');

// Defining salt as typed array
const x = new Uint32Array(7);

// Calling scrypt method with some of its parameter
crypto.scrypt('yytunnd', x,  16, (err, derivedKey) => {

  if (err) throw err;

  // Prints derived key which is encoded
  console.log("The derived key1 is :",
            derivedKey.toString("ascii"));
});

// Defining salt as data view
const y = new DataView(new ArrayBuffer(5));

// Calling scrypt method with the parameter N
crypto.scrypt('oksjdjdn', y, 16, { N: 32 },
                (err, derivedKey) => {

  if (err) throw err;

  // Prints derived key after encoding
  console.log("The derived key2 is :",
            derivedKey.toString("base64"));
  console.log();
});
```

**输出:**

```js
The derived key2 is : 6Gu0JKHDSHs0tkTuGYuQ7A==
The derived key1 is : G"@&H 
                           pVCD3                               
                                X%

```

**参考:**[https://nodejs . org/API/crypt . html # crypt _ crypt _ scrypt _ password _ salt _ keylen _ options _ callback](https://nodejs.org/api/crypto.html#crypto_crypto_scrypt_password_salt_keylen_options_callback)