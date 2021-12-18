# Node.js ecdh.generateKeys()方法

> 原文:[https://www . geesforgeks . org/node-js-ecdh-generatekeys-method/](https://www.geeksforgeeks.org/node-js-ecdh-generatekeys-method/)

**ecdh.generateKeys()** 方法是加密模块中 ecdh 类的内置应用程序编程接口，用于生成椭圆曲线 Diffie-Hellman (ECDH)对象的私钥和公钥值。它只返回给定格式和编码的公钥。

**语法:**

```
ecdh.generateKeys( encoding, format )
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **编码:**这是一个字符串值，指定返回值的编码。
*   **格式:**是指定按键格式的字符串。该值可以是“压缩”或“未压缩”。

**返回值:**返回指定编码的椭圆曲线差分赫尔曼公钥。如果没有提供编码，则作为缓冲区返回，否则返回字符串。

以下示例演示了这种方法:

**例 1:**

## java 描述语言

```
const crypto = require('crypto');

// Generate an ECDH object for geekA
const geek = crypto.createECDH('secp521r1');

// Generate keys for geek and return
// the public key
const geekAPublicKey = geek.generateKeys();

console.log(
  "Public Key of Geek A is:", geekAPublicKey);

// Get the private key of geek
const geekAPrivateKey = geek.getPrivateKey();
console.log(
  "Private Key of Geek A is:", geekAPrivateKey);
```

**输出:**

> 极客 A 的公钥为: <buffer e4="" ad="" d9="" a4="" a6="" e3="" db="" a9="" dc="" c8="" c9="" bb="" de="" b7="" c4="" c6="" f9="" e7="" more="" bytes="">极客 A 的私钥为:<Buffer 01 8f af 82 49 30 70 E0 47 1f 46 7d 3 99 50 8b 14 47 97 04 9d 3e 46 C7 B1 8e D1 C1 ad 6f de ea C7 A0 BC A8 af F2 C3 E0 46 df 74 BF 07 a3 36 a2 AC…16 更多字节></buffer>

**例 2:**

## java 描述语言

```
const crypto = require('crypto');

// Generate an ECDH object for geekA
const geekA = crypto.createECDH('secp521r1');

// Generate keys for geekA in base64 encoding
const geekAkey =
  geekA.generateKeys('base64');

console.log(
  "Public Key of Geek A is:", geekAkey);

// Generate an ECDH object for geekB
const geekB = crypto.createECDH('secp521r1');

// Generate keys for geekB in base64
// encoding and compressed
const geekBkey =
  geekB.generateKeys('base64', 'compressed');

console.log(
  "Public Key of Geek B is:", geekBkey);
```

**输出:**

> geek a is:bahbkh 6 uv 0 hazphqr+bva/GC 8 vrqtf 0 ltpnweoph+pdklhhhne 9/xyi2 pjdq 1 nhum/gekojksmead 51 q 0 ehge 2y+iihb 2 gsluy 7ho 0 oomlfrlm 8y paxnv 6 skbqsbngnyh/hebilillznfgurnsvsh 4 Rui 0 useoh/V6 nfpefua = =
> geek 的公钥

**参考:**[https://nodejs . org/API/crypt . html # crypt _ ecdh _ generate keys _ encoding _ format](https://nodejs.org/api/crypto.html#crypto_ecdh_generatekeys_encoding_format)