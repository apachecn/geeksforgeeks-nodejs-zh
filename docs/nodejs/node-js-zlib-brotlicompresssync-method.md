# node . js zlib . brotlicompresssync()方法

> 原文:[https://www . geesforgeks . org/node-js-zlib-brotlicompresssync-method/](https://www.geeksforgeeks.org/node-js-zlib-brotlicompresssync-method/)

**zlib . brotlicompresssync()**方法是 Zlib 模块的内置应用编程接口，用于使用 BrotliCompress 压缩一大块数据。

**语法:**

```
zlib.brotliCompressSync( buffer, options )
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **哥哥哥哥哥哥::t1]嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨 buffer typed array data view array buffer 字符串。**
*   **option:** is an optional parameter.

**返回值:**用 BrotliCompress 返回数据块。

以下示例说明了在 Node.js 中使用 **zlib.brotliCompressSync()方法**:

**例 1:**

```
// Node.js program to demonstrate the     
// zlib.brotliCompressSync() method  

// Including zlib module
var zlib = require('zlib');

// Declaring input and assigning
// it a value string
var input = "0123456789";

// Calling brotliCompressSync method
var brotliCom = zlib.brotliCompressSync(input);

console.log(brotliCom);
```

**输出:**

```
// Buffer 8b 04 80 30 31 32 33 34 35 36 37 38 39 03

```

**例 2:**

```
// Node.js program to demonstrate the     
// zlib.brotliCompressSync() method  

// Including zlib module
var zlib = require('zlib');

// Declaring input and assigning
// it a value string
var input = "0123456789";

// Calling brotliCompressSync method
var brotliCom = zlib.brotliCompressSync(input).toString('hex');

console.log(brotliCom);
```

**输出:**

```
8b04803031323334353637383903

```

**参考资料:**[https://nodejs . org/API/zlib . html # zlib _ zlib _ bromless compression _ buffer _ options](https://nodejs.org/api/zlib.html#zlib_zlib_brotlicompresssync_buffer_options)