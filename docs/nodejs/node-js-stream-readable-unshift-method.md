# node . js Stream readable . unshift()方法

> 原文:[https://www . geesforgeks . org/node-js-stream-readable-unshift-method/](https://www.geeksforgeeks.org/node-js-stream-readable-unshift-method/)

可读流中的**可读. unshift()方法**用于将数据块推回到内部缓冲区。然而，当一个流被完全消耗并且需要“不消耗”时，这个方法是有帮助的。

**语法:**

```js
readable.unshift( chunk, encoding )
```

**参数:**该方法接受两个参数，如上所述，如下所述。

*   **Block:** It contains the data block to be unloaded into the read queue.
*   **Code:** Save the code type.

**返回值:**该方法将数据块转移到内部缓冲区，再次调用 read 方法后可以只读。

以下示例说明了在 Node.js 中使用 **readable.unshift()方法**:

**例 1:**

```js
// Node.js program to demonstrate the     
// readable.unshift() method  

// Including fs module
const fs = require('fs');

// Declaring data
var data = '';

// Constructing readable stream
const readable = fs.createReadStream("input.text");

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
console.log("Program ends!!!");

// Calling unshift method
readable.unshift(data);
```

**输出:**

```js
Program ends!!!
true
read: GfG
```

**例 2:**

```js
// Node.js program to demonstrate the     
// readable.unshift(chunk[, encoding])
// method  

// Include fs module
const fs = require('fs');
var data = '';

// Create readable stream
const readable = fs.createReadStream("input.text");

// Calling setEncoding method
readable.setEncoding('utf8');

// Instructions to unshift data
readable.on("readable", () => {
  let data = readable.read();

  while (data === "GfG") {

    readable.unshift(data);
    data = readable.read();
  }
  });

// Displays that program 
// is unshifted
  console.log("Unshifted!!");
```

**输出:**

```js
Unshifted!!
```

**参考:**[https://nodejs . org/API/stream . html # stream _ readable _ unshut _ chunk _ encoding](https://nodejs.org/api/stream.html#stream_readable_unshift_chunk_encoding)。