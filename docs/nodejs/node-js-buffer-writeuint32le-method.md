# Node.js Buffer.writeUInt32LE()方法

> 原文:[https://www . geesforgeks . org/node-js-buffer-writeuint 32 le-method/](https://www.geeksforgeeks.org/node-js-buffer-writeuint32le-method/)

**Buffer.writeUInt32LE()方法**用于使用小端格式将指定的字节写入缓冲对象。该值包含有效的未赋值 32 位整数。

**语法:**

```js
Buffer.writeUInt32LE( value, offset )
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **Value:** It is an integer value to be written into the buffer.
*   **Offset:** is an integer value, indicating the number of bytes to skip before writing, and the offset value is in the range of **0 to buffer.length–4** . Its default value is 0.

**返回值:**返回偏移量加上写入字节数的整数值。

**例 1:**

```js
// Node.js program to demonstrate the  
// Buffer.writeUInt32LE() Method

// Allocate a buffer
const buf = Buffer.allocUnsafe(4);

// Write the buffer element in LE format
buf.writeUInt32LE(0xabcdabcd, 0);

// Display the buffer list
console.log(buf);

// Write the buffer element in LE format
buf.writeUInt32LE(0xfacedcba, 0);

// Display the buffer list
console.log(buf);
```

**输出:**

```js
<Buffer cd ab cd ab>
<Buffer ba dc ce fa>

```

**例 2:**

```js
// Node.js program to demonstrate the  
// Buffer.writeUInt32LE() Method

// Allocate a buffer
const buf = Buffer.allocUnsafe(4);

// Write the buffer element in LE format
buf.writeUInt32LE(0xabce, 0);

// Display the buffer list
console.log(buf);

// Write the buffer element in LE format
buf.writeUInt32LE(0xeab, 0);

// Display the buffer list
console.log(buf);
```

**输出:**

```js
<Buffer ce ab 00 00>
<Buffer ab 0e 00 00>

```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**T2【https://nodejs . org/API/buffer . html # buff _ writeuint32 le _ value _ offset