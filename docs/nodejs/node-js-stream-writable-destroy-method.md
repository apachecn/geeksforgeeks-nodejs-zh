# Node.js Stream 可写. destroy()方法

> 原文:[https://www . geesforgeks . org/node-js-stream-written-destroy-method/](https://www.geeksforgeeks.org/node-js-stream-writable-destroy-method/)

**write . destroy()方法**是 Stream 模块的内置应用编程接口，用于销毁创建的流，在已经销毁创建的流后，不能调用 write()方法再次写入数据。

**语法:**

```
writable.destroy()
```

**参数:**此方法不接受任何参数。

**返回值:**返回被破坏属性设置为真的可写的所有属性。

以下示例说明了 Node.js 中**可写.科克()方法**的使用:

**例 1:**

```
// Node.js program to demonstrate the     
// writable.uncork() method  
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
writable.write('hello');

// Calling destroy function
writable.destroy();
```

**输出:**

```
hi
hello
Writable {  _writableState:
   WritableState {
     objectMode: false,     highWaterMark: 16384,
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

因此，创建的流被破坏。

**例 2:**

```
// Node.js program to demonstrate the     
// writable.uncork() method  
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
writable.write('hello');

// Calling destroy function
writable.destroy();

writable.write('');
```

**输出:**

```
hi
hello
Error [ERR_STREAM_DESTROYED]: Cannot call write after a stream was destro
yed
    at doWrite (_stream_writable.js:411:19)
    at writeOrBuffer (_stream_writable.js:399:5)
    at Writable.write (_stream_writable.js:299:11)
    at /home/runner/QuizzicalFluffyOperation/index.js:29:10
    at Script.runInContext (vm.js:133:20)
    at Object. (/run_dir/interp.js:156:20)
    at Module._compile (internal/modules/cjs/loader.js:778:30)
    at Object.Module._extensions..js (internal/modules/cjs/loader.js:789:
10)
    at Module.load (internal/modules/cjs/loader.js:653:32)

```

在上面的示例中，发生错误是因为在流被销毁后调用了 write()方法。

**参考:**[https://nodejs . org/API/stream . html # stream _ written _ destroy _ error](https://nodejs.org/api/stream.html#stream_writable_destroy_error)