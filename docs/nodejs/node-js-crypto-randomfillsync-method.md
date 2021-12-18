# node . js crypto . randomfillsync()方法

> 原文:[https://www . geesforgeks . org/node-js-crypto-randomfillsync-method/](https://www.geeksforgeeks.org/node-js-crypto-randomfillsync-method/)

**crypto.randomFillSync()方法**是加密模块的内置应用编程接口，用于返回作为*缓冲区*参数传递的对象。
**语法:**

```js
crypto.randomFillSync( buffer, offset, size )
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **缓冲区**该参数保存缓冲区、数据类型或数据视图类型的数据。
*   **偏移量:**是默认值为 0 的数字。
*   **大小:**是一个数字，默认值为**(buffer . length–offset)**。

**返回值:**返回*缓冲区、类型数据或数据视图*类型的数据。
以下示例说明了 **crypto.randomFillSync()方法**在 Node.js:
**示例 1:**
中的使用

## java 描述语言

```js
// Node.js program to demonstrate the 
// crypto.randomFillSync() method

// Including crypto module
const crypto = require('crypto');

// Defining buffer
const buffer = Buffer.alloc(15);

// Calling randomFillSync method with only 
// one parameter, buffer
console.log(crypto.randomFillSync(buffer).toString('ascii'));

// Calling randomFillSync method with 
// two parameters, buffer and offset
crypto.randomFillSync(buffer, 4);
console.log(buffer.toString('base64'));

// Calling randomFillSync method with three 
// parameters, buffer, offset and size
crypto.randomFillSync(buffer, 4, 4);
console.log(buffer.toString('base64'));
```

**输出:**

```js
+~`Ld#%KT&6VF1e
K/7gTBXCFISh30dPoE5o
K/7gTO7iUG+h30dPoE5o
```

这里，最后两个值是相同的。
**例 2:**

## java 描述语言

```js
// Node.js program to demonstrate the 
// crypto.randomFillSync() method

// Including crypto module
const crypto = require('crypto');

// Creating TypedArray instance i.e, Int8Array
const x = new Int8Array(5);

// Calling randomFillSync with all its parameter
console.log(Buffer.from(crypto.randomFillSync(x).buffer,
         x.byteOffset, x.byteLength).toString('base64'));

console.log();

// Creating TypedArray instance i.e, BigInt64Array
const y = new BigInt64Array(4);
console.log(Buffer.from(crypto.randomFillSync(y).buffer,
          y.byteOffset, y.byteLength).toString('ascii'));
console.log();

// Creating a DataView instance
const z = new DataView(new ArrayBuffer(7));
console.log(Buffer.from(crypto.randomFillSync(z).buffer,
            z.byteOffset, z.byteLength).toString('hex'));
```

**输出:**

```js
BQrDFc8=

EM4;)N+.qY, o-kp:b:C.

479eb4d9175221
```

这里，任何*类型的 dArray 或 DataView* 实例都作为缓冲区传递。
**参考:**[https://nodejs . org/API/crypto . html # crypto _ crypto _ randomfillsync _ buffer _ offset _ size](https://nodejs.org/api/crypto.html#crypto_crypto_randomfillsync_buffer_offset_size)