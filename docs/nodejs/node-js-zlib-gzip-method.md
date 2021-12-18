# Node.js zlib.gzip()方法

> 原文:[https://www.geeksforgeeks.org/node-js-zlib-gzip-method/](https://www.geeksforgeeks.org/node-js-zlib-gzip-method/)

**zlib.gzip()方法**是 zlib 模块的内置应用编程接口，用于压缩一大块数据。

**语法:**

```js
zlib.gzip( buffer, options, callback )
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **Buffer: it can be buffer, type, data view, array buffer and string type.**
***   **option:** is an optional parameter for saving zlib options.*   **Callback:** It holds the callback function.**

****返回值:**返回压缩后的数据块。**

**以下示例说明了 Node.js 中 **zlib.gzip()方法**的使用:**

****例 1:****

 **```js
// Node.js program to demonstrate the     
// gzip() method

// Including zlib module
const zlib = require("zlib");

// Declaring input and assigning
// it a value string
var input = "Geek";

// Calling gzip method
zlib.gzip(input, (err, buffer) => {

  if (!err) {

    console.log(buffer.toString('base64'));
  } 
  else {
    console.log(err);
  }
});
console.log("Data Compressed...");
```** 

****输出:****

```js
Data Compressed...
H4sIAAAAAAAAA3NPTc0GAGGRcasEAAAA 
```

****例 2:****

 **```js
// Node.js program to demonstrate the     
// gzip() method

// Including zlib module
const zlib = require("zlib");

// Declaring input and assigning
// it a value string
var input = "Geek";

// Calling gzip method
zlib.gzip(input, (err, buffer) => {

  if (!err) {

    console.log(buffer.toString('hex'));
  } 
  else {
    console.log(err);
  }
});
console.log("Data Compressed...");
```** 

****输出:****

```js
Hint: hit control+c anytime to enter REPL.
Data Compressed...
1f8b0800000000000003734f4dcd0600619171ab04000000 
```

****参考:**T2】https://nodejs . org/API/zlib . html # zlib _ zlib _ gzip _ buffer _ options _ callback**