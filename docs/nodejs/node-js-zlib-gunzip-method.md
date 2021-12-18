# Node.js zlib.gunzip()方法

> 原文:[https://www.geeksforgeeks.org/node-js-zlib-gunzip-method/](https://www.geeksforgeeks.org/node-js-zlib-gunzip-method/)

**zlib.gunzip()方法**是 zlib 模块的内置应用程序编程接口，用于解压缩一大块数据。

**语法:**

```
zlib.gunzip( buffer, options, callback )
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **Buffer: it can be buffer, type, data view, array buffer and string type.**
***   **option:** is an optional parameter for saving zlib options.*   **Callback:** It holds the callback function.**

****返回值:**解压后返回数据块。**

**以下示例说明了 Node.js 中 **zlib.gunzip()方法**的使用:**

****例 1:****

 **```
// Node.js program to demonstrate the     
// gunzip() method

// Including zlib module
const zlib = require("zlib");

// Declaring input and assigning
// it a value string
var input = "Geek";

// Calling gzip method
zlib.gzip(input, (err, buffer) => {

  // Calling gunzip method
 zlib.gunzip(buffer, (err, buffer) => {

    console.log(buffer.toString('utf8'));

    });
 });

console.log("Data Decompressed...");
```** 

****输出:****

```
Data Decompressed...
Geek 
```

****例 2:****

 **```
// Node.js program to demonstrate the     
// gunzip() method

// Including zlib module
const zlib = require("zlib");

// Declaring input and assigning
// it a value string
var input = "Geek";

// Calling gzip method
zlib.gzip(input, (err, buffer) => {

  // Calling gunzip method
 zlib.gunzip(buffer, (err, buffer) => {

    console.log(buffer.toString('hex'));

    });
 });

console.log("Data Decompressed...");
```** 

****输出:****

```
Data Decompressed...
4765656b 
```

****参考:**[https://nodejs . org/API/zlib . html # zlib _ gunzip _ buffer _ options _ callback](https://nodejs.org/api/zlib.html#zlib_zlib_gunzip_buffer_options_callback)**