# Node.js ecdh.setPublicKey()方法

> 原文:[https://www . geesforgeks . org/node-js-ecdh-set publickey-method/](https://www.geeksforgeeks.org/node-js-ecdh-setpublickey-method/)

**ecdh.getPublicKey()** 方法是加密模块中 ecdh 类的内置应用程序编程接口，用于设置椭圆曲线 Diffie-Hellman (ECDH)对象的公钥。可以使用*编码*参数指定密钥的编码。

通常不需要该方法，因为当应用程序中需要计算共享秘密时，可以使用 **generateKeys()** 和 **setPrivateKey()方法**。如果公共密钥对于指定曲线无效，则会引发错误。

**语法:**

```
ecdh.setPublicKey( publicKey, encoding )
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **公钥:**这是需要设置的公钥。它可以以字符串、数组缓冲区、缓冲区、类型缓冲区或数据视图的格式给出。
*   **编码:**这是一个字符串值，指定返回值的编码。这是一个可选参数。

以下示例演示了这种方法:

**例 1:**

## java 描述语言

```
const crypto = require('crypto');

// Generate an ECDH object for geekOne
const geekOne = crypto.createECDH('secp521r1');

// Generate a temporary ECDH object
// for generating a public key
const tmpECDH = crypto.createECDH('secp521r1');

// Get a temporary public key as a
// Buffer for demonstration
let tempECDHPublicKey = tmpECDH.generateKeys();

// Set the public key to be equal to the
// above generated key in the Buffer format
geekOne.setPublicKey(tempECDHPublicKey);

// Get the public key that was set
let geekOnePublicKey = geekOne.getPublicKey();

console.log("Public Key of Geek A is:",
  geekOnePublicKey);
```

**输出:**

> 极客一号的公钥是:

**示例 2:** 在本例中，生成的关键点是不同的曲线。因此，当使用此方法设置此键时，它会抛出一个错误，因为它与 ECDH 对象的曲线不匹配。

## java 描述语言

```
const crypto = require('crypto');

// Generate an ECDH object for geekOne
const geekOne = crypto.createECDH('secp521r1');

// Generate a key with the encryption
// type as SHA256
let hashObj = crypto.createHash('sha256');
let tempPublicKey =
  hashObj.update('thisisapublickey', 'utf8').digest();

// Display the generated key
console.log("The generated key is:", tempPublicKey);

// Attempt to set the public key to
// be equal to the above generated key
geekOne.setPublicKey(tempPublicKey);
```

**输出:**

> 生成的密钥为: <buffer a7="" de="" ff="" a0="" e1="" eb="" fe="" d6="" a6="" b1="">节点:内部/加密/diffihellman:231
> 本【kHandle】。setPublicKey(键)；
> ^
> 错误:无法在 ECDH.setPublicKey 处将缓冲区转换为 EC_POINT
> (节点:内部/加密/diffiehllman:231:17)
> 在对象处。<匿名>(G:\ tutorials \ ecdh-setPublicKey \ ex2 . js:16:9)
> at Module。_ 编译(节点:内部/模块/cjs/加载器:1095:14)
> 在对象.模块. _ 扩展..js(节点:内部/模块/cjs/加载器:1124:10)
> at Module.load(节点:内部/模块/cjs/加载器:975:32)
> at function . module . _ load(节点:内部/模块/cjs/加载器:816:12)
> at function . executeuserentrypoint[as runMain](节点:内部/模块/run_main:79:12)
> at 节点:内部/main/run _ run</buffer>

**参考:**[https://nodejs . org/API/crypto . html # crypt _ ecdh _ setppublicy _ public key _ encoding](https://nodejs.org/api/crypto.html#crypto_ecdh_setpublickey_publickey_encoding)