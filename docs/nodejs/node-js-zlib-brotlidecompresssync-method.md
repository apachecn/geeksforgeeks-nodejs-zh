# node . js zlib . brotlidecompresssync()方法

> 原文:[https://www . geesforgeks . org/node-js-zlib-brotlidecompresssync-method/](https://www.geeksforgeeks.org/node-js-zlib-brotlidecompresssync-method/)

**zlib.brotliDecompressSync()方法**是 zlib 模块的内置应用程序编程接口，用于使用 BrotliDecompress 解压缩数据块。

**语法:**

```
zlib.brotliDecompressSync( buffer, options )
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **哥哥哥哥哥哥::t1]嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨 buffer typed array data view array buffer 字符串。**
*   **Option:** This parameter stores the zlib option value.

**返回值:**用 BrotliDecompress 返回数据块。

以下示例说明了在 Node.js 中使用 **zlib.brotliDecompressSync()方法**:

**例 1:**

```
// Node.js program to demonstrate the     
// zlib.brotliDecompressSync() method  

// Including zlib module
var zlib = require('zlib');

// Declaring input and assigning
// it a value string
var input = "Nidhi";

// Calling brotliDecompressSync method
var brotliCom = zlib.brotliCompressSync(input);
var brotliDec = zlib.brotliDecompressSync(
    new Buffer.from(brotliCom)).toString('hex');

console.log(brotliDec);
```

**输出:**

```
4e69646869
```

**例 2:**

```
// Node.js program to demonstrate the     
// zlib.brotliDecompressSync() method  

// Including zlib module
var zlib = require('zlib');

// Declaring input and assigning
// it a value string
var input = "Nidhi";

// Calling brotliDecompressSync method
var brotliCom = zlib.brotliCompressSync(input).toString('hex')
var brotliDec = zlib.brotliDecompressSync(
    new Buffer.from(brotliCom, 'hex')).toString('base64');

console.log(brotliDec);
```

**输出:**

```
TmlkaGk=
```

**参考:**T2【https://nodejs . org/API/zlib . html # zlib _ zlib _ brotlidecompresssync _ buffer _ options