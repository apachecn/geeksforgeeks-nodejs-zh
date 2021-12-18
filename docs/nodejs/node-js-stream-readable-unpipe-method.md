# Node.js Stream 可读. unpip()方法

> 原文:[https://www . geesforgeks . org/node-js-stream-readable-unpie-method/](https://www.geeksforgeeks.org/node-js-stream-readable-unpipe-method/)

可读流中的**可读. unpipe()方法**用于分离之前在使用 stream.pipe()方法时附加的可写流。

**语法:**

```
readable.unpipe( destination )
```

**参数:**该方法接受单参数**目的地**，即待分离的可写流的目的地。

**返回值:**返回流。可写，即目的地。

以下示例说明了在 Node.js 中使用**readable . unpip()方法**:

**例 1:**

```
// Node.js program to demonstrate the     
// readable.unpipe() method

// Accessing fs module
const fs = require('fs');

// Constructing readable stream
const readable = fs.createReadStream("input.text");

// Constructing writable Stream
const writable = fs.createWriteStream("output.text");

// Calling pipe method
readable.pipe(writable);

// Calling unpipe method
readable.unpipe(writable);
console.log("done");
```

**输出:**

```
done

```

**例 2:**

```
// Node.js program to demonstrate the     
// readable.unpipe() method

// Accessing fs module
const fs = require('fs');

// Constructing readable stream
const readable = fs.createReadStream("input.text");

// Constructing writable Stream
const writable = fs.createWriteStream("output.text");

// All the data from readable goes into 'output.text',
// for only two seconds.
readable.pipe(writable);
setTimeout(() => {
  console.log('Stop writing to output.text.');

  // Calling unpipe method
  readable.unpipe(writable);
  console.log('close the file stream.');

  //Calling end method
  writable.end();
}, 2000);
console.log("done");
```

**输出:**

```
done
Stop writing to output.text.
close the file stream.

```

**参考:**[https://nodejs . org/API/stream . html # stream _ readable _ unpip _ destination](https://nodejs.org/api/stream.html#stream_readable_unpipe_destination)。