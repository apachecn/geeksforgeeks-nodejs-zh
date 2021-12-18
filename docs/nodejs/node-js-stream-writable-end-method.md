# Node.js Stream 可写. end()方法

> 原文:[https://www . geesforgeks . org/node-js-stream-written-end-method/](https://www.geeksforgeeks.org/node-js-stream-writable-end-method/)

**可写. end()方法**是 Stream 模块的内置应用编程接口，这样就不会再有数据写入可写了。参数*块*和*编码*是可选的，这将允许在关闭流之前立即写入最后一个新的数据块。此外，可选的*回调*函数被添加为可写流的“完成”事件的监听器。

**语法:**

```
writable.end( chunk, encoding, callback)
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **Chunk:** is an optional data writing. The value of the block must be a string, buffer or Uint 8 array. For object mode, the block value can be any value other than null.
*   **Code:** If the chunk is a string value, the code value is saved.
*   **Callback:** is an optional callback function of the stream.

**返回值:**它返回调用此方法之前写入的数据，如果 end()方法有一大块新数据，那么它也会在末尾返回。

下面的例子说明了在 Node.js 中**可写. end()方法**的使用:

**例 1:**

```
// Node.js program to demonstrate the     
// writable.end() method  

// INcluding stream module
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

// Calling end method with its 
// all the parameters
writable.end("last data", "utf8", () => {
     console.log("Writable stream ended!");
});
```

**输出:**

```
hi
last data
Writable {
  _writableState:
   WritableState {
     objectMode: false,
     highWaterMark: 16384,
     finalCalled: false,
     needDrain: false,
     ending: true,
     ended: true,
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
  _events:
   [Object: null prototype] {
     finish: { [Function: bound onceWrapper] listener: [Function] } },
  _eventsCount: 1,
  _maxListeners: undefined }
Writable stream ended!

```

**例 2:**

```
// Node.js program to demonstrate the     
// writable.end() method  

// INcluding stream module
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

// Calling end method with its 
// all the parameters
writable.end("last data", "utf8", () => {
     console.log("Writable stream ended!");
});
writable.write('GfG');
```

**输出:**

```
hi
last data
Error [ERR_STREAM_WRITE_AFTER_END]: write after end
    at writeAfterEnd (_stream_writable.js:248:12)
    at Writable.write (_stream_writable.js:296:5)
    at /home/runner/LuxuriousLegitimateObservation/index.js:30:10
    at Script.runInContext (vm.js:133:20)
    at Object. (/run_dir/interp.js:156:20)
    at Module._compile (internal/modules/cjs/loader.js:778:30)
    at Object.Module._extensions..js (internal/modules/cjs/loader.js:789:10)
    at Module.load (internal/modules/cjs/loader.js:653:32)
    at tryModuleLoad (internal/modules/cjs/loader.js:593:12)
    at Function.Module._load (internal/modules/cjs/loader.js:585:3)Writab
le stream ended!

```

这里显示一个错误，因为在 end()方法之后调用 write()方法是不可能的。

**参考:**[https://nodejs . org/API/stream . html # stream _ written _ end _ chunk _ encoding _ callback](https://nodejs.org/api/stream.html#stream_writable_end_chunk_encoding_callback)