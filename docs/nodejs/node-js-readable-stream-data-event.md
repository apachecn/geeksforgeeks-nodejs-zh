# Node.js 可读流数据事件

> 原文:[https://www . geesforgeks . org/node-js-readable-stream-data-event/](https://www.geeksforgeeks.org/node-js-readable-stream-data-event/)

可读流中的**“数据”事件**在可读时发出。调用 pipe()和 readable.resume()方法将流切换到流动模式，或者向数据事件添加侦听器回调。也可以通过调用 readable.read()方法并返回可用的数据块来引发此事件。

**语法:**

```
Event: 'data'
```

下面的例子说明了**数据事件**在 Node.js 中的使用:

**例 1:**

```
// Node.js program to demonstrate the     
// readable data event

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

// Handling the data event
readable.on('data', (chunk) => {
  console.log(`chunk length is: ${chunk.length}`);
});

console.log("Done...");
```

**输出:**

```
Done...
chunk length is: 13
read: GeeksforGeeks

```

**例 2:**

```
// Node.js program to demonstrate the     
// readable data event

// Including fs module
const fs = require('fs');

// Constructing readable stream
const readable = fs.createReadStream("input.txt");

// Calling pause method
readable.pause();

// Handling the data event
readable.on('data', (chunk) => {
  console.log(`chunk length is: ${chunk.length}`);
});

console.log("Done...");
```

**输出:**

```
Done...

```

**参考:**[https://nodejs.org/api/stream.html#stream_event_data](https://nodejs.org/api/stream.html#stream_event_data)。