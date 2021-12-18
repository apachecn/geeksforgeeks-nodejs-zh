# Node.js Stream 可读. pause()方法

> 原文:[https://www . geesforgeks . org/node-js-stream-readable-pause-method/](https://www.geeksforgeeks.org/node-js-stream-readable-pause-method/)

**readable.pause()方法**是 Stream 模块的内置应用编程接口，用于阻止流动模式发出‘数据’事件。如果任何变得可访问的数据将继续存在于内部缓冲区中。

**语法:**

```
readable.pause()
```

**参数:**此方法不接受任何参数。

**返回值:**如果使用此方法，则此时暂停读取数据。

下面的例子说明了 **readable.pause()方法**在 Node.js 中的使用:

**例 1:**

```
// Node.js program to demonstrate the     
// readable.pause() method  

// Including fs module
const fs = require('fs');

// Constructing readable stream
const readable = fs.createReadStream("input.txt");
readable.on('data', (chunk) => {
  console.log(`${chunk}`);
});

// Calling pause method
readable.pause();

// Checking if paused or not
readable.isPaused();
```

**输出:**

```
true
```

**例 2:**

```
// Node.js program to demonstrate the     
// readable.pause() method  

// Include fs module
const fs = require('fs');

// Create readable stream
const readable = fs.createReadStream("input.txt");

// Handling data event
readable.on('data', (chunk) => {
  console.log(`Received ${chunk.length} bytes of data.`);

  // Calling pause method
  readable.pause();

  // After this any data will be displayed 
  // after 1 sec.
  console.log('No further data will be displayed for 1 second.');

  // Using setTimeout function
  setTimeout(() => {
    console.log('Now data starts flowing again.');
    readable.resume();
  }, 1000);
});

// Displays that program 
// is ended
console.log("Program ends!!");
```

**输出:**

```
Program ends!!
Received 5 bytes of data.
No further data will be displayed for 1 second.
Now data starts flowing again.

```

但是，您可以在运行时看到，在执行 pause()方法后，1 秒钟内不会显示更多数据。

**参考:**[https://nodejs.org/api/stream.html#stream_readable_pause](https://nodejs.org/api/stream.html#stream_readable_pause)。