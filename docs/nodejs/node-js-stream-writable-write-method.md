# Node.js Stream 可写. write()方法

> 原文:[https://www . geesforgeks . org/node-js-stream-write-write-method/](https://www.geeksforgeeks.org/node-js-stream-writable-write-method/)

**write . write()方法**是 Stream 模块的内置应用编程接口，用于将一些数据写入可写流。一旦数据被完全处理，就调用回调函数。

**语法:**

```js
writable.write( chunk, encoding, callback)
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **Chunk:** is an optional data writing. The value of the block must be a string, buffer or Uint 8 array. For object mode, the block value can be any value other than null.
*   **Code:** If the chunk is a string value, the code value is saved.
*   **Callback:** is an optional callback function of the stream.

**返回值:**如果在此方法返回真之前发出‘排空’事件，则返回假。

以下示例说明了在 Node.js 中使用**可写. write()方法**:

**例 1:**

```js
// Node.js program to demonstrate the     
// writable.write() method  

// Including stream module
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

// Calling write method with
// all its parameter
writable.write("GfG", "utf8", () => {
     console.log("CS-Portal!");
});
```

**输出:**

```js
GfG
true
CS-Portal!

```

**例 2:**

```js
// Node.js program to demonstrate the     
// writable.write() method  

// Including stream module
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

// Calling write method with one
// parameter
writable.write('GeeksforGeeks');
```

**输出:**

```js
GeeksforGeeks
true

```

**参考:**[https://nodejs . org/API/stream . html # stream _ write _ chunk _ encoding _ callback](https://nodejs.org/api/stream.html#stream_writable_write_chunk_encoding_callback)