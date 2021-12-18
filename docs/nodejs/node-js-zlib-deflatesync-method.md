# node . js zlib . pincesync()方法

> 原文:[https://www . geeksforgeeks . org/node-js-zlib-通缩 sync-method/](https://www.geeksforgeeks.org/node-js-zlib-deflatesync-method/)

方法是 zlib 模块的一个内置应用程序编程接口，用于使用 Deflate 压缩一大块数据。

**语法:**

```js
zlib.deflateSync( buffer, options )
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **哥哥哥哥哥哥::t1]嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨 buffer typed array data view array buffer 字符串。**
*   **Option:** This parameter stores the zlib option value.

**返回值:**用 deflate 返回数据块。

以下示例说明了在 Node.js 中使用 **zlib .平减同步()方法**:

**例 1:**

```js
// Node.js program to demonstrate the     
// zlib.deflateSync() method  

// Including zlib module
var zlib = require('zlib');

// Declaring input and assigning
// it a value string
var input = "GfG CS-Portal";

// Calling deflateSync method
var deflated = zlib.deflateSync(input);

console.log(deflated);
```

**输出:**

```js
<Buffer 78 9c 73 4f 73 57 70 0e d6 0d c8 2f 2a 49 cc 01 00 1b 48 04 4a>

```

**例 2:**

```js
// Node.js program to demonstrate the     
// zlib.deflateSync() method  

// Including zlib module
var zlib = require('zlib');

// Declaring input and assigning
// it a value string
var input = "GfG CS-Portal";

// Calling deflateSync method and converting
// the deflate to string encoded with hex
var deflated = zlib.deflateSync(input).toString('hex');

console.log(deflated);
```

**输出:**

```js
789c734f7357700ed60dc82f2a49cc01001b48044a

```

**参考:**T2【https://nodejs . org/API/zlib . html # zlib _ zlib _ pinciesync _ buffer _ options