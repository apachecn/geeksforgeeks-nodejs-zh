# Node.js crypto.webcrypto 属性

> 原文:[https://www . geesforgeks . org/node-js-crypto-web crypto-property/](https://www.geeksforgeeks.org/node-js-crypto-webcrypto-property/)

**crypto.webcrypto** 是加密模块内一个内置的加密类应用编程接口，用于获取 Web Crypto API 标准的加密对象。

**语法:**

```js
const crypto.webcrypto
```

**参数:**该属性不接受任何参数。

**返回值**:该属性返回 Web Crypto API 标准的加密对象。

**例 1:**

## index.js

```js
// Node.js program to demonstrate the  
// crypto.webcrypto function

// Importing crypto module
const crypto = require('crypto')

// getting object of crypto 
// by using webcrypto function
const val = crypto.webcrypto

const buffer  = new ArrayBuffer(8)

//display the result
console.log(val.getRandomValues(Int16Array.of(buffer)))
```

使用以下命令运行 index.js 文件。

```js
node index.js
```

**输出:**

```js
Int16Array(1) [ 31796 ]
```

**例 2:**

## index . js

```js
// Node.js program to demonstrate the  
// crypto.webcrypto function

//display the result
console.log((require('crypto').webcrypto)
.getRandomValues(Int16Array.of(new ArrayBuffer(8))))
```

使用以下命令运行 index.js 文件。

```js
node index.js
```

**输出:**

```js
Int16Array(1) [ -6968 ]
```

**参考**:[https://nodejs . org/dist/latest-v 15 . x/docs/API/crypto . html # crypto _ crypto _ web crypto](https://nodejs.org/dist/latest-v15.x/docs/api/crypto.html#crypto_crypto_webcrypto)