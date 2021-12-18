# Node.js Stream 可写. writablehighwark 属性

> 原文:[https://www . geesforgeks . org/node-js-stream-writteble-writablehighwark-property/](https://www.geeksforgeeks.org/node-js-stream-writable-writablehighwatermark-property/)

**可写.可写高水位线属性**是流模块的内置应用编程接口，用于检查创建可写时传递的**高水位线**值。

**语法:**

```
writable.writableHighWaterMark
```

**返回值:**如果设置，则返回*高水位线*的值，否则返回默认值。

以下示例说明了在 Node.js 中**可写.可写高水印属性**的使用:

**例 1:**

```
// Node.js program to demonstrate the     
// writable.writableHighWaterMark Property

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

// Writing data
writable.write('hi');

// Again writing some data
writable.write('GFG');

// Calling writable.writableHighWaterMark 
// Property
writable.writableHighWaterMark;
```

**输出:**

```
hi
GFG
16384

```

这里，返回默认值。

**例 2:**

```
// Node.js program to demonstrate the     
// writable.writableHighWaterMark Property

// Accessing stream module
const stream = require('stream');

// Creating a stream and setting the value
// of the highWaterMark
const writable = new stream.Writable({
    highWaterMark: 1234
});

// Calling writable.writableHighWaterMark 
// Property
writable.writableHighWaterMark;
```

**输出:**

```
1234
```

这里，返回在创建可写流时设置的*高水位线*的值。

**参考:**[https://nodejs . org/API/stream . html # stream _ writable _ writablehighwark](https://nodejs.org/api/stream.html#stream_writable_writablehighwatermark)