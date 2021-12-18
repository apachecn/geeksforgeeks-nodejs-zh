# Node.js ecdh.getPrivateKey()方法

> 原文:[https://www . geesforgeks . org/node-js-ecdh-getprivate key-method/](https://www.geeksforgeeks.org/node-js-ecdh-getprivatekey-method/)

**ecdh.getPrivateKey()** 方法是加密模块内 ecdh 类的内置应用编程接口，用于获取椭圆曲线 Diffie-Hellman (ECDH)对象的私钥。密钥的编码可以使用*编码*参数指定，格式可以使用*格式*参数指定。

**注意:**必须首先使用 **generateKeys()** 方法生成密钥，然后才能使用私钥检索它们。

**语法:**

```js
ecdh.getPrivateKey( encoding )
```

**参数:**该方法接受如上所述的单个参数，如下所述:

*   **编码:**这是一个字符串值，指定返回值的编码。这是一个可选参数。
*   **格式:**是指定按键格式的字符串。该值可以是“压缩”或“未压缩”。这是一个可选参数。

**返回值:**返回指定编码的椭圆曲线差分赫尔曼私钥。如果不提供编码，则作为缓冲区返回，否则返回字符串。

**下面的例子演示了这种方法:**

**例 1:**

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

// Get the private key for geekA
const geekAprivateKey = geekA.getPrivateKey();

console.log("Private Key of Geek A is:",
  geekAprivateKey);

// Get the private key for geekB
const geekBprivateKey = geekB.getPrivateKey();

console.log("Private Key of Geek B is:",
  geekBprivateKey);
```

**输出:**

> 极客 A 的私钥为: <buffer b1="" cd="" e7="" b4="" a9="" fe="" d8="" d9="" ac="" d0="" d6="" ad="" d3="" a7="" ed="" d5="" e6="" c4="" cb="" more="" bytes="">极客 B 的私钥为:<Buffer 01 2f B2 ea a9 65 23 27 65 be ab 68 3a 6e 88 6e db C4 6a 65 9d 52 B7 9e 69 39 b5 5f 3a 87 55 3d F6 62 51 94 5e 24 48 62 96 DC 3b 4f 10 D2 30 99 03 4c…16 更多字节></buffer>

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

// Get the private key for geekA in base64
const geekAPrivateKey =
  geekA.getPrivateKey('base64');

console.log("Private Key of Geek A is:",
  geekAPrivateKey);

// Get the private key for geekB in hex
const geekBPrivateKey =
  geekB.getPrivateKey('hex');

console.log("Private Key of Geek B is:",
  geekBPrivateKey);
```

**输出:**

> Geek A 的私密金钥是:axzv alaji 4u 5 GL 0h j+kkrinlh45 k+ukizz 27 MD 0x 4 jsbtjeuku 8 vtufvcw 3 alht 4 lit+v1 jp 6f q/4mh 2 dfnlfpu 6
> geek b 的私密金钥是:0152465d 0 c 729 f46 f1 f 78532 FDE 54 EB 0218 b 491 e 5 a 87926120862 b 79

**参考资料:**[https://nodejs . org/API/crypt . html # crypt _ ecdh _ get rivtekey _ encoding](https://nodejs.org/api/crypto.html#crypto_ecdh_getprivatekey_encoding)