# Node.js Stream 可读.可读属性

> 原文:[https://www . geesforgeks . org/node-js-stream-可读-可读-property/](https://www.geeksforgeeks.org/node-js-stream-readable-readable-property/)

**可读.可读属性**是 Stream 模块的内置应用编程接口，用于检查调用 readable.read()方法是否安全。

**语法:**

```js
readable.readable
```

**返回值:**如果可读则返回真，否则返回假。

下面的例子说明了**可读属性**在 Node.js 中的使用:

**例 1:**

```js
// Node.js program to demonstrate the     
// readable.readable Property

// Include fs module
const fs = require('fs');

// Creating readable stream
const readable = fs.createReadStream("input.txt");

// Calling readable property
readable.readable;
```

**输出:**

```js
true
```

**例 2:**

```js
// Node.js program to demonstrate the     
// readable.readable Property  

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

    // Displaying the chunk
    console.log(`read: ${chunk}`);
  }
});

// Shows that the program
// ended
console.log("Program ends!!");

// Calling readable property
readable.readable;
```

**输出:**

```js
Program ends!!
true
read: hello

```

**参考:**T2】https://nodejs.org/api/stream.html#stream_readable_readable