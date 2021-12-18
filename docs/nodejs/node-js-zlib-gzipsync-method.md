# Node.js zlib.gzipSync()方法

> 原文:[https://www.geeksforgeeks.org/node-js-zlib-gzipsync-method/](https://www.geeksforgeeks.org/node-js-zlib-gzipsync-method/)

**zlib.gzipSync()方法**是 zlib 模块的内置应用编程接口，用于使用 Gzip 压缩一大块数据。

**语法:**

```js
zlib.gzipSync( buffer, options )
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **哥哥哥哥哥哥::t1]嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨 buffer typed array data view array buffer 字符串。**
*   **Option:** This parameter stores the zlib option value.

**返回值:**用 Gzip 返回数据块。

以下示例说明了在 Node.js 中使用 **zlib.gzipSync()方法**:

**例 1:**

```js
// Node.js program to demonstrate the     
// zlib.gzipSync() method  

// Including zlib module
var zlib = require('zlib');

// Declaring input and assigning
// it a value string
var input = "Nidhi";

// Calling brotliDecompressSync method
var gzi = zlib.gzipSync(input);

console.log(gzi);
```

**输出:**

```js
<Buffer 1f 8b 08 00 00 00 00 00 00 03 f3 cb
    4c c9 c8 04 00 13 f2 5b b1 05 00 00 00>

```

**例 2:**

```js
// Node.js program to demonstrate the     
// zlib.gzipSync() method  

// Including zlib module
var zlib = require('zlib');

// Declaring input and assigning
// it a value string
var input = "Nidhi";

// Calling brotliDecompressSync method
var gzi = zlib.gzipSync(input).toString('hex');

console.log(gzi);
```

**输出:**

```js
1f8b0800000000000003f3cb4cc9c8040013f25bb105000000
```

**参考:**[https://nodejs . org/API/zlib . html # zlib _ zlib _ gzip sync _ buffer _ options](https://nodejs.org/api/zlib.html#zlib_zlib_gzipsync_buffer_options)