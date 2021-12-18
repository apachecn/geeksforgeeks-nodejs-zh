# Node.js Stream 可读. readableHighWaterMark 属性

> 原文:[https://www . geesforgeks . org/node-js-stream-readable-high watermark-property/](https://www.geeksforgeeks.org/node-js-stream-readable-readablehighwatermark-property/)

可读流中的**Readable HighWaterMark 属性**，用于检查构建可读流时使用的 high watermark 的值。

**语法:**

```js
readable.readableHighWaterMark
```

**返回值:**返回构建可读流时使用的高水位线的值。

以下示例说明了在 Node.js 中使用**可读. readablehighwark 属性**:

**例 1:**

```js
// Node.js program to demonstrate the     
// readable.readableHighWaterMark Property  

// Include fs module
const fs = require("fs");

// Constructing readable stream
const readable = fs.createReadStream("input.txt");

// Instructions for reading data
readable.on('readable', () => {
  let chunk;

  // Using while loop and calling
  // read method with parameter
  while (null !== (chunk = readable.read())) {

    // Displaying the chunk
    console.log(`read: ${chunk}`);
  }
});

// Calling readable.readableHighWaterMark
// Property
readable.readableHighWaterMark;
```

**输出:**

```js
65536
read: GeeksforGeeks

```

**例 2:**

```js
// Node.js program to demonstrate the     
// readable.readableHighWaterMark Property

// Accessing stream module
const stream = require('stream');

// Creating a stream and setting the value
// of the highWaterMark
const readable = new stream.Readable({
    highWaterMark: 1234
});

// Calling readable.readableHighWaterMark 
// Property
readable.readableHighWaterMark;
```

**输出:**

```js
1234
```

**参考:**[https://nodejs . org/API/stream . html # stream _ readablehighwark](https://nodejs.org/api/stream.html#stream_readable_readablehighwatermark)。