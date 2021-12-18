# Node.js Stream 可写. setDefaultEncoding()方法

> 原文:[https://www . geesforgeks . org/node-js-stream-written-setdefaultencoding-method/](https://www.geeksforgeeks.org/node-js-stream-writable-setdefaultencoding-method/)

**可写. setDefaultEncoding()方法**是 Stream 模块的内置应用编程接口，用于设置可写流的默认编码。

**语法:**

```js
writable.setDefaultEncoding( encoding ) 
```

**参数:**该方法接受单参数**编码**，该编码保存用于可写流的编码。

**返回值:**返回默认的编码。

以下示例说明了在 Node.js 中使用**可写. setDefaultEncoding()方法**:

**例 1:**

```js
// Node.js program to demonstrate the     
// writable.setDefaultEncoding() method  
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

// Calling setDefaultEncoding method
writable.setDefaultEncoding("utf8");
```

**输出:**

```js
hi
Writable {
  _writableState:
   WritableState {
     objectMode: false,
     highWaterMark: 16384,
     finalCalled: false,
     needDrain: false,
     ending: false,
     ended: false,
     finished: false,
     destroyed: false,
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
     pendingcb: 1,
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

这里，默认值在输出中返回。

**例 2:**

```js
// Node.js program to demonstrate the     
// writable.setDefaultEncoding() method  
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

// Calling setDefaultEncoding method
writable.setDefaultEncoding("ascii");
```

**输出:**

```js
hi
Writable {
  _writableState:
   WritableState {
     objectMode: false,
     highWaterMark: 16384,
     finalCalled: false,
     needDrain: false,     ending: false,
     ended: false,
     finished: false,
     destroyed: false,
     decodeStrings: true,
     defaultEncoding: 'ascii',
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
     pendingcb: 1,
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

这里，默认值是“ascii”。

**参考:**[https://nodejs . org/API/stream . html # stream _ written _ setdefaultencoding _ encoding](https://nodejs.org/api/stream.html#stream_writable_setdefaultencoding_encoding)