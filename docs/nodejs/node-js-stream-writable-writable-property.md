# Node.js Stream 可写可写属性

> 原文:[https://www . geesforgeks . org/node-js-stream-written-written-property/](https://www.geeksforgeeks.org/node-js-stream-writable-writable-property/)

**可写可写属性**是 Stream 模块的内置应用编程接口，用于检查可写. write()方法调用是否安全。

**语法:**

```
writable.writable 
```

**返回值:**如果可以安全调用 writable.write()方法，则返回 true，否则返回 false。

下面的例子说明了**可写属性**在 Node.js 中的使用:

**例 1:**

```
// Node.js program to demonstrate the     
// writable.writable Property

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

// Calling writable.writable
// Property
writable.writable;
```

**输出:**

```
hi
GFG
true

```

**例 2:**

```
// Node.js program to demonstrate the     
// writable.writable Property

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

// Calling end() method
writable.end();

// Calling writable.writable
// Property
writable.writable;
```

**输出:**

```
hi
GFG
false

```

在上面的示例中，输出为 false，因为在调用 writable.write 属性之前调用了 writable.end()方法，所以调用 writable.write()方法是不安全的，因此输出为 false。

**参考:**T2】https://nodejs.org/api/stream.html#stream_writable_writable