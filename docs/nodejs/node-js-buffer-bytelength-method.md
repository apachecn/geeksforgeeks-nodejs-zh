# Node.js Buffer.byteLength()方法

> 原文:[https://www . geesforgeks . org/node-js-buffer-bytelength-method/](https://www.geeksforgeeks.org/node-js-buffer-bytelength-method/)

**Buffer.byteLength()方法**用于返回指定缓冲对象的长度(以字节为单位)。

**语法:**

```
Buffer.byteLength( string, encoding )
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **字符串**为必选项，用于指定计算缓冲区长度的对象。支持的字符串类型有字符串、缓冲区、类型缓冲区、数据视图和数组缓冲区。
*   **编码:**为可选参数。如果对象是字符串，此参数指定其编码方案。编码方案的默认值为“utf8”。

**返回值:**返回指定对象的字节数。

**例 1:**

```
// Node.js program to demonstrate the
// Buffer.bytelength() method

// Create a buffer
var buf = Buffer.alloc(20);

// Check the length of a buffer object:
var lenobj = Buffer.byteLength(buf);

console.log(lenobj);
```

**输出:**

```
20
```

**例 2:**

```
// Node.js program to demonstrate the
// Buffer.bytelength() method

// Check the length of a buffer object:
var len = Buffer.byteLength('GeeksForGeeks');

console.log(len);
```

**输出:**

```
13
```

**注:**

*   在 Node.js v7.0.0 中，无效的输入参数会引发错误。
*   在 Node.js v5.10 中，字符串参数的值可以是任何类型的 dArray、DataView 或 ArrayBuffer。
*   这个方法被添加到 node.js v0.1.90 中。

**参考:**
[https://nodejs . org/docs/latest-v 11 . x/API/buffer . html # buffer _ class _ method _ buffer _ byte length _ string _ encoding](https://nodejs.org/docs/latest-v11.x/api/buffer.html#buffer_class_method_buffer_bytelength_string_encoding)