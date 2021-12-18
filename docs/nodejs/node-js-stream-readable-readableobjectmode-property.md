# Node.js Stream 可读. readableObjectMode 属性

> 原文:[https://www . geesforgeks . org/node-js-stream-readable object mode-property/](https://www.geeksforgeeks.org/node-js-stream-readable-readableobjectmode-property/)

可读流中的**可读. readableObjectMode 属性**，用于检查流的*对象模式*。

**语法:**

```js
readable.readableObjectMode
```

**返回值:**返回*布尔*值。

下面的例子说明了在 Node.js 中使用【readable.readableObjectMode 属性:

**例 1:**

```js
// Node.js program to demonstrate the     
// readable.readableObjectMode Property

// Accessing readable stream module
const Readable = require('readable-stream').Readable;

// Constructing readable stream and
// setting the objectMode value
const readable = Readable({objectMode: true});

// Defining ._read method
readable._read = () => {};

// Instructions for reading data
readable.on('readable', () => {
  let chunk;

  // Using while loop and calling
  // read method with parameter
  while (null !== (chunk = readable.read(4))) {

    // Displaying the chunk
    console.log(`read: ${chunk}`);
  }
});

// Calling readableObjectMode
// Property
readable.readableObjectMode;
console.log("objectMode is true!!");
```

**输出:**

```js
objectMode is true!!

```

**例 2:**

```js
// Node.js program to demonstrate the     
// readable.readableObjectMode Property

// Accessing readable stream module
const Readable = require('readable-stream').Readable;

// Constructing readable stream and
// setting the objectMode value
const readable = Readable({objectMode: false});

// Defining ._read method
readable._read = () => {};

// Instructions for reading data
readable.on('readable', () => {
  let chunk;

  // Using while loop and calling
  // read method with parameter
  while (null !== (chunk = readable.read(4))) {

    // Displaying the chunk
    console.log(`read: ${chunk}`);
  }
});

// Calling readableObjectMode
// Property
readable.readableObjectMode;
console.log("objectMode is false!!");
```

**输出:**

```js
objectMode is false!!
```

**参考:**[https://nodejs . org/API/stream . html # stream _ readable _ readable object mode](https://nodejs.org/api/stream.html#stream_readable_readableobjectmode)