# Node.js 可读流恢复事件

> 原文:[https://www . geesforgeks . org/node-js-readable-stream-resume-event/](https://www.geeksforgeeks.org/node-js-readable-stream-resume-event/)

当调用 stream.resume()并且*readableflow*属性不为真时，会发出可读流中的**“resume”事件**。

**语法:**

```js
Event: 'resume'
```

**返回值:**如果可读则发出，如果调用 resume()则不发出。

下面的例子说明了**恢复事件**在 Node.js 中的使用:

**例 1:**

```js
// Node.js program to demonstrate the     
// readable resume event

// Including fs module
const fs = require('fs');

// Constructing readable stream
const readable = fs.createReadStream("input.txt");

// Handling data event
readable.on('data', (chunk) => {
  console.log(`${chunk}`);
});

// Calling pause method
 readable.pause() 

 // Calling resume method
 readable.resume();

 // Handling resume event
 readable.on('resume', () => {
    console.log("resume emitted!");
});

console.log("Program ends....");
```

**输出:**

```js
Program ends....
resume emitted!
GeeksforGeeks

```

**例 2:**

```js
// Node.js program to demonstrate the     
// readable resume event

// Including fs module
const fs = require('fs');

// Constructing readable stream
const readable = fs.createReadStream("input.txt");

// Handling data event
readable.on('data', (chunk) => {
console.log(`${chunk}`);

  // Calling pause method
  readable.pause();

  // After this any data will be displayed 
  // after 3 sec.
  console.log('No additional data will "
        + "be displayed for 3 seconds.');

  // Using setTimeout function
  setTimeout(() => {
    console.log('Now data starts flowing again.');

    // Calling resume method
    readable.resume();

    // Emitting resume event
    readable.on("resume", () => {
    console.log("resume emitted!");
});
  }, 3000);
});

console.log("Done....");
```

**输出:**

```js
Done....
GeeksforGeeks
No additional data will be displayed for 3 seconds.
Now data starts flowing again.
resume emitted!

```

**参考:**T2】https://nodejs.org/api/stream.html#stream_event_resume