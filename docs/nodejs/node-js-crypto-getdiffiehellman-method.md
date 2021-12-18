# node . js crypto . getdiffihellman()方法

> 原文:[https://www . geesforgeks . org/node-js-crypto-getdiffihellman-method/](https://www.geeksforgeeks.org/node-js-crypto-getdiffiehellman-method/)

**crypto . getdiffeiehellman()方法**用于创建预定义的**diffeiehellmangroup**密钥交换对象。这里，受青睐的群体是 RFC 2412 中定义的‘mod P1’、‘mod p2’、‘mod P5’和 RFC 3526 中定义的‘mod p14’、‘mod p15’、‘mod p16’、‘mod P17’、‘mod p18’。

**语法:**

```
crypto.getDiffieHellman( groupName )
```

**参数:**该方法接受单参数**组名**，类型为字符串。

**返回类型:**返回**差分 HellmanGroup** 密钥交换对象。

以下示例说明了在 Node.js 中使用**crypto . getdiffihellman()方法**:

**例 1:**

```
// Node.js program to demonstrate the 
// crypto.getDiffieHellman() method

// Including crypto module
const crypto = require('crypto');

// Calling getDiffieHellman method
// with its parameter groupName
const diffiehellmangrp = crypto.getDiffieHellman('modp14');

// Prints DiffieHellmanGroup key exchange object
console.log("Key exchange object : ", diffiehellmangrp);
```

**输出:**

```
Key exchange object :  DiffieHellmanGroup 
{ _handle: { verifyError: [Getter] }, verifyError: 0 }
```

**例 2:**

```
// Node.js program to demonstrate the 
// crypto.getDiffieHellman() method

// Including crypto module
const crypto = require('crypto');

// Calling two getDiffieHellman method
// with its parameter, groupName
const diffiehellmangrp1 = crypto.getDiffieHellman('modp14');
const diffiehellmangrp2 = crypto.getDiffieHellman('modp14');

// Generating keys
diffiehellmangrp1.generateKeys();
diffiehellmangrp2.generateKeys();

// Computing secret
const diffiehellmangrp1sc = diffiehellmangrp1
.computeSecret(diffiehellmangrp2.getPublicKey(), null, 'hex');

const diffiehellmangrp2sc = diffiehellmangrp2
.computeSecret(diffiehellmangrp1.getPublicKey(), null, 'hex');

// Checking if both the secrets are same or not
console.log(diffiehellmangrp1sc === diffiehellmangrp2sc);
```

**输出:**

```
true
```

**参考:**[https://nodejs . org/API/crypt . html # crypt _ crypt _ getdifllman _ group name](https://nodejs.org/api/crypto.html#crypto_crypto_getdiffiehellman_groupname)