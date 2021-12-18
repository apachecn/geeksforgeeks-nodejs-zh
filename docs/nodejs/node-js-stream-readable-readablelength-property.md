# Node.js Stream 可读. readableLength 属性

> 原文:[https://www . geesforgeks . org/node-js-stream-readable-length-property/](https://www.geeksforgeeks.org/node-js-stream-readable-readablelength-property/)

可读流中的**可读. readableLength 属性**，用于检查队列中准备读取的字节数。

**语法:**

```js
readable.readableLength
```

**返回值:**返回队列中准备读取的字节数。

下面的例子说明了在 Node.js 中**可读. readableLength 属性**的使用:

**例 1:**

```js
// Node.js program to demonstrate the     
// readable.readableLength Property

// Accessing stream module
const stream = require('stream');

// Creating a Readable stream 
const readable = new stream.Readable("input.txt");

// Calling readable.readableLength 
// Property
readable.readableLength;
```

**输出:**

```js
0
```

**例 2:**

```js
// Node.js program to demonstrate the     
// readable.readableLength property  

// Include fs module
const fs = require("fs");

// Constructing readable stream
const readable = fs.createReadStream("input.txt");

// Instructions for reading data
readable.on('readable', () => {
  let chunk;

  // Using while loop and calling
  // read method
  while (null !== (chunk = readable.read())) {

    // Displaying the chunk length
    console.log(`read: ${chunk.length}`);
     }
});

// Calling readableLength property
readable.readableLength;
```

**输出:**

```js
0
read: 13

```

**参考:**[https://nodejs . org/API/stream . html # stream _ readable _ readablelength](https://nodejs.org/api/stream.html#stream_readable_readablelength)。