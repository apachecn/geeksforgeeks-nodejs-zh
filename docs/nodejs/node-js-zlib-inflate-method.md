# node . js zlib . explain()方法

> 原文:[https://www.geeksforgeeks.org/node-js-zlib-inflate-method/](https://www.geeksforgeeks.org/node-js-zlib-inflate-method/)

方法是 zlib 模块的一个内置应用编程接口，用于解压缩一大块数据。

**语法:**

```js
zlib.inflate( buffer, options, callback )
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **Buffer: it can be buffer, type, data view, array buffer and string type.**
***   **option:** is an optional parameter for saving zlib options.*   **Callback:** It holds the callback function.**

****返回值:**解压后返回数据块。**

**以下示例说明了在 Node.js 中使用**zlib . explain()方法**:**

****例 1:****

 **```js
// Node.js program to demonstrate the     
// inflate() method

// Including zlib module
const zlib = require("zlib");

// Declaring input and assigning
// it a value string
var input = "Geeks";

// Calling deflate method
zlib.deflate(input, (err, buffer) => {

  // Calling inflate method
  zlib.inflate(buffer, (err, buffer) => {
    console.log(buffer.toString('utf8'));
  });
});
```** 

****输出:****

```js
Geeks 
```

****例 2:****

 **```js
// Node.js program to demonstrate the     
// inflate() method

// Including zlib module
const zlib = require("zlib");

// Declare input and assign
// it a value string
var input = "Nidhi Singh";

// Calling deflate method
zlib.deflate(input, (err, buffer) => {

  // Calling inflate method
  zlib.inflate(buffer, (err, buffer) => {
    console.log(buffer.toString('hex'));
  });
});
```** 

****输出:****

```js
4e696468692053696e6768 
```

****参考:**[https://nodejs . org/API/zlib . html # zlib _ zlib _ explain _ buffer _ options _ callback](https://nodejs.org/api/zlib.html#zlib_zlib_inflate_buffer_options_callback)**