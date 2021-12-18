# Node.js Buffer.writeInt16LE()方法

> 原文:[https://www . geesforgeks . org/node-js-buffer-writeint16le-method/](https://www.geeksforgeeks.org/node-js-buffer-writeint16le-method/)

**Buffer.writeInt16LE()方法**是 Buffer 模块中类 **Buffer** 的内置应用编程接口，用于以指定的小端格式将有效的带符号 16 位整数写入指定偏移量处的缓冲区。

**语法:**

```js
Buffer.writeInt16LE( value, offset )
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **Value:** A valid signed 16-bit integer to be written into the buffer.
*   **Offset:** indicates the number of bytes to skip before writing to the buffer. The offset value is in the range of **0 < = offset < = buf.length–2** . The default value of offset for is 0.

**返回值:**以小端格式返回一个在指定偏移量插入值的缓冲区。

下面的例子说明了 **Buffer.writeInt16LE()** 方法在 Node.js 中的使用:

**例 1:**

```js
// Node.js program to demonstrate the 
// Buffer.writeInt16LE() method 

// Creating a buffer 
const buf = Buffer.allocUnsafe(10); 

// Using Buffer.writeInt16LE() method 
buf.writeInt16LE(0x0114, 0); 

// Display the buffer 
console.log(buf); 

// Using Buffer.writeInt16LE() method 
buf.writeInt16LE(0x1015, 2); 

// Display the buffer 
console.log(buf); 

// Using Buffer.writeInt16LE() method 
buf.writeInt16LE(0x0016, 8); 

// Display the buffer 
console.log(buf); 

// Using Buffer.writeInt16LE() method 
buf.writeInt16LE(0x0217, 6); 

// Display the buffer 
console.log(buf); 

// Using Buffer.writeInt16LE() method 
buf.writeInt16LE(0x0518, 4); 

// Display the result 
console.log(buf); 
```

**输出:**

```js
<Buffer 14 01 9b 02 00 00 00 00 a8 79>
<Buffer 14 01 15 10 00 00 00 00 a8 79>
<Buffer 14 01 15 10 00 00 00 00 16 00>
<Buffer 14 01 15 10 00 00 17 02 16 00>
<Buffer 14 01 15 10 18 05 17 02 16 00>

```

**例 2:**

```js
// Node.js program to demonstrate the 
// Buffer.writeInt16LE() method 

// Creating a buffer 
const buf = Buffer.allocUnsafe(6); 

// Using Buffer.writeInt16LE() method 
buf.writeInt16LE(0x2211, 0); 

// Display the buffer 
console.log(buf); 

// Using Buffer.writeInt16LE() method 
buf.writeInt16LE(0x4433, 2); 

// Display the buffer 
console.log(buf); 

// Using Buffer.writeInt16LE() method 
buf.writeInt16LE(0x6655, 4); 

// Display the buffer 
console.log(buf); 
```

**输出:**

```js
<Buffer 11 22 00 00 00 00>
<Buffer 11 22 33 44 00 00>
<Buffer 11 22 33 44 55 66>

```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/dist/latest-v 13 . x/docs/API/buffer . html # buffer _ buf _ writeint16le _ value _ offset](https://nodejs.org/dist/latest-v13.x/docs/api/buffer.html#buffer_buf_writeint16le_value_offset)