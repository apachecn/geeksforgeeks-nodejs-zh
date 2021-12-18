# Node.js zlib.unzipSync()方法

> 原文:[https://www . geesforgeks . org/node-js-zlib-unzipsync-method/](https://www.geeksforgeeks.org/node-js-zlib-unzipsync-method/)

**zlib.unzipSync()方法**是 zlib 模块的内置应用程序编程接口，用于使用 Unzip 解压缩一大块数据。

**语法:**

```js
zlib.unzipSync( buffer, options )
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **Buffer: the type can be buffer, type line, data view, array buffer and string.**
***   **option:** is an optional parameter for saving zlib options.**

****返回值:**用解压返回数据块。**

**以下示例说明了 Node.js 中 **zlib.unzipSync()方法**的使用:**

****例 1:****

 **```js
// Node.js program to demonstrate the     
// zlib.unzipSync() method  

// Including zlib module
var zlib = require('zlib');

// Declaring input and assigning
// it a value string
var input = "NidhiSingh";

// Calling gzipSync method
var gzi = zlib.gzipSync(input);

// Calling unzipSync method
var decom = zlib.unzipSync(
    new Buffer.from(gzi)).toString('base64');

console.log(decom);
```** 

****输出:****

```js
TmlkaGlTaW5naA== 
```

****例 2:****

 **```js
// Node.js program to demonstrate the     
// zlib.unzipSync() method  

// Including zlib module
var zlib = require('zlib');

// Declaring input and assigning
// it a value string
var input = "NidhiSingh";

// Calling gzipSync method
var gzi = zlib.gzipSync(input).toString('hex');

// Calling unzipSync method
var decom = zlib.unzipSync(
    new Buffer.from(gzi, 'hex')).toString('hex');

console.log(decom);
```** 

****输出:****

```js
4e6964686953696e6768 
```

****参考:**[https://nodejs . org/API/zlib . html # zlib _ zlib _ unzipsync _ buffer _ options](https://nodejs.org/api/zlib.html#zlib_zlib_unzipsync_buffer_options)**