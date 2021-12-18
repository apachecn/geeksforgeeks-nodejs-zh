# Node.js 可读流暂停事件

> 原文:[https://www . geesforgeks . org/node-js-readable-stream-pause-event/](https://www.geeksforgeeks.org/node-js-readable-stream-pause-event/)

当调用 stream.pause()并且*readableflow*属性不为假时，会发出可读流中的**“暂停”事件**。

**语法:**

```
Event: 'pause'
```

**返回值:**可读就发出，调用 pause()不可读就不发出。

下面的例子说明了**暂停事件**在 Node.js 中的使用:

**例 1:**

```
// Node.js program to demonstrate the     
// readable pause event

// Including fs module
const fs = require('fs');

// Constructing readable stream
const readable = fs.createReadStream("input.txt");
readable.on('data', (chunk) => {
  console.log(`${chunk}`);
});

// Handling pause event
readable.on("pause", () => {
    console.log("pause emitted!");
});

// Calling pause method
readable.pause();
console.log("Program ends....");
```

**输出:**

```
pause emitted!
Program ends....

```

**例 2:**

```
// Node.js program to demonstrate the     
// readable pause event

// Including fs module
const fs = require('fs');

// Constructing readable stream
const readable = fs.createReadStream("input.txt");
readable.on('data', (chunk) => {
  console.log(`${chunk}`);
});

// Handling pause event
readable.on("pause", () => {
    console.log("pause emitted!");
});

console.log("Program ends....");
```

**输出:**

```
Program ends....
GeeksforGeeks

```

这里不调用 pause()方法，因此不会发出暂停事件。

**参考:**T2】https://nodejs.org/api/stream.html#stream_event_pause