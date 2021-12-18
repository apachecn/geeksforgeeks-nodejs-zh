# Node.js Stream 可写. writableObjectMode 属性

> 原文:[https://www . geesforgeks . org/node-js-stream-write-writableobjectmode-property/](https://www.geeksforgeeks.org/node-js-stream-writable-writableobjectmode-property/)

流模块中的**可写、可写对象模式属性**用于获取可写流的对象模式值。

**语法:**

```js
writable.writableObjectMode 
```

**返回值:**如果*对象模式*设置为真，则返回真，否则返回假。

以下示例说明了在 Node.js 中使用**可写.可写对象模式属性**:

**例 1:**

```js
// Node.js program to demonstrate the     
// writable.writableObjectMode Property

// Accessing stream module
const stream = require('stream');

// Creating a stream and creating 
// a write function
const writable = new stream.Writable({

  // setting value of objectMode
  objectMode: true,

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
writable.write('GfG')

// Calling writable.writableObjectMode 
// Property
writable.writableObjectMode;
```

**输出:**

```js
GfG
true

```

**例 2:**

```js
// Node.js program to demonstrate the     
// writable.writableObjectMode Property

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
writable.write('GfG')

// Calling writable.writableObjectMode 
// Property
writable.writableObjectMode;
```

**输出**

```js
GfG
false

```

这里*对象模式*没有设置，所以默认设置为假。

**参考:**[https://nodejs . org/API/stream . html # stream _ writable _ writable object mode](https://nodejs.org/api/stream.html#stream_writable_writableobjectmode)