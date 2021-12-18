# Node.js ecdh.setPrivateKey()方法

> 原文:[https://www . geesforgeks . org/node-js-ecdh-set private key-method/](https://www.geeksforgeeks.org/node-js-ecdh-setprivatekey-method/)

**ecdh.getPrivateKey()** 方法是加密模块内 ecdh 类的内置应用编程接口，用于设置椭圆曲线 Diffie-Hellman (ECDH)对象的私钥。可以使用*编码*参数指定密钥的编码。

如果私钥对指定曲线无效，将引发错误。使用此方法设置私钥将自动生成并在 ECDH 对象中设置相应的公钥。

**语法:**

```
ecdh.setPrivateKey( privateKey, encoding )
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **私钥:**这是需要设置的私钥。它可以以字符串、数组缓冲区、缓冲区、类型缓冲区或数据视图的格式给出。
*   **编码:** In 编码字符串值，指定返回值的编码。这是一个可选参数。

**返回值:**返回指定编码的椭圆曲线差分赫尔曼公钥。如果不提供编码，则作为缓冲区返回，否则返回字符串。

以下示例演示了这种方法:

**例 1:**

## java 描述语言

```
const crypto = require('crypto');

// Generate an ECDH object for geekA
const geekA = crypto.createECDH('secp521r1');

// Generate an ECDH object for geekB
const geekB = crypto.createECDH('secp521r1');

// Create a private key of geekA
geekA.setPrivateKey("thisisasecretkey!");

// Create a private key of geekB
geekB.setPrivateKey("thisisanotherkey!");

// Get the private keys of both the geeks
let geekAPrivateKey = geekA.getPrivateKey();
let geekBPrivateKey = geekB.getPrivateKey();

console.log("Private Key of Geek A is:",
  geekAPrivateKey);
console.log("Private Key of Geek B is:",
  geekBPrivateKey);
```

**输出:**

> 极客 A 的私钥为: <buffer>极客 B 的私钥为:<缓冲区 74 68 69 73 69 73 61 6e 6f 74 68 65 72 6b 65 79 21></buffer>

**例 2:**

## java 描述语言

```
const crypto = require('crypto');

// Generate an ECDH object for geekA
const geekA = crypto.createECDH('secp521r1');

// Generate an ECDH object for geekB
const geekB = crypto.createECDH('secp521r1');

// Create a private key of geekA
// with "hello" in hex format
geekA.setPrivateKey("68656c6c6f", "hex");

// Create a private key of geekB
// with "world" in base64 format
geekB.setPrivateKey("d29ybGQ=", "base64");

// Get the private keys of both the geeks
// in 'utf-8' encoding
let geekAPrivateKey = 
  geekA.getPrivateKey('utf-8');
let geekBPrivateKey = 
  geekB.getPrivateKey('utf-8');

console.log("Private Key of Geek A is:", 
  geekAPrivateKey);
console.log("Private Key of Geek B is:",
  geekBPrivateKey);
```

**输出:**

```
Private Key of Geek A is: hello
Private Key of Geek B is: world
```

**参考:**[https://nodejs . org/API/crypto . html # crypt _ ecdh _ setprivtekey _ private key _ encoding](https://nodejs.org/api/crypto.html#crypto_ecdh_setprivatekey_privatekey_encoding)