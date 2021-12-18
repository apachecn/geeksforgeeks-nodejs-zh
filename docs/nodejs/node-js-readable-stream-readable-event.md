# Node.js 可读流可读事件

> 原文:[https://www . geesforgeks . org/node-js-ready-stream-ready-event/](https://www.geeksforgeeks.org/node-js-readable-stream-readable-event/)

可读流中的**“可读”事件**在数据可用时发出，以便可以从流中读取数据，或者可以通过添加“可读”事件的侦听器来发出，该侦听器将导致数据被读取到内部缓冲区中。

**语法:**

```js
Event: 'readable'
```

下面的例子说明了**可读事件**在 Node.js 中的使用:

**例 1:**

```js
// Node.js program to demonstrate the     
// readable event

// Including fs module
const fs = require('fs');

// Constructing readable stream
const readable = fs.createReadStream("input.txt");

// Handling readable event
readable.on('readable', () => {
  let chunk;

  // Using while loop and calling
  // read method
  while (null !== (chunk = readable.read())) {

    // Displaying the chunk
    console.log(`read: ${chunk}`);
  }
});

console.log("Done...");
```

**输出:**

```js
Done...
read: GeeksforGeeks

```

**例 2:**

```js
// Node.js program to demonstrate the     
// readable event

// Including fs module
const fs = require('fs');

// Constructing readable stream
const readable = fs.createReadStream("input.txt");

// Handling readable event
readable.on('readable', () => {
  console.log(`readable: ${readable.read()}`);
});

// Handling end event
readable.on('end', () => {
  console.log('Stream ended');
});
console.log("Done.");
```

**输出:**

```js
Done.
readable: GeeksforGeeks
readable: null
Stream ended

```

这里，发出 end 事件，因此返回 null。

**参考:**T2】https://nodejs.org/api/stream.html#stream_event_readable