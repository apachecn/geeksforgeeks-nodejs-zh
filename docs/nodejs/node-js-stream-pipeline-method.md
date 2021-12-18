# Node.js Stream.pipeline()方法

> 原文:[https://www . geesforgeks . org/node-js-stream-pipeline-method/](https://www.geeksforgeeks.org/node-js-stream-pipeline-method/)

**stream.pipeline()方法**是一种模块方法，用于链接传递错误的流，并在管道完成时准确清理和提供回调函数。

**语法:**

```js
stream.pipeline(...streams, callback)
```

**参数:**该方法接受两个参数，如上所述，如下所述。

*   **... Stream:** These are two or more streams that will be connected together by pipelines.
*   **Callback:** This function is called when the pipeline is completely completed. If the pipeline is not completed, "Error" will be displayed.

**返回值:**返回一个清理函数。

下面的例子说明了 **stream.pipeline()方法**在 Node.js 中的使用:

**例 1:**

```js
// Node.js program to demonstrate the     
// stream.pipeline() method

// Including fs and zlib module
var fs = require('fs');
const zlib = require('zlib');

// Constructing finished from stream
const { pipeline } = require('stream');

// Constructing promisify from
// util
const { promisify } = require('util');

// Defining pipelineAsync method
const pipelineAsync = promisify(pipeline);

// Constructing readable stream
const readable = fs.createReadStream("input.text");

// Constructing writable stream
var writable = fs.createWriteStream("output.text");

// Creating transform stream
const transform = zlib.createGzip();

// Async function
(async function run() {
  try{ 

    // pipelining three streams
    await pipelineAsync(
      readable,
      transform,
      writable
    );
    console.log("pipeline accomplished.");
    }

  // Shows error
  catch(err) {
    console.error('pipeline failed with error:', err);
  }
  })();
```

**输出:**

```js
Promise {  }
pipeline accomplished.
```

**例 2:**

```js
// Node.js program to demonstrate the     
// stream.pipeline() method

// Including fs and zlib module
var fs = require('fs');
const zlib = require('zlib');

// Constructing finished from stream
const { pipeline } = require('stream');

// Constructing promisify from
// util
const { promisify } = require('util');

// Defining pipelineAsync method
const pipelineAsync = promisify(pipeline);

// Constructing readable stream
const readable = fs.createReadStream("input.text");

// Constructing writable stream
var writable = fs.createWriteStream("output.text");

// Creating transform stream
const transform = zlib.createGzip();

// Async function
(async function run() {
  try{ 

    // pipelining three streams
    await pipelineAsync(
      readable,
      writable,
      transform
    );
    console.log("pipeline accomplished.");
    }

  // Shows error
  catch(err) {
    console.error('pipeline failed with error:', err);
  }
  })();
```

**输出:**这里，管道传输时，流的顺序不正确，因此出现错误。

```js
Promise {  }
pipeline failed with error: Error [ERR_STREAM_CANNOT_PIPE]: Cannot pipe, not readable
    at WriteStream.Writable.pipe (_stream_writable.js:243:24)
    at pipe (internal/streams/pipeline.js:57:15)
    at Array.reduce ()
    at pipeline (internal/streams/pipeline.js:88:18)
    at Promise (internal/util.js:274:30)
    at new Promise ()
    at pipeline (internal/util.js:273:12)
    at run (/home/runner/ThirstyTimelyKey/index.js:33:11)
    at /home/runner/ThirstyTimelyKey/index.js:45:5
    at Script.runInContext (vm.js:133:20)

```

**参考:**[https://nodejs . org/API/stream . html # stream _ stream _ pipeline _ streams _ callback](https://nodejs.org/api/stream.html#stream_stream_pipeline_streams_callback)。