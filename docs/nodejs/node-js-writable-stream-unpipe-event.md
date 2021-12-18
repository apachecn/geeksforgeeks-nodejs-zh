# Node.js 可写流拆线事件

> 原文:[https://www . geesforgeks . org/node-js-written-stream-unpip-event/](https://www.geeksforgeeks.org/node-js-writable-stream-unpipe-event/)

可写流中的**“unpip”事件**是在可读流上调用 stream.unpipe()方法时发出的，方法是将该可写流从其目标集合中分离出来。

**语法:**

```
 Event: 'unpipe'
```

**返回值:**如果正在调用 unpipe()方法，则发出此事件，否则不发出。

以下示例说明了在 Node.js 中使用**“取消固定”事件**:

**例 1:**

```
// Node.js program to demonstrate the     
// unpipe event

// Accessing fs module
var fs = require("fs");

// Create a readable stream
var readable = fs.createReadStream('input.txt');

// Create a writable stream
var writable = fs.createWriteStream('output.txt');

// Handling unpipe event
writable.on("unpipe", readable => {
    console.log("Unpiped!");
});

// Calling pipe method
readable.pipe(writable);

// Calling unpipe method
readable.unpipe(writable);

console.log("Program Ended...");
```

**输出:**

```
Unpiped!
Program Ended...

```

**例 2:**

```
// Node.js program to demonstrate the     
// unpipe event

// Accessing fs module
var fs = require("fs");

// Create a readable stream
var readable = fs.createReadStream('input.txt');

// Create a writable stream
var writable = fs.createWriteStream('output.txt');

// Handling unpipe event
writable.on("unpipe", readable => {
    console.log("Unpiped!");
});

console.log("Program Ended...");
```

**输出:**

```
Program Ended...

```

因此，这里不调用 unpipe()函数，因此不发出 unpipe 事件。

**参考:**T2】https://nodejs.org/api/stream.html#stream_event_unpipe