# Node.js Buffer.writeUInt32BE()方法

> 原文:[https://www . geesforgeks . org/node-js-buffer-writeuint 32 be-method/](https://www.geeksforgeeks.org/node-js-buffer-writeuint32be-method/)

Buffer.writeUInt32BE()方法用于向 Buffer 类的实例中写入一个数字。该值以大端格式写入指定的偏移量。

**语法:**

```js
buffer.writeUInt32BE(value, offset)
```

**参数:**此方法接受两个参数，如上所述，如下所述:

*   **Value:** This parameter holds the number to be written. It should be a valid unsigned 32-bit integer. In addition, no behavior is defined for invalid values.
*   **Offset:** This parameter stores the number of bytes to skip. The value must be in the range [0, buffer.length–4]. It is an optional parameter with a default value of zero.

**返回值:**该参数返回写入字节数和偏移量之和。

**例 1:**

```js
// Node.js program to demonstrate the 
// Buffer.writeUInt32BE method

// Creating a buffer of size 8
const buffer = Buffer.allocUnsafe(8);

console.log(buffer);

// Return value is 4 
buffer.writeUInt32BE(0xabcdabcd, 0);

console.log(buffer);

// Return value is 8
buffer.writeUInt32BE(0xabcdabcd, 4);

console.log(buffer);
```

**输出:**

```js
<Buffer 6c 69 63 65 00 00 00 00>
<Buffer ab cd ab cd 00 00 00 00>
<Buffer ab cd ab cd ab cd ab cd>

```

**例 2:**

```js
// Node.js program to demonstrate the 
// Buffer.writeUInt32BE method

// Creating a buffer of size 8
const buffer = Buffer.allocUnsafe(8);

console.log(buffer);

// Out of range error will be thrown
buffer.writeUInt32BE(0xabcdabcd, 5);
```

**输出:**

```js
<Buffer b0 f1 67 fc 63 7f 00 00>
Thrown:
RangeError [ERR_OUT_OF_RANGE]  ........

```

**参考:**[https://nodejs . org/API/buffer . html # buffer _ buf _ readint 32 be _ offset](https://nodejs.org/api/buffer.html#buffer_buf_readint32be_offset)