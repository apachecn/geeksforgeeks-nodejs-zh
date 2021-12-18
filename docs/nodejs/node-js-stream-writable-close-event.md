# Node.js 流。可写关闭事件

> 原文:[https://www . geesforgeks . org/node-js-stream-written-close-event/](https://www.geeksforgeeks.org/node-js-stream-writable-close-event/)

**溪流。可写关闭事件**是 stream 模块的内置应用编程接口，用于在关闭 Stream 及其任何隐藏资源(例如，文件描述符)时发出。这个事件意味着不会发出更多的事件，并且不会进行进一步的计算。

**语法:**

```js
Event: 'close'
```

**返回值:**如果在此事件后正在调用 writable.destroy()方法或正在关闭文件描述符，则发出此事件，否则不发出。

下面的例子说明了**流的使用。Node.js 中的可写关闭事件**:

**例 1:**

```js
// Node.js program to demonstrate the     
// close event  

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

// Writing data
writable.write('GeeksforGeeks');

// Emitting close event
writable.on('close', () => {
    console.log("No further operations will be performed!");
});

// Calling destroy function
writable.destroy();

// Shows that the program ends
console.log("program is ended.");
```

**输出:**

```js
GeeksforGeeks
program is ended.
No further operations will be performed!

```

在上面的示例中，在 close 事件之后调用了 writable.destroy()方法，因此它被发出。

**例 2:**

```js
// Node.js program to demonstrate the     
// close event  

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

// Writing data
writable.write('GeeksforGeeks');

// Emitting close event
writable.on('close', () => {
    console.log("No further operations will be performed!");
});

// Shows that the program ends
console.log("program is ended.");
```

**输出:**

```js
GeeksforGeeks
program is ended.

```

因此，这里不调用 writable.destroy()函数，因此不执行 close 事件。

**参考:**T2】https://nodejs.org/api/stream.html#stream_event_close