# Node.js 可读流错误事件

> 原文:[https://www . geesforgeks . org/node-js-readable-stream-error-event/](https://www.geeksforgeeks.org/node-js-readable-stream-error-event/)

可读流中的**“错误”事件**可以随时发出。当隐藏流由于某种隐藏的内部故障而无法生成数据时，或者当流的实现推送无效的数据块时，就会发生这种情况。此外，单个 Error 对象作为参数传递给侦听器回调。

**语法:**

```
Event: 'error'
```

以下示例说明了在 Node.js:
**示例 1:** 中**错误事件**的使用

## java 描述语言

```
// Node.js program to demonstrate the     
// readable error event

// Including fs module
const fs = require('fs');

// Constructing readable stream
const readable = fs.createReadStream("input.txt");

// Handling error event
readable.on("error", err => {
    console.log(err);
});

console.log("Done...");
```

**输出:**

```
Done...
{ [Error: ENOENT: no such file or directory, open 'input.txt'] errno: -2,
 code: 'ENOENT', syscall: 'open', path: 'input.text' }
```

**例 2:**

## java 描述语言

```
// Node.js program to demonstrate the     
// readable error event

// Including fs module
const fs = require('fs');

// Constructing readable stream
const readable = fs.createReadStream("input.txt");

// Handling error event
readable.on("error", err => {
    console.log(err);
});

console.log("Done...");
```

**输出:**

```
Done...
```

这里，不会发生错误，因此不会发出错误事件。
**参考:**[https://nodejs.org/api/stream.html#stream_event_error_1](https://nodejs.org/api/stream.html#stream_event_error_1)