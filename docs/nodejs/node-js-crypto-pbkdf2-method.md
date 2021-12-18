# Node.js crypto.pbkdf2()方法

> 原文:[https://www.geeksforgeeks.org/node-js-crypto-pbkdf2-method/](https://www.geeksforgeeks.org/node-js-crypto-pbkdf2-method/)

**crypto.pbkdf2()方法**给出了一个异步的**基于密码的密钥派生函数 2** ，即(pbkdf2)实现。此外，由摘要定义的特定 HMAC 摘要算法被实现为从所述密码、salt 和迭代中导出所需字节长度的密钥(keylen)。

**语法:**

```
crypto.pbkdf2( password, salt, iterations, keylen, digest, callback )
```

**参数:**该方法接受 6 个参数，如上所述，如下所述:

*   **Password:** It can store data of type *string, Buffer, TypedArray or dataview* .
*   **Salt:** Be as unique as possible. However, the recommended salt is arbitrary, and in any case it is at least 16 bytes long. Its type is **string, buffer, type data or data view** .
*   **Iteration times:** must be a number and should be set as high as possible. Therefore, the more iterations, the more secure the derived key is, but in this case, it takes more time to complete. It's of numerical type.
*   **keylen:** is the key of required byte length, type number.
*   **Abstract:** is a string type abstract algorithm.
*   **Callback:** is a function with two parameters, namely **err and derived key** .

**返回类型:**返回导出的基于密码的密钥。

下面的例子说明了 **crypto.pbkdf2()方法**在 Node.js 中的使用:

**例 1:**

```
// Node.js program to demonstrate the 
// crypto.pbkdf2() method

// Including crypto module
const crypto = require('crypto');

// Implementing pbkdf2 with all its parameters
crypto.pbkdf2('secret', 'salt', 100000, 64,
         'sha512', (err, derivedKey) => {

  if (err) throw err;

  // Prints derivedKey
  console.log(derivedKey.toString('hex'));
});
```

**输出:**

```
3745e482c6e0ade35da10139e797157f4a5da669dad7d5da88ef87e
47471cc47ed941c7ad618e827304f083f8707f12b7cfdd5f489b782
f10cc269e3c08d59ae

```

**例 2:**

```
// Node.js program to demonstrate the 
// crypto.pbkdf2() method

// Including crypto module
const crypto = require('crypto');

// Implementing pbkdf2 with all its parameters
// but digest is null
crypto.pbkdf2('secret', 'salt', 677, 6,
          null, (err, derivedKey) => {

  if (err) 
  {
    console.log(err);
  } 
  else
  {

  // Prints derivedKey without encoding
  console.log(derivedKey);

     }
});    
```

**输出:**这里，返回一个缓冲区，因为派生键没有被更改为字符串。

```
Buffer 71 1e 7b 7b 9b 53
```

**参考:**[https://nodejs . org/API/crypt . html # crypt _ crypt _ pbkdf 2 _ password _ salt _ iteration _ keylen _ digest _ callback](https://nodejs.org/api/crypto.html#crypto_crypto_pbkdf2_password_salt_iterations_keylen_digest_callback)