# 节点. js 流可读.已破坏属性

> 原文:[https://www . geesforgeks . org/node-js-stream-可读-已销毁-property/](https://www.geeksforgeeks.org/node-js-stream-readable-destroyed-property/)

**可读.销毁属性**是 Stream 模块的内置应用编程接口，用于检查可读.销毁()函数是否被调用。

**语法:**

```
readable.destroyed
```

**返回值:**如果可读则返回真，否则返回假。

下面的例子说明了在 Node.js 中**可读.销毁属性**的使用:

**例 1:**

```
// Node.js program to demonstrate the     
// readable.destroyed Property  

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
readable.destroy('error');

// Displays that the stream is 
// destroyed
console.log("Stream destroyed");

// Calling readable.destroyed
// Property
readable.destroyed;
```

**输出:**

```
Stream destroyed
true
error

```

**例 2:**

```
// Node.js program to demonstrate the     
// readable.destroyed Property  

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

// Displays that the stream is 
// destroyed
console.log("Program completed!!");

// Calling readable.destroyed
// Property
readable.destroyed;
```

**输出:**

```
Program completed!!
false
read: hello
```

所以，这里 readable.destroy()方法在 readable.destroyed 属性之前不被调用，所以它返回 false。

**参考:**[https://nodejs . org/API/stream . html # stream _ readable _ 销毁](https://nodejs.org/api/stream.html#stream_readable_destroyed)