# Node.js Buffer.writeUInt16BE()方法

> 原文:[https://www . geesforgeks . org/node-js-buffer-writeuint 16 be-method/](https://www.geeksforgeeks.org/node-js-buffer-writeuint16be-method/)

**Buffer.writeUInt16BE()方法**用于使用大端格式将指定的字节写入缓冲对象。该值应为有效的无符号 16 位整数。

**语法:**

```js
Buffer.writeUInt16BE( value, offset )
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **Value:** It is an integer value to be written into the buffer.
*   **Offset:** is an integer value, indicating the number of bytes to skip before writing, and the offset value is in the range of **0 to buffer.length–2** . Its default value is 0.

**返回值:**返回偏移量加上写入字节数的整数值。

**例 1:**

```js
// Node.js program to demonstrate the  
// Buffer.writeUInt16BE() Method

// Allocate a buffer
const buf = Buffer.allocUnsafe(4);

// Write the buffer element in BE format
buf.writeUInt16BE(0xabcd, 0);

// Display the buffer list
console.log(buf);

// Write the buffer element in BE format
buf.writeUInt16BE(0xfede, 2)

// Display the buffer list
console.log(buf);
```

**输出:**

```js
<Buffer ab cd f4 09>
<Buffer ab cd fe de>

```

**例 2:**

```js
// Node.js program to demonstrate the  
// Buffer.writeUInt16BE() Method

// Allocate a buffer
const buf = Buffer.allocUnsafe(4);

// Write the buffer element in BE format
buf.writeUInt16BE(0xabab, 0);

// Display the buffer list
console.log(buf);

// Write the buffer element in BE format
buf.writeUInt16BE(0xefde, 2);

// Display the buffer list
console.log(buf);
```

**输出:**

```js
<Buffer ab ab ad 09>
<Buffer ab ab ef de>

```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/API/buffer . html # buff _ writeuint 16 be _ value _ offset](https://nodejs.org/api/buffer.html#buffer_buf_writeuint16be_value_offset)