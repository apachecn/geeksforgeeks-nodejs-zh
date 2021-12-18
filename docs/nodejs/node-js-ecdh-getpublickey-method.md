# Node.js ecdh.getPublicKey()方法

> 原文:[https://www . geesforgeks . org/node-js-ecdh-getpublikey-method/](https://www.geeksforgeeks.org/node-js-ecdh-getpublickey-method/)

**ecdh.getPublicKey()** 方法是加密模块中 ecdh 类的内置应用程序编程接口，用于获取指定编码的椭圆曲线 Diffie-Hellman (ECDH)对象的公钥。密钥的编码可以使用*编码*参数指定，格式可以使用*格式*参数指定。

必须首先使用 **generateKeys()** 方法生成密钥，然后才能使用公钥检索它们。

**语法:**

```js
ecdh.getPublicKey( encoding, format )
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **编码:**这是一个字符串值，指定返回值的编码。
*   **格式:**是指定按键格式的字符串。该值可以是“压缩”或“未压缩”。

**返回值:**返回指定编码的椭圆曲线差分赫尔曼公钥。如果不提供编码，则作为缓冲区返回，否则返回字符串。

**实施例 1:** 以下实施例说明了该方法:

## java 描述语言

```js
const crypto = require('crypto');

// Generate an ECDH object for geekA
const geekA = crypto.createECDH('secp521r1');

// Generate an ECDH object for geekB
const geekB = crypto.createECDH('secp521r1');

// Generate the keys for both the geeks
geekA.generateKeys();
geekB.generateKeys();

// Get the public key for geekA
const geekAPublicKey = geekA.getPublicKey();

console.log("Public Key of Geek A is:", geekAPublicKey);

// Generate keys for geekB
const geekBPublicKey = geekB.getPublicKey();

console.log("Public Key of Geek B is:", geekBPublicKey);
```

**输出:**

> 极客 A 的公钥为: <buffer d4="" a4="" ef="" a2="" e6="" bd="" a6="" fe="" a7="" e2="" e7="" ce="" ae="" cc="" f3="" ad="" ab="" more="" bytes="">极客 B 的公钥为:<Buffer 04 01 03 2c 43 12 21 39 D2 D5 E8 DC BF F7 C6 cf B2 a3 15 62 00 47 50 83 2e 22 ce 54 20 13 DD fa D2 0c 0f 31 Fe B0 C5 1f af 65 a1 d0 B0 49 66 42 61 99…83 更多字节></buffer>

**例 2:**

## java 描述语言

```js
const crypto = require('crypto');

// Generate an ECDH object for geekA
const geekA = crypto.createECDH('secp521r1');

// Generate an ECDH object for geekB
const geekB = crypto.createECDH('secp521r1');

// Generate the keys for both the geeks
geekA.generateKeys();
geekB.generateKeys();

// Get the public key for geekA in base64
const geekAPublicKey = 
  geekA.getPublicKey('base64');

console.log(
  "Public Key of Geek A is:", geekAPublicKey);

// Generate keys for geekB in hex in
// the compressed format
const geekBPublicKey =
  geekB.getPublicKey('hex', 'compressed');

console.log(
  "Public Key of Geek B is:", geekBPublicKey);
```

**输出:**

> Geek A 的公开密钥是:bacc 88 Lu 8 xdew 2 wuiluluckcch 0 kqc 79 lilcyuj 92 auutiymp 3 cfstcd 5 gfkbf 329 L2 wbzr 4 xwugqxagye 6 isnanamoxs 2u 4eo 3 nscmsi 2+bxssjhykim 8 njqn m7vgsq 4 d0 fpmgnwgfcjoo+v 0 vbb 3 zvepfswkwyti 0 wlf 7kxa = = t0]公开

**参考:**[https://nodejs . org/API/crypto . html # crypt _ ecdh _ get publicly _ encoding _ format](https://nodejs.org/api/crypto.html#crypto_ecdh_getpublickey_encoding_format)