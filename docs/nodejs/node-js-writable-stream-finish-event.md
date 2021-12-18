# Node.js 可写流结束事件

> 原文:[https://www . geesforgeks . org/node-js-written-stream-finish-event/](https://www.geeksforgeeks.org/node-js-writable-stream-finish-event/)

当所有数据被刷新到隐藏系统时，在调用可写. end()方法后，发出可写流中的**“完成”事件**。

**语法:**

```js
 Event: 'finish'
```

**返回值:**如果之前调用了可写的. end()方法，则发出此事件，否则不发出。

下面的例子说明了**“完成”事件**在 Node.js 中的使用:

**例 1:**

```js
// Node.js program to demonstrate the     
// finish event  

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
writable.write('hi');

// Calling end function
writable.end();

// Emitting finish event
writable.on('finish', function() {
   console.log("Write is completed.");
});

// Displays that the program 
// is ended
console.log("program is ended.");
```

**输出:**

```js
hi
program is ended.
Write is completed.

```

在上面的示例中，在 finish 事件之前调用了 writable.end()方法，因此它被发出。

**例 2:**

```js
// Node.js program to demonstrate the     
// finish event  

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
writable.write('hi');

// Emitting finish event
writable.on('finish', function() {
   console.log("Write is completed.");
});

// Displays that the program 
// is ended
console.log("program is ended.");
```

**输出:**

```js
hi
program is ended.

```

因此，这里不调用 writable.end()函数，因此不执行 finish 事件。

**参考:**T2】https://nodejs.org/api/stream.html#stream_event_finish