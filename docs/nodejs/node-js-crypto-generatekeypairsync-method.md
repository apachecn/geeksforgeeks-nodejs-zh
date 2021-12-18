# node . js crypto . generatekeypairsync()方法

> 原文:[https://www . geesforgeks . org/node-js-crypto-generatekeypairsync-method/](https://www.geeksforgeeks.org/node-js-crypto-generatekeypairsync-method/)

**crypto.generateKeyPairSync()方法**是加密模块的内置应用编程接口，用于生成指定类型的新非对称密钥对。例如，当前支持的密钥类型有 RSA、DSA、EC、Ed25519、Ed448、X25519、X448 和 DH。此外，如果在这里声明了选项的 publicKeyEncoding 或 privateKeyEncoding，那么这个函数的行为就像在其输出中调用了 keyObject.export()一样。否则，密钥的特定部分将作为密钥对象返回。
但是，建议使用强密码将公钥编码为“spki”，将私钥编码为“pkcs8”，以便对密码保密。

**语法:**

```
crypto.generateKeyPairSync( type, options )
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **类型:**它保存一个字符串，并且必须包含以下一个或多个算法:*‘RSA’‘DSA’‘EC’‘ed 25519’‘ed 448’‘x 25519’‘x448’或‘DH’*。
*   **选项:**为对象类型。它可以保存以下参数:
    1.  **modulusLength:** 它保存一个数字。它是以位为单位的密钥大小，仅适用于 RSA 和 DSA 算法。
    2.  **public index:**它保存一个数字。它是 RSA 算法的公开指数。其默认值为 0x10001。
    3.  **除数长度:**它保存一个数字。这是数字减影算法中 *q* 的大小。
    4.  **namedCurve:** 它保存一个字符串。它是用于 EC 算法的曲线的名称。
    5.  **prime:** 它保存一个缓冲区。它是 DH 算法的首要参数。
    6.  **质数长度:**它保存一个数字。它是 DH 算法的质数长度，以位为单位。
    7.  **发生器:**它保存一个数字。是 DH 算法的自定义生成器。它的默认值是 2。
    8.  **groupName:** 保存字符串。是 DH 算法的 Diffie-Hellman 组名。
    9.  **publicKeyEncoding:** 它保存一个字符串。
    10.  **privateKeyEncoding:** 它保存一个对象。

**返回值:**它返回一个给定类型的新的非对称密钥对，即它返回一个包含私钥和公钥的对象，公钥保存字符串、缓冲区和密钥对象。

以下示例说明了在 Node.js 中使用 **crypto.generateKeyPairSync()方法**:

**例 1:**

```
// Node.js program to demonstrate the
// crypto.generateKeyPairSync() method

// Including generateKeyPairSync from crypto module
const { generateKeyPairSync } = require('crypto');

// Including publicKey and  privateKey from 
// generateKeyPairSync() method with its 
// parameters
const { publicKey, privateKey } = generateKeyPairSync('ec', {
  namedCurve: 'secp256k1',    // Options
  publicKeyEncoding: {
    type: 'spki',
    format: 'der'
  },
  privateKeyEncoding: {
    type: 'pkcs8',
    format: 'der'
  }
});

// Prints asymmetric key pair
console.log("The public key is: ", publicKey);
console.log();
console.log("The private key is: ", privateKey);
```

**输出:**

```
The public key is: <Buffer 30 56 30 10 06 07
2a 86 48 ce 3d 02 01 06 052b 81 04 00 0a 03 42
00 04 d9 88 53 5b 21 84 f8 73 14 c8 0b 31 e2 2a
28 a5 4c 8f 68 23 65 84 d9 fe 20 3f ... >

The private key is:  Buffer 30 81 84 02 01 00 30
10 06 07 2a 86 48 ce 3d 02 01 06 05 2b 81 04 00
0a 04 6d 30 6b 02 01 01 04 20 50 4a 87 c3 8c
968f 2b 41 f8 66 99 8a 95 ae 45 75 ... >

```

**例 2:**

```
// Node.js program to demonstrate the
// crypto.generateKeyPairSync() method

// Including generateKeyPairSync from crypto module
const { generateKeyPairSync } = require('crypto');

// Including publicKey and  privateKey from 
// generateKeyPairSync() method with its 
// parameters
const { publicKey, privateKey } = generateKeyPairSync('dsa', {
  modulusLength: 570,
  publicKeyEncoding: {
    type: 'spki',
    format: 'der'
  },
  privateKeyEncoding: {
    type: 'pkcs8',
    format: 'der'
  }
});

// Prints asymmetric key pair after encoding
console.log("The public key is: ", 
         publicKey.toString('base64'));
console.log();
console.log("The private key is: ",
         privateKey.toString('base64'));
```

**输出:**

```
The public key is:  MIIBETCBwAYHKoZIzjgEATCBtAJJAM6084jk1Y6s/0sWQCs3k59AjV1GgAHb8gmB+Lxd/YVid+GySyss8tqhVQl49xho1DHoeJMNsVO6mcRqaSlSCPgmzqGaOvn2mQIdAKL5nGKJjDZF8Pb1SVvwWivhPShJiiHC2JjgrN8CSAqhzmg26/kEHYTZ3yNEGuguDhLvMAPdVG9pjTahLBytn8JQa3yQwLuPB4MzKfJ4d0pvKVZVnkMsatUe2ZkjnKoCjGlzwggd+QNMAAJJAMvsOBUjUKLhpkw4FZP7LIz0yYyOV1yYy84t8qSO42Yf6sNUfK6INnkFbpLHjFLcaDkFPqE5oRCIUqIVOhH0I7jNcGCN2m+ZWg==

The private key is:  MIHnAgEAMIHABgcqhkjOOAQBMIG0AkkAzrTziOTVjqz/SxZAKzeTn0CNXUaAAdvyCYH4vF39hWJ34bJLKyzy2qFVCXj3GGjUMeh4kw2xU7qZxGppKVII+CbOoZo6+faZAh0AovmcYomMNkXw9vVJW/BaK+E9KEmKIcLYmOCs3wJICqHOaDbr+QQdhNnfI0Qa6C4OEu8wA91Ub2mNNqEsHK2fwlBrfJDAu48HgzMp8nh3Sm8pVlWeQyxq1R7ZmSOcqgKMaXPCCB35BB8CHQChh8yXsr/3dx3OdV6JmIWPcHe6dTHh6IOEIHer
```

这里使用的是“dsa”键类型。

**参考:**[https://nodejs . org/API/crypt . html # crypt _ crypt _ generate keypair _ type _ options](https://nodejs.org/api/crypto.html#crypto_crypto_generatekeypairsync_type_options)