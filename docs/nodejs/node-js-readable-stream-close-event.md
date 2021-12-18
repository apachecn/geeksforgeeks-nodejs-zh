# Node.js 可读流关闭事件

> 原文:[https://www . geesforgeks . org/node-js-readable-stream-close-event/](https://www.geeksforgeeks.org/node-js-readable-stream-close-event/)

可读流中的**“关闭”事件**在流及其任何隐藏资源被关闭时发出。该事件意味着不能发出进一步的事件，也不能进行进一步的计算。此外，如果用 emitClose 选项创建了一个可读流，那么它总是可以发出“关闭”事件。

**语法:**

```
Event: 'close '
```

下面的例子说明了**关闭事件**在 Node.js 中的使用:

**例 1:**

```
// Node.js program to demonstrate the     
// readable close event

// Including fs module
const fs = require('fs');

// Constructing readable stream
const readable = fs.createReadStream("input.txt");

// Calling close method
readable.close();

// Handling close event
readable.on("close", () => {
    console.log("Stream ended");
});

console.log("Done...");
```

**输出:**

```
Done...
Stream ended

```

**例 2:**

```
// Node.js program to demonstrate the     
// readable close event

// Including fs module
const fs = require('fs');

// Constructing readable stream
const readable = fs.createReadStream("input.txt");

// Handling close event
readable.on("close", () => {
    console.log("Stream ended");
});

console.log("Done...");
```

**输出:**

```
Done...

```

这里不调用 close 方法，因此不会发出 close 事件。

**参考:**[https://nodejs.org/api/stream.html#stream_event_close_1](https://nodejs.org/api/stream.html#stream_event_close_1)。