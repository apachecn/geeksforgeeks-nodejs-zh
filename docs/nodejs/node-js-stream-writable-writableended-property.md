# Node.js Stream 可写.可写结束属性

> 原文:[https://www . geesforgeks . org/node-js-stream-writteableend-property/](https://www.geeksforgeeks.org/node-js-stream-writable-writableended-property/)

**可写.可写结束属性**是 Stream 模块的内置应用编程接口，用于检查可写.结束()方法是否被调用。

**语法:**

```js
writable.writableEnded 
```

**返回值:**如果在之前调用了 writable.end()方法，则返回 true，否则返回 false。

以下示例说明了在 Node.js 中**可写可写结束属性**的使用:

**例 1:**

```js
// Node.js program to demonstrate the     
// writable.writableEnded Property

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

// Calling end function
writable.end();

// Calling writable.writableEnded
// Property
writable.writableEnded;

// Calling destroy function
//to display output
writable.destroy();
```

**输出:**

```js
hi
GFG
Writable {
  _writableState:
   WritableState {     objectMode: false,
     highWaterMark: 16384,
     finalCalled: false,
     needDrain: false,
     ending: true,
     ended: true,
     finished: false,
     destroyed: true,
     decodeStrings: true,
     defaultEncoding: 'utf8',
     length: 0,
     writing: false,
     corked: 0,
     sync: false,
     bufferProcessing: false,
     onwrite: [Function: bound onwrite],
     writecb: null,
     writelen: 0,
     bufferedRequest: null,
     lastBufferedRequest: null,
     pendingcb: 2,
     prefinished: true,
     errorEmitted: false,
     emitClose: true,
     autoDestroy: false,
     bufferedRequestCount: 0,
     corkedRequestsFree:
      { next: null,
        entry: null,
        finish: [Function: bound onCorkedFinish] } },
  writable: false,
  _write: [Function: write],
  domain: null,
  _events: [Object: null prototype] {},
  _eventsCount: 0,
  _maxListeners: undefined }

```

在这里，您可以看到上面示例中的 end 属性被设置为 true。

**例 2:**

```js
// Node.js program to demonstrate the     
// writable.writableEnded Property

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

// Calling writable.writableEnded
// Property
writable.writableEnded;

// Calling destroy function
//to display output
writable.destroy();
```

**输出:**

```js
hi
GFG
Writable {
  _writableState:   WritableState {
     objectMode: false,
     highWaterMark: 16384,
     finalCalled: false,
     needDrain: false,
     ending: false,
     ended: false,
     finished: false,
     destroyed: true,
     decodeStrings: true,
     defaultEncoding: 'utf8',
     length: 0,
     writing: false,
     corked: 0,
     sync: false,
     bufferProcessing: false,
     onwrite: [Function: bound onwrite],
     writecb: null,
     writelen: 0,
     bufferedRequest: null,
     lastBufferedRequest: null,
     pendingcb: 2,
     prefinished: false,
     errorEmitted: false,
     emitClose: true,
     autoDestroy: false,
     bufferedRequestCount: 0,
     corkedRequestsFree:
      { next: null,
        entry: null,
        finish: [Function: bound onCorkedFinish] } },
  writable: true,
  _write: [Function: write],
  domain: null,
  _events: [Object: null prototype] {},
  _eventsCount: 0,
  _maxListeners: undefined }

```

在上面的示例中，end 属性被设置为 false，因为在调用 write . writable end 属性之前没有调用 writable.end()方法。

**参考:**[https://nodejs . org/API/stream . html # stream _ writable _ writableended](https://nodejs.org/api/stream.html#stream_writable_writableended)