# Node.js Stream 可读[symbol . asynnciterator]()方法

> 原文:[https://www . geeksforgeeks . org/node-js-stream-readable symbol-asynciterrator-method/](https://www.geeksforgeeks.org/node-js-stream-readablesymbol-asynciterator-method/)

可读流中的**可读【Symbol.asyncIterator】()方法**用于完全消耗该流。

**语法:**

```
readable[Symbol.asyncIterator]()
```

**参数:**此方法不接受任何参数。

**返回值:**返回**asynciterror**完全消耗流。

下面的例子说明了在 Node.js 中使用**可读的【符号. asynnciterator】()**方法:

**例 1:**

```
// Node.js program to demonstrate the     
// readable[Symbol.asyncIterator]()
// method  

// Include fs module
const fs = require('fs');

// Using async function
async function print(readable) {

  // Setting the encoding
  readable.setEncoding('utf8');
  let data = '';
  for await (const chunk of readable) {
    data += chunk;
  }
  console.log(data);
}
print(fs.createReadStream('input.text')).catch(console.error);
```

**输出:**

```
Promise { <Pending> }
GeeksforGeeks
```

**例 2:**

```
// Node.js program to demonstrate the     
// readable[Symbol.asyncIterator]()
// method  

// Constructing readable from stream
const { Readable } = require('stream');

// Using async function
async function * generate() {
  yield 'GfG';
  yield 'CS-Portal';
}

// Creating readable streams from iterables
const readable = Readable.from(generate());

readable.on('data', (chunk) => {
  console.log(chunk);
});

console.log("program ends!!!");
```

**输出:**

```
program ends!!!
GfG
CS-Portal

```

**参考:**[https://nodejs . org/API/stream . html # stream _ readable _ symbol _ asynciterator](https://nodejs.org/api/stream.html#stream_readable_symbol_asynciterator)。