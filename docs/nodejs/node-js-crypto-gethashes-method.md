# Node.js crypto.getHashes()方法

> 原文:[https://www . geesforgeks . org/node-js-crypto-gethashes-method/](https://www.geeksforgeeks.org/node-js-crypto-gethashes-method/)

**crypto.getHashes()方法**是一个内置的加密模块应用编程接口，用于显示数组中所有支持的哈希算法的名称。

**语法:**

```
crypto.getHashes()
```

**参数:**此方法不接受任何参数。

**返回值:**返回所有支持的哈希算法的名称。

下面的例子说明了 **crypto.getHashes()方法**在 Node.js 中的使用:

**例:**

```
// Node.js program to demonstrate the 
// crypto.getHashes() method

// Including crypto module
const crypto = require('crypto');

// Calling getHashes method
const hash = crypto.getHashes();

// Prints all the supported hash algorithms
console.log("The list of all the hash "
        + "algorithms are : ", hash);
```

**输出:**

```
The list of all the hash algorithms are :  [ 'RSA-MD4',
  'RSA-MD5',
  'RSA-MDC2',
  'RSA-RIPEMD160',
  'RSA-SHA1',
  'RSA-SHA1-2',
  'RSA-SHA224',
  'RSA-SHA256',
  'RSA-SHA3-224',
  'RSA-SHA3-256',
  'RSA-SHA3-384',
  'RSA-SHA3-512',
  'RSA-SHA384',
  'RSA-SHA512',
  'RSA-SHA512/224',
  'RSA-SHA512/256',
  'RSA-SM3',
  'blake2b512',
  'blake2s256',
  'id-rsassa-pkcs1-v1_5-with-sha3-224',
  'id-rsassa-pkcs1-v1_5-with-sha3-256',
  'id-rsassa-pkcs1-v1_5-with-sha3-384',
  'id-rsassa-pkcs1-v1_5-with-sha3-512',
  'md4',
  'md4WithRSAEncryption',
  'md5',
  'md5-sha1',
  'md5WithRSAEncryption',
  'mdc2',
  'mdc2WithRSA',
  'ripemd',
  'ripemd160',
  'ripemd160WithRSA',
  'rmd160',
  'sha1',
  'sha1WithRSAEncryption',
  'sha224',
  'sha224WithRSAEncryption',
  'sha256',
  'sha256WithRSAEncryption',
  'sha3-224',
  'sha3-256',
  'sha3-384',
  'sha3-512',
  'sha384',
  'sha384WithRSAEncryption',
  'sha512',
  'sha512-224',
  'sha512-224WithRSAEncryption',
  'sha512-256',
  'sha512-256WithRSAEncryption',
  'sha512WithRSAEncryption',
  'shake128',
  'shake256',
  'sm3',
  'sm3WithRSAEncryption',
  'ssl3-md5',
  'ssl3-sha1',
  'whirlpool' ]

```

**参考:**[https://nodejs . org/API/crypt . html # crypt _ crypt _ get hashes](https://nodejs.org/api/crypto.html#crypto_crypto_gethashes)