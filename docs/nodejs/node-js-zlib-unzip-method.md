# Node.js zlib.unzip()方法

> 原文:[https://www.geeksforgeeks.org/node-js-zlib-unzip-method/](https://www.geeksforgeeks.org/node-js-zlib-unzip-method/)

**zlib.unzip()方法**是 zlib 模块的内置应用程序编程接口，用于解压缩一大块数据。

**语法:**

```js
zlib.unzip( buffer, options, callback )
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **Buffer: it can be buffer, type, data view, array buffer and string type.**
***   **option:** is an optional parameter for saving zlib options.*   **Callback:** It holds the callback function.**

****返回值:**解压后返回数据块。**

**下面的例子说明了在 Node.js 中使用 **zlib.unzip()方法**:**

****例 1:****

 **```js
// Node.js program to demonstrate the     
// unzip() method

// Including zlib module
const zlib = require("zlib");

// Declaring input and assigning
// it a value string
var input = "GfG";

// Calling gzip method
zlib.gzip(input, (err, buffer) => {

  // Calling unzip method
 zlib.unzip(buffer, (err, buffer) => {

    console.log(buffer.toString('utf8'));

    });
 });

console.log("Data Decompressed...");
```** 

****输出:****

```js
Data Decompressed...
GfG 
```

****例 2:****

 **```js
// Node.js program to demonstrate the     
// unzip() method

// Including zlib module
const zlib = require("zlib");

// Declaring input and assigning
// it a value string
var input = "GfG";

// Calling gzip method
zlib.gzip(input, (err, buffer) => {

  // Calling unzip method
 zlib.unzip(buffer, (err, buffer) => {

    console.log(buffer.toString('base64'));

    });
 });

console.log("Data Decompressed...");
```** 

****输出:****

```js
Data Decompressed...
R2ZH 
```

****参考:**T2】https://nodejs . org/API/zlib . html # zlib _ zlib _ unzip _ buffer _ options _ callback**