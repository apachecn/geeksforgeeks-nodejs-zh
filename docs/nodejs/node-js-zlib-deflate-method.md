# Node.js zlib.deflate()方法

> 原文:[https://www.geeksforgeeks.org/node-js-zlib-deflate-method/](https://www.geeksforgeeks.org/node-js-zlib-deflate-method/)

**zlib.deflate()方法**是 zlib 模块的内置应用编程接口，用于压缩一大块数据。

**语法:**

```js
zlib.deflate( buffer, options, callback )
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **Buffer: the type can be buffer, type line, data view, array buffer and string.**
***   **option:** is an optional parameter for saving zlib options.*   **Callback:** It holds the callback function.**

****返回值:**返回压缩后的数据块。**

**以下示例说明了 Node.js 中 **zlib.deflate()方法**的使用:**

****例 1:****

 **```js
// Node.js program to demonstrate the     
// deflate() method

// Including zlib module
const zlib = require("zlib");

// Declaring input and assigning
// it a value string
var input = "Geeks";

// Calling deflate method
zlib.deflate(input, (err, buffer) => {

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
eJxzT03NLgYABXQB8A== 
```

****例 2:****

 **```js
// Node.js program to demonstrate the     
// deflate() method

// Including zlib module
const zlib = require("zlib");

// Declaring input and assigning
// it a value string
var input = "Geeks";

// Calling deflate method
zlib.deflate(input, (err, buffer) => {

  if (!err) {

    console.log(buffer.toString('bas64'));
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
buffer.js:631
  throw new ERR_UNKNOWN_ENCODING(encoding);
  ^

TypeError [ERR_UNKNOWN_ENCODING]: Unknown encoding: bas64
    at stringSlice (buffer.js:631:9)    
    at Buffer.toString (buffer.js:667:10)    
    at Deflate.zlib.deflate [as cb] 
(/home/runner/BeautifulMiserlySourcecode/index.js:17:24)
    at Deflate.zlibBufferOnEnd (zlib.js:133:10)
    at Deflate.emit (events.js:203:15)
    at Deflate.EventEmitter.emit (domain.js:448:20)
    at endReadableNT (_stream_readable.js:1143:12)
    at process._tickCallback (internal/process/next_tick.js:63:19) 
```

**在这里，对数据进行编码时会发生错误，因此会引发错误。**

****参考:**T2【https://nodejs . org/API/zlib . html # zlib _ zlib _ deflate _ buffer _ options _ callback**