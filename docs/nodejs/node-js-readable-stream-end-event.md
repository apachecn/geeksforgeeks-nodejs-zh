# Node.js 可读流结束事件

> 原文:[https://www . geesforgeks . org/node-js-readable-stream-end-event/](https://www.geeksforgeeks.org/node-js-readable-stream-end-event/)

当可读流中没有可使用的数据时，会发出可读流中的**“结束”事件**。如果数据没有被完全使用，则不会发出“end”事件。这可以通过将流切换到流动模式，或者通过反复调用 stream.read()方法直到所有数据都被消耗掉来实现。

**语法:**

```
Event: 'end'
```

下面的例子说明了**结束事件**在 Node.js 中的使用:

**例 1:**

```
// Node.js program to demonstrate the     
// readable end event

// Including fs module
const fs = require('fs');

// Constructing readable stream
const readable = fs.createReadStream("input.txt");

// Instructions to read data
readable.on('readable', () => {
  let chunk;

  // Using while loop and calling
  // read method
  while (null !== (chunk = readable.read())) {

    // Displaying the chunk
    console.log(`read: ${chunk}`);
  }
});

// Handling end event
readable.on('end', () => {
  console.log('All the data is being consumed.');
});

console.log("Done...");
```

**输出:**

```
Done...
read: GeeksforGeeks
All the data is being consumed.

```

**例 2:**

```
// Node.js program to demonstrate the     
// readable end event

// Including fs module
const fs = require('fs');

// Constructing readable stream
const readable = fs.createReadStream("input.txt");

// Handling end event
readable.on('end', () => {
  console.log('All the data is being consumed.');
});

console.log("Done...");
```

**输出:**

```
Done...

```

在这里，所有的数据都不作为 stream 使用，不调用 read()方法，因此在这里不发出 end 事件。

**参考:**T2】https://nodejs.org/api/stream.html#stream_event_end