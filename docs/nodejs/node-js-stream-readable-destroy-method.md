# Node.js Stream 可读. destroy()方法

> 原文:[https://www . geesforgeks . org/node-js-stream-readable-destroy-method/](https://www.geeksforgeeks.org/node-js-stream-readable-destroy-method/)

**readable.destroy()方法**是 Stream 模块的内置应用编程接口，用于销毁流。

**语法:**

```
readable.destroy( error )
```

**参数:**该方法接受单参数**错误**，该参数是可选的，在处理错误事件时会发出错误。

**返回值:**如果使用此方法，则流被破坏，如果错误参数作为参数传递，则它发出错误事件。

以下示例说明了在 Node.js 中使用 **readable.destroy()方法**:

**例 1:**

```
// Node.js program to demonstrate the     
// readable.destroy() method  

// Include fs module
const fs = require("fs");

// Constructing readable stream
const readable = fs.createReadStream("input.txt");

// Instructions for reading data
readable.on('readable', () => {
  let chunk;

  // Using while loop and calling
  // read method with parameter
  while (null !== (chunk = readable.read(1))) {

    // Displaying the chunk
    console.log(`read: ${chunk}`);
  }
});

// Calling destroy method
readable.destroy();

// Displays that the stream is 
// destroyed
console.log("Stream destroyed");
```

**输出:**

```
Stream destroyed
```

**例 2:**

```
// Node.js program to demonstrate the     
// readable.destroy() method  

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

// Handling error event
readable.on('error', err => {
    console.log(err);
});

// Calling destroy method
// with parameter
readable.destroy(['error']);

// Displays that the stream is 
// destroyed
console.log("Stream destroyed");
```

**输出:**

```
Stream destroyed
[ 'error' ]
```

在上面的示例中，发出了错误事件。

**参考:**[https://nodejs . org/API/stream . html # stream _ readable _ destroy _ error](https://nodejs.org/api/stream.html#stream_readable_destroy_error)