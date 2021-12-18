# Node.js Buffer.writeDoubleBE()方法

> 原文:[https://www . geesforgeks . org/node-js-buffer-write double be-method/](https://www.geeksforgeeks.org/node-js-buffer-writedoublebe-method/)

**Buffer.writeDoubleBE()方法**是 Buffer 模块中类 Buffer 的内置应用编程接口，用于将大端 64 位双精度值写入指定偏移量处的已分配缓冲区。

**语法:**

```
Buffer.writeDoubleBE( value, offset )
```

**参数:**此方法接受两个参数，如上所述，如下所述:

*   **Value:** This parameter specifies the 4-byte floating-point value to be written into the buffer. It should be a valid 64-bit big double precision value. When the value is not this value, the behavior is undefined.
*   **Offset:** It specifies the number of bytes to skip before writing, or simply indicates the index in the buffer. The value of offset is **0 < = offset < = buffer length–8** . Its default value is 0.

**返回值:**这个方法返回一个整数值，它是偏移量和写入字节数的和。

下面的例子说明了在 Node.js 中使用 Buffer.writeDoubleBE()方法:

**例 1:**

```
// Node.js program to demonstrate the 
// Buffer.writeDoubleBE() method 

// Allocating 32 bytes buffer
const buf = Buffer.allocUnsafe(32);

// Writing 64bits or 8 bytes double values
// to the buffer and printing returned
//  value to console
console.log(buf.writeDoubleBE(123.123, 0));
console.log(buf.writeDoubleBE(166.089, 8));
console.log(buf.writeDoubleBE(231.678, 16));
console.log(buf.writeDoubleBE(341.781, 24));

// Display the buffer
console.log(buf);
```

**输出:**

```
8
16
24
32
<Buffer 40 5e c7 df 3b 64 5a 1d 40 64 c2 d9 16 87 2b
02 40 6c f5 b2 2d 0e 56 04 40 75 5c 7e f9 db 22 d1>

```

**例 2:**

```
// Node.js program to demonstrate the 
// Buffer.writeDoubleBE() method 

// Allocating 16 bytes buffer
const buf = Buffer.allocUnsafe(16);

// Printing buffer before writing value
console.log("Before writing into buffer:");
console.log(buf);

// Writing 64 bits or 8 bytes double values
// to the buffer and printing returned
// value to console
console.log(buf.writeDoubleBE(219.098, 0));
console.log(buf.writeFloatBE(169.096, 8));

// Printing the buffer after writing into buffer
console.log("After writing into buffer:");
console.log(buf);
```

**输出:**

```
Before writing into buffer:
<Buffer f8 02 ff bc f8 01 00 00 f8 02 ff bc f8 01 00 00>
8
12
After writing into buffer:
<Buffer 40 6b 63 22 d0 e5 60 42 43 29 18 93 f8 01 00 00>

```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/API/buffer . html # buff _ write double be _ value _ offset](https://nodejs.org/api/buffer.html#buffer_buf_writedoublebe_value_offset)