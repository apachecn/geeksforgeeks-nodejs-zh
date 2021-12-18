# Node.js Buffer.writeUInt8()方法

> 原文:[https://www . geesforgeks . org/node-js-buffer-writeuint 8-method/](https://www.geeksforgeeks.org/node-js-buffer-writeuint8-method/)

**Buffer.writeUInt8()方法**是 Buffer 模块中类 **Buffer** 的内置应用编程接口，用于将值写入指定偏移量处的缓冲区。该值应为有效的无符号 8 位整数，否则行为未定义。

**语法:**

```js
Buffer.writeUInt8( value, offset )
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **Value:** The unsigned integer value to be written into the buffer.
*   **Offset:** indicates the number of bytes to skip before writing to the buffer. The offset can be in the range of **0 < = offset < = buf.length–1** . The default value of offset for is 0.

**返回值:**返回在指定偏移量插入值的缓冲区。

下面的例子说明了 **Buffer.writeUInt8()** 方法在 Node.js 中的使用:

**例 1:**

```js
// Node.js program to demonstrate the 
// Buffer.writeUInt8() method 

// Creating a buffer 
const buf = Buffer.allocUnsafe(5);

// Using Buffer.writeUInt8() method
buf.writeUInt8(0x14, 0);

// Display the buffer
console.log(buf); 

// Using Buffer.writeUInt8() method
buf.writeUInt8(0x15, 1);

// Display the buffer
console.log(buf); 

// Using Buffer.writeUInt8() method
buf.writeUInt8(0x16, 4);

// Display the buffer
console.log(buf); 

// Using Buffer.writeUInt8() method
buf.writeUInt8(0x17, 3);

// Display the buffer
console.log(buf); 

// Using Buffer.writeUInt8() method
buf.writeUInt8(0x18, 2);

// Display the result 
console.log(buf); 
```

**输出:**

```js
<Buffer 14 00 00 00 d6>
<Buffer 14 15 00 00 d6>
<Buffer 14 15 00 00 16>
<Buffer 14 15 00 17 16>
<Buffer 14 15 18 17 16>

```

**例 2:**

```js
// Node.js program to demonstrate the 
// Buffer.writeUInt8() method 

// Creating a buffer 
const buf = Buffer.allocUnsafe(3);

// Using Buffer.writeUInt8() method
buf.writeUInt8(0x11, 0);

// Display the buffer
console.log(buf); 

// Using Buffer.writeUInt8() method
buf.writeUInt8(0x22, 1);

// Display the buffer
console.log(buf); 

// Using Buffer.writeUInt8() method
buf.writeUInt8(0x33, 2);

// Display the buffer
console.log(buf); 
```

**输出:**

```js
<Buffer 11 e7 31>
<Buffer 11 22 31>
<Buffer 11 22 33>

```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/dist/latest-v 13 . x/docs/API/buffer . html # buffer _ buf _ writeuint 8 _ value _ offset](https://nodejs.org/dist/latest-v13.x/docs/api/buffer.html#buffer_buf_writeuint8_value_offset)