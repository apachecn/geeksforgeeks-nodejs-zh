# node . js Stream transform . destroy()方法

> 原文:[https://www . geesforgeks . org/node-js-stream-transform-destroy-method/](https://www.geeksforgeeks.org/node-js-stream-transform-destroy-method/)

可读流中的 **transform.destroy()方法**用于销毁转换流，并可选地发出“错误”事件。此外，转换流会在调用之后释放任何内部资源。

**语法:**

```
transform.destroy( error )
```

**参数:**该方法接受单参数*误差*，该误差可选地发出一个误差事件。

**返回值:**如果在创建流时出错，它会发出错误事件，否则它只会破坏转换流。

以下示例说明了在 Node.js 中使用 **transform.destroy()方法**:

**例 1:**

```
// Node.js program to demonstrate the     
// transform.destroy() method

// Accessing zlib module
var zlib = require("zlib");

// Create a transform stream
var transform = zlib.createGzip();

// Calling destroy method
transform.destroy();
transform.destroyed;
```

**输出:**

```
true
```

**例 2:**

```
// Node.js program to demonstrate the     
// transform.destroy() method

// Accessing fs module
var fs = require("fs");

// Accessing zlib module
var zlib = require("zlib");

// Create a readable stream
var readable = fs.createReadStream('input.text');

// Create a writable stream
var writable = fs.createWriteStream('output.text');

// Create a transform stream
var transform = zlib.createGzip();

// Calling pipe method
readable.pipe(transform).pipe(writable);

// Calling destroy method
transform.destroy();
console.log("done...");
```

**输出:**

```
done...
```

在这里，转换流被破坏，因此制作的管道也被移除。

**参考:**[https://nodejs . org/API/stream . html # stream _ transform _ destroy _ error](https://nodejs.org/api/stream.html#stream_transform_destroy_error)