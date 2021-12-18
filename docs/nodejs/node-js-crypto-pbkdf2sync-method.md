# Node.js crypto.pbkdf2Sync()方法

> 原文:[https://www . geesforgeks . org/node-js-crypto-pbkdf2sync-method/](https://www.geeksforgeeks.org/node-js-crypto-pbkdf2sync-method/)

**crypto.pbkdf2Sync()** 方法给出了一个异步的*基于密码的密钥派生函数 2* ，即(PBKDF2)实现。此外，由摘要定义的特定 HMAC 摘要算法被实现为从所述密码、salt 和迭代中导出所需字节长度的密钥(keylen)。

**语法:**

```js
crypto.pbkdf2Sync( password, salt, iterations, keylen, digest )
```

**参数:**该方法接受 5 个参数，如上所述，如下所述:

*   **是绿筠::t1]云娥*-你好 TypedArray 缓冲区阿力 data view〔T3〕。***
*   **Salt:** Be as unique as possible. However, the recommended salt is arbitrary, and in any case it is at least 16 bytes long. Its type is *string, buffer, type data or data view* .
*   **Iteration times:** must be a number and should be set as high as possible. Therefore, the more iterations, the more secure the derived key is, but in this case, it takes more time to complete. It's of numerical type.
*   **keylen:** is the key of required byte length, type number.
*   **Abstract:** It is a string type abstract algorithm.

**返回类型:**返回派生键作为缓冲区。

下面的例子说明了 **crypto.pbkdf2Sync()方法**在 Node.js 中的使用:

**例 1:**

```js
// Node.js program to demonstrate the 
// crypto.pbkdf2Sync() method

// Including crypto module
const crypto = require('crypto');

// Implementing pbkdf2Sync
const key = crypto.pbkdf2Sync('secret',
           'salt', 2000, 64, 'sha512');

// Prints buffer
console.log(key);
```

**输出:**

```js
<Buffer 3c f1 85 49 62 52 38 64 2a 4e b1 4c f6 25 2e 1e fc
d7 8e 01 c9 40 d7 84 63 5e 24 ef 71 0f 91 83 bb 6d 03 bd
73 43 33 ec 78 a9 78 c8 1f ea7a dc 8c a6 ...>

```

**例 2:**

```js
// Node.js program to demonstrate the 
// crypto.pbkdf2Sync() method

// Including crypto module
const crypto = require('crypto');

// Implementing pbkdf2Sync
const key = crypto.pbkdf2Sync('secret',
       'salt', 100000, 100, 'sha512');

// Prints key which is encoded and converted
// to string
console.log(key.toString('hex'));
```

**输出:**

```js
3745e482c6e0ade35da10139e797157f4a5da669dad7d5da88ef87e4
7471cc47ed941c7ad618e827304f083f8707f12b7cfdd5f489b782f10cc269
e3c08d59ae04919ee902c99dba309cde75569fbe8e6d5c341d6f2576f6618c
589e77911a261ee964e2

```

**参考:**[https://nodejs . org/API/crypt . html # crypt _ crypt _ pbkdf 2 sync _ password _ salt _ iteration _ keylen _ digest](https://nodejs.org/api/crypto.html#crypto_crypto_pbkdf2sync_password_salt_iterations_keylen_digest)