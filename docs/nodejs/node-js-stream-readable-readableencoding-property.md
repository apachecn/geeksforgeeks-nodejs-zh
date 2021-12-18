# Node.js Stream 可读. readableEncoding 属性

> 原文:[https://www . geesforgeks . org/node-js-stream-readable encoding-property/](https://www.geeksforgeeks.org/node-js-stream-readable-readableencoding-property/)

可读流中的【readable.readableEncodin 属性用于获取所述可读流的属性编码。此外，您可以使用可读的. setEncoding()方法设置此属性。

**语法:**

```
readable.readableEncoding
```

**返回值:**返回程序中使用的编码。

下面的例子说明了在 Node.js 中**可读. readableEncoding 属性**的使用:

**例 1:**

```
// Node.js program to demonstrate the     
// readable.readableEncoding Property  

// Include fs module
const fs = require("fs");

// Constructing readable stream
const readable = fs.createReadStream("input.text");

// Setting the encoding 
readable.setEncoding("base64");

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

// Calling readableEncoding property
readable.readableEncoding;
```

**输出:**

```
read: aGVs
read: bG8=

```

**例 2:**

```
// Node.js program to demonstrate the     
// readable.readableEncoding Property  

// Include fs module
const fs = require("fs");

// Constructing readable stream
const readable = fs.createReadStream("input.text");

// Setting the encoding 
readable.setEncoding("hex");

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

// Calling readableEncoding property
readable.readableEncoding;
```

**输出:**

```
read: 68656c6c6f
```

**参考:**[https://nodejs . org/API/stream . html # stream _ readable _ encoding](https://nodejs.org/api/stream.html#stream_readable_readableencoding)。