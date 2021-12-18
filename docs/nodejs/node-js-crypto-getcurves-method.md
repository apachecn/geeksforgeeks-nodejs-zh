# Node.js crypto.getCurves()方法

> 原文:[https://www . geesforgeks . org/node-js-crypto-get curves-method/](https://www.geeksforgeeks.org/node-js-crypto-getcurves-method/)

**crypto.getCurves()方法**是加密模块的内置应用编程接口，用于显示一个数组，该数组包含所有支持的椭圆曲线的名称。

**语法:**

```js
crypto.getCurves()
```

**参数:**此方法不接受任何参数。

**返回值:**该方法返回所有支持的椭圆曲线的名称。

下面的例子说明了在 Node.js 中 **crypto.getCurves()方法**的使用:

**例:**

```js
// Node.js program to demonstrate the 
// crypto.getCurves() method

// Including crypto module
const crypto = require('crypto');

// Calling getCurves method
const curve = crypto.getCurves();

// Prints all the supported elliptic curves
console.log("The list of all the elliptic curves are : ", curve);
```

**输出:**

```js
The list of all the elliptic curves are :  [ 'Oakley-EC2N-3',
  'Oakley-EC2N-4',
  'SM2',
  'brainpoolP160r1',
  'brainpoolP160t1',
  'brainpoolP192r1',
  'brainpoolP192t1',
  'brainpoolP224r1',
  'brainpoolP224t1',
  'brainpoolP256r1',
  'brainpoolP256t1',
  'brainpoolP320r1',
  'brainpoolP320t1',
  'brainpoolP384r1',
  'brainpoolP384t1',
  'brainpoolP512r1',
  'brainpoolP512t1',
  'c2pnb163v1',
  'c2pnb163v2',
  'c2pnb163v3',
  'c2pnb176v1',
  'c2pnb208w1',
  'c2pnb272w1',
  'c2pnb304w1',
  'c2pnb368w1',
  'c2tnb191v1',
  'c2tnb191v2',
  'c2tnb191v3',
  'c2tnb239v1',
  'c2tnb239v2',
  'c2tnb239v3',
  'c2tnb359v1',
  'c2tnb431r1',
  'prime192v1',
  'prime192v2',
  'prime192v3',
  'prime239v1',
  'prime239v2',
  'prime239v3',
  'prime256v1',
  'secp112r1',
  'secp112r2',
  'secp128r1',
  'secp128r2',
  'secp160k1',
  'secp160r1',
  'secp160r2',
  'secp192k1',
  'secp224k1',
  'secp224r1',
  'secp256k1',
  'secp384r1',
  'secp521r1',
  'sect113r1',
  'sect113r2',
  'sect131r1',
  'sect131r2',
  'sect163k1',
  'sect163r1',
  'sect163r2',
  'sect193r1',
  'sect193r2',
  'sect233k1',
  'sect233r1',
  'sect239k1',
  'sect283k1',
  'sect283r1',
  'sect409k1',
  'sect409r1',
  'sect571k1',
  'sect571r1',
  'wap-wsg-idm-ecid-wtls1',
  'wap-wsg-idm-ecid-wtls10',
  'wap-wsg-idm-ecid-wtls11',
  'wap-wsg-idm-ecid-wtls12',
  'wap-wsg-idm-ecid-wtls3',
  'wap-wsg-idm-ecid-wtls4',
  'wap-wsg-idm-ecid-wtls5',
  'wap-wsg-idm-ecid-wtls6',
  'wap-wsg-idm-ecid-wtls7',
  'wap-wsg-idm-ecid-wtls8',
  'wap-wsg-idm-ecid-wtls9' ]

```

**参考:**[https://nodejs . org/API/crypt . html # crypt _ crypt _ getcurves](https://nodejs.org/api/crypto.html#crypto_crypto_getcurves)