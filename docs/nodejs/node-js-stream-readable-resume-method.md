# Node.js Stream 可读. resume()方法

> 原文:[https://www . geesforgeks . org/node-js-stream-readable-resume-method/](https://www.geeksforgeeks.org/node-js-stream-readable-resume-method/)

可读流中的 **readable.resume()方法**用于暂停的数据可以再次恢复，数据再次开始流动。

**语法:**

```js
readable.resume()
```

**参数:**此方法不接受任何参数。

**返回值:**如果使用该方法，则暂停的数据再次开始流动。

下面的例子说明了 **readable.resume()方法**在 Node.js 中的使用:

**例 1:**

```js
// Node.js program to demonstrate the     
// readable.resume() method  

// Including fs module
const fs = require('fs');

// Constructing readable stream
const readable = fs.createReadStream("input.text");
readable.on('data', (chunk) => {
  console.log(`${chunk}`);
});

// Calling pause method
readable.pause();

// Calling resume method
readable.resume();

console.log("Data starts flowing again!!");
```

**输出:**

```js
Data starts flowing again!!
Hello!!!

```

**例 2:**

```js
// Node.js program to demonstrate the     
// readable.resume() method  

// Include fs module
const fs = require('fs');

// Create readable stream
const readable = fs.createReadStream("input.text");

// Handling data event
readable.on('data', (chunk) => {
  console.log(`${chunk}`);

  // Calling pause method
  readable.pause();

  // After this any data will be displayed 
  // after 3 sec.
  console.log('No additional data will be '
             + 'displayed for 3 seconds.');

  // Using setTimeout function
  setTimeout(() => {
    console.log('Now data starts flowing again.');

    // Calling resume method
    readable.resume();
  }, 3000);
});

// Displays that program 
// is ended
console.log("Program ends!!");
```

**输出:**

```js
Program ends!!
Hello!!!
No additional data will be displayed for 3 seconds.
Now data starts flowing again.

```

但是，您可以在运行时看到，在执行 pause()方法后，3 秒钟内不会显示更多数据。

**参考:**T2】https://nodejs.org/api/stream.html#stream_readable_resume