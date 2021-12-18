# Node.js zlib.brotliCompress()方法

> 原文:[https://www . geesforgeks . org/node-js-zlib-brot licompress-method/](https://www.geeksforgeeks.org/node-js-zlib-brotlicompress-method/)

方法是 zlib 模块的内置应用编程接口，用于压缩一大块数据。

**语法:**

```js
zlib.brotliCompress( buffer, options, callback )
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **Buffer: it can be buffer, type, data view, array buffer and string type.**
***   **option:** is an optional parameter for saving zlib options.*   **Callback:** It holds the callback function.**

****返回值:**返回压缩后的数据块。**

**以下示例说明了在 Node.js 中使用 **zlib.brotliCompress()方法**:**

****例 1:****

 **```js
// Node.js program to demonstrate the     
// brotliCompress() method

// Including zlib module
const zlib = require("zlib");

// Declaring input and assigning
// it a value string
var input = "Computer Science";

// Calling brotliCompress method
zlib.brotliCompress(input, (err, buffer) => {

        console.log(buffer.toString('base64'));
});
```** 

****输出:****

```js
Gw8A+CUAqhBDSpVv9iA= 
```

****例 2:****

 **```js
// Node.js program to demonstrate the     
// brotliCompress() method

// Including zlib module
const zlib = require("zlib");

// Declaring input and assigning
// it a value string
var input = "Computer Science";

// Calling brotliCompress method
zlib.brotliCompress(input, (err, buffer) => {
  if(!err) {
      console.log(buffer.toString('hex'));
  }
  else {
      console.log(err);
  }
});
```** 

****输出:****

```js
1b0f00f82500aa10434a956ff620 
```

****参考:**[https://nodejs . org/API/zlib . html # zlib _ zlib _ bromless _ buffer _ options _ callback](https://nodejs.org/api/zlib.html#zlib_zlib_brotlicompress_buffer_options_callback)**