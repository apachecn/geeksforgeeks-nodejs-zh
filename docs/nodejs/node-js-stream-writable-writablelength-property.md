# Node.js Stream 可写可写长度属性

> 原文:[https://www . geesforgeks . org/node-js-stream-write-writablelength-property/](https://www.geeksforgeeks.org/node-js-stream-writable-writablelength-property/)

**可写可写长度属性**是流模块的内置应用，用于检查队列中准备写入的字节数。

**语法:**

```
writable.writableLength
```

**返回值:**该属性返回准备写入队列的字节数。

下面的例子说明了在 Node.js 中**可写可写长度属性**的使用:

**例 1:**

```
// Node.js program to demonstrate the     
// writable.writableLength Property

// Accessing stream module
const stream = require('stream');

// Creating a stream and creating 
// a write function
const writable = new stream.Writable({

  // Write function with its 
  // parameters
  write: function(chunk, encoding, next) {

    // Converting the chunk of
    // data to string
    console.log(chunk.toString());
    next();
  }
});

// Calling cork() function
writable.cork();

 //Writing data
writable.write('hi');

// Again writing some data
writable.write('GFG');

// Calling writable.writableLength 
// Property
writable.writableLength;
```

**输出:**

```
5
```

**例 2:**

```
// Node.js program to demonstrate the     
// writable.writableLength Property

// Accessing stream module
const stream = require('stream');

// Creating a stream and creating 
// a write function
const writable = new stream.Writable({

  // Write function with its 
  // parameters
  write: function(chunk, encoding, next) {

    // Converting the chunk of
    // data to string
    console.log(chunk.toString());
    next();
  }
});

// Calling cork() function
writable.cork();

 //Writing data
writable.write('hi');

// Calling uncork() function
writable.uncork();

// Again calling cork function
writable.cork();

// Again writing some data
writable.write('GFG');

// Calling writable.writableLength 
// Property
writable.writableLength;
```

**输出:**

```
hi
3

```

这里，数据“hi”不再存在于缓冲器中，因此，缓冲器只有 3 个字节存在，数据“GFG”需要 3 个字节。

**参考:**[https://nodejs . org/API/stream . html # stream _ writable _ writablelength](https://nodejs.org/api/stream.html#stream_writable_writablelength)