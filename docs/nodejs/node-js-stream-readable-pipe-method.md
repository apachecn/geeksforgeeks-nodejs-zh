# Node.js Stream 可读. pipe()方法

> 原文:[https://www . geesforgeks . org/node-js-stream-readable-pipe-method/](https://www.geeksforgeeks.org/node-js-stream-readable-pipe-method/)

可读流中的**可读. pipe()方法**用于将可写流附加到可读流，从而切换到流动模式，然后将其拥有的所有数据推送到附加的可写流。

**语法:**

```
readable.pipe( destination, options )
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **Destination:** This parameter stores the destination of the written data.
*   **Option:** This parameter stores the pipeline options.

**返回值:**返回流。可写目标，如果是双工或转换流，则允许管道链。

下面的例子说明了在 Node.js 中使用**readable . haripe()方法**:

**例 1:**

```
// Node.js program to demonstrate the     
// readable.pipe() method

// Accessing fs module
var fs = require("fs");

// Create a readable stream
var readable = fs.createReadStream('input.txt');

// Create a writable stream
var writable = fs.createWriteStream('output.txt');

// Calling pipe method
readable.pipe(writable);

console.log("Program Ended");
```

**输出:**

```
Program Ended

```

因此，在管道方法之后，名为“output.text”的文件必须包含文件“input.text”中的数据。

**例 2:**

```
// Node.js program to demonstrate     
// the chaining of streams using
// readable.pipe() method

// Accessing fs and zlib module
var fs = require("fs");
var zlib = require('zlib');

// Compress the file input.text to 
// input.txt.gz using pipe() method
fs.createReadStream('input.text')
   .pipe(zlib.createGzip())
   .pipe(fs.createWriteStream('input.text.gz'));

console.log("File Compressed.");
```

**输出:**

```
File Compressed.

```

**参考:**[https://nodejs . org/API/stream . html # stream _ readable _ pipe _ destination _ options](https://nodejs.org/api/stream.html#stream_readable_pipe_destination_options)。