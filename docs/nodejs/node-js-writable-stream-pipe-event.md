# Node.js 可写流管道事件

> 原文:[https://www . geesforgeks . org/node-js-written-stream-pipe-event/](https://www.geeksforgeeks.org/node-js-writable-stream-pipe-event/)

可写流中的**管道事件**是在可读流上调用 stream.pipe()方法时发出的，方法是将该可写流附加到它的目标集。

**语法:**

```
Event: 'pipe'
```

**返回值:**如果正在调用 pipe()方法，则发出此事件，否则不发出。

以下示例说明了**“管道”事件**在 Node.js:
**示例 1:** 中的使用

```
// Node.js program to demonstrate the     
// pipe event

// Accessing fs module
var fs = require("fs");

// Create a readable stream
var readable = fs.createReadStream('input.txt');

// Create a writable stream
var writable = fs.createWriteStream('output.txt');

// Handling pipe event
writable.on("pipe", readable => {
    console.log("Piped!");
});

// Calling pipe method
readable.pipe(writable);

console.log("Program Ended.");
```

**输出:**

```
Piped!
Program Ended.

```

**例 2:**

```
// Node.js program to demonstrate the     
// pipe event

// Accessing fs module
var fs = require("fs");

// Create a readable stream
var readable = fs.createReadStream('input.txt');

// Create a writable stream
var writable = fs.createWriteStream('output.txt');

// Handling pipe event
writable.on("pipe", readable => {
    console.log("Piped!");
});

console.log("Program Ended");
```

**输出:**

```
Program Ended

```

因此，这里不调用 pipe()函数，因此不会发出 pipe 事件。

**参考:**T2】https://nodejs.org/api/stream.html#stream_event_pipe