# Node.js Buffer.writeUInt16LE()方法

> 原文:[https://www . geesforgeks . org/node-js-buffer-writeuint 16le-method/](https://www.geeksforgeeks.org/node-js-buffer-writeuint16le-method/)

**Buffer.writeUInt16LE()方法**用于将**小端**格式的指定字节写入缓冲对象。这里，值应该是有效的无符号 16 位整数。

**语法:**

```
Buffer.writeUInt16LE( value, offset )
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **Value:** It is an integer value and will be written into the buffer.
*   **Offset** is an integer value, which indicates the number of bytes to skip before writing. The value of offset is in the range of **0 to buffer.length–2** , and the default value is 0.

**返回值:**返回一个整数值**偏移量**加上写入的字节数。

**例 1:**

```
// Node.js program to demonstrate the
//Buffer.writeUInt16LE() Method
const buff = Buffer.allocUnsafe(4);

buff.writeUInt16LE(0xdead, 0);
console.log(buff);

buff.writeUInt16LE(0xbeef, 2)
console.log(buff);
```

**输出:**

```
<Buffer ad de 00 00>
<Buffer ad de ef be>

```

**例 2:**

```
// Node.js program to demonstrate the
//Buffer.writeUInt16LE() Method
const buff = Buffer.allocUnsafe(4);

buff.writeUInt16LE(0xfeed, 0);
console.log(buff);

buff.writeUInt16LE(0xabcd, 2);
console.log(buff);
```

**输出:**

```
<Buffer ed fe 00 00>
<Buffer ed fe cd ab>

```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/API/buffer . html # buff _ writeuint16le _ value _ offset](https://nodejs.org/api/buffer.html#buffer_buf_writeuint16le_value_offset)