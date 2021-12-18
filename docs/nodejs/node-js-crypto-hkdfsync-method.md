# Node.js crypto.hkdfSync()方法

> 原文:[https://www . geesforgeks . org/node-js-crypto-hkdfsync-method/](https://www.geeksforgeeks.org/node-js-crypto-hkdfsync-method/)

该方法提供了基于同步 HMAC 的提取和扩展密钥派生函数密钥派生。给定*键*、*盐*和*信息*，使用*摘要*导出**密钥**T2】字节的密钥。

**语法:**

```
crypto.hkdfSync(digest, key, salt, info, keylen)
```

**参数:**该方法有 5 个参数。

*   **Digest:** It must be a string.
*   **Key:** Minimum length—1 byte, the type is string, buffer, array buffer, type data area, key object or data view.
*   **Salt:** must be provided, but it can be zero-length and unique. Can be *string* , *array buffer,* buffer, *type DARAY* or *data view* .
*   **Information:** must be provided, but it can be of zero length and cannot exceed 1024 bytes. Its type is string, buffer, array buffer, type buffer, key object or data view.
*   **keylen:** is the length of the key to be generated and must be greater than 0\. It must be a number of type B..

**返回类型**:以缓冲区的形式返回派生键。

**例 1:**

## app.js

```
// Node.js program to demonstrate the
//  crypto.hkdfSync() Method.

// // Including crypto module 
import crypto from 'crypto'

//Implementing hkdfSync()
const Key = crypto.hkdfSync('sha512', 'key', 'salt', 'info', 64);

// Prints Buffer.
console.log(Key);
```

**输出:**

```
ArrayBuffer {
 [Uint8Contents]: <24 15 6e 2c 35 52 5b 
 aa f3 d0 fb b9 2b 73 4c 80 32 a1 10 a3 f1 2e 
 25 96 e4 41 e1 92 48 70 d8 4c 3a 50 06 52 a7 
 23 73 80 24 43 24 51 04 6f d2 37 ef ad 83 92 
 fb 68 6c 52 77 a5 9e 01 05 39 16 53>,
 byteLength: 64
}
```

**例 2:**

## app . js

```
// Node.js program to demonstrate the
// crypto.hkdfSync() Method.

// Including crypto module 
import crypto from 'crypto'

// Implementing hkdfSync()
const Key = crypto.hkdfSync('sha512', 'key', 'salt', 'info', 16);

// Prints Buffer.
console.log(Buffer.from(Key).toString('hex'));
```

**输出:**

```
24156e2c35525baaf3d0fbb92b734c80
```

**例三:**

## Javascript

```
// Node.js program to demonstrate the
// crypto.hkdfSync() Method.

// Including crypto module 
import crypto from 'crypto'

//Implementing hkdfSync()
const Key = crypto.hkdfSync('sha512', 'key', 'salt', 'info', 32);

// Prints Buffer.
console.log(Buffer.from(Key).toString('base64'));
```

**输出:**

```
JBVuLDVSW6rz0Pu5K3NMgDKhEKPxLiWW5EHhkkhw2Ew=
```

**例 4:**

## Javascript

```
// Node.js program to demonstrate the
// crypto.hkdfSync() Method.

// Including crypto module 
import crypto from 'crypto'

// Implementing hkdfSync()
const Key = crypto.hkdfSync('sha512', 'key', 'salt', 'info', 32);

// Prints Buffer.
console.log(Buffer.from(Key).toString('ascii'));
```

**输出:**

```
$n,5R[*sP{9+sL 2!#q.%dAaHpXL
```

**参考**:[https://nodejs . org/API/crypt . html # crypt _ crypt _ hkdfsync _ digest _ key _ salt _ info _ keylen](https://nodejs.org/api/crypto.html#crypto_crypto_hkdfsync_digest_key_salt_info_keylen)