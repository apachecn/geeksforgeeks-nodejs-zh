# Node.js Stream 可读. setEncoding()方法

> 原文:[https://www . geesforgeks . org/node-js-stream-readable-set encoding-method/](https://www.geeksforgeeks.org/node-js-stream-readable-setencoding-method/)

可读流中的**可读. setEncoding()方法**用于设置读取数据的编码。

**语法:**

```js
readable.setEncoding( encoding )
```

**参数:**该方法接受保存编码类型的单参数**编码**。

**返回值:**以编码形式返回数据。

以下示例说明了在 Node.js 中使用**可读的. setEncoding()方法**:

**例 1:**

```js
// Node.js program to demonstrate the     
// readable.setEncoding() method  

// Include fs module
const fs = require('fs');

// Create readable stream
const readable = fs.createReadStream("input.txt");

// Calling setEncoding method
readable.setEncoding('hex');

// Handling data event
readable.on('data', (chunk) => {
  console.log(`${chunk}`);
});

// Displays that program 
// is ended
console.log("Program ends!!");
```

**输出:**

```js
Program ends!!
48656c6c6f

```

**例 2:**

```js
// Node.js program to demonstrate the     
// readable.setEncoding() method  

// Include fs module
const fs = require('fs');

// Create readable stream
const readable = fs.createReadStream("input.txt");

// Calling setEncoding method
readable.setEncoding('base64');

// Handling data event
readable.on('data', (chunk) => {
  console.log(`${chunk}`);
});

// Displays that program 
// is ended
console.log("Program ends!!");
```

**输出:**

```js
Program ends!!
SGVs
bG8=

```

**参考:**[https://nodejs . org/API/stream . html # stream _ readable _ setencoding _ encoding](https://nodejs.org/api/stream.html#stream_readable_setencoding_encoding)