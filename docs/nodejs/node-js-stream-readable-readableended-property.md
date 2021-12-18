# Node.js Stream 可读. readableEnded 属性

> 原文:[https://www . geesforgeks . org/node-js-stream-readableend-property/](https://www.geeksforgeeks.org/node-js-stream-readable-readableended-property/)

可读流中的**可读. readableEnded 属性**用于检查是否发出了结束事件。

**语法:**

```
readable.readableEnded
```

**返回值:**如果发出结束事件，则返回真，否则返回假。

下面的例子说明了在 Node.js 中**可读. readableEnded 属性**的使用:

**例 1:**

```
// Node.js program to demonstrate the     
// readable.readableEnded Property  

// Include fs module
var fs = require("fs");

// Data to be displayed
var data = '';

// Create a readable stream
var readable = fs.createReadStream("input.text");

// Set the encoding to be utf8. 
readable.setEncoding('UTF8');

// Handling stream event data and end
readable.on('data', function(chunk) {
   data += chunk;
});

// End event
readable.on('end',function() {
   console.log(data);
});

// Calling readableEnded property
readable.readableEnded;
```

**输出:**

```
read: hello
true
end!!

```

**例 2:**

```
// Node.js program to demonstrate the     
// readable.readableEnded Property  

// Include fs module
var fs = require("fs");

// Create a readable stream
var readable = fs.createReadStream("input.text");

// Set the encoding to be utf8. 
readable.setEncoding('UTF8');
readable.on('readable', () => {
  let chunk;

  // Using while loop and calling
  // read method with parameter
  while (null !== (chunk = readable.read())) {

    // Displaying the chunk
    console.log(`read: ${chunk}`);
  }
});

// Calling readableEnded property
readable.readableEnded;
```

**输出:**

```
false
read: hello

```

**参考:**[https://nodejs . org/API/stream . html # stream _ readableended](https://nodejs.org/api/stream.html#stream_readable_readableended)。