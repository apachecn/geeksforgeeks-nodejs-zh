# node . js buffer . writeuitrel()方法

> 原文:[https://www . geesforgeks . org/node-js-buffer-writeuitrel-method/](https://www.geeksforgeeks.org/node-js-buffer-writeuintle-method/)

**Buffer . writeuitrel()**方法用于使用小端字节向 Buffer 对象写入指定的字节。它支持高达 48 位的精度。当使用非无符号整数的值时，其行为是未定义的。

**语法:**

```
Buffer.writeUIntLE( value, offset, byteLength )
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **Value:** Specifies the number to be written into the Buffer object.
*   **Offset:** Specify the number of bytes to skip before writing to the buffer. The value of offset lies in **0 < = offset < = buf.length–byte length** .
*   **Byte Length:** Specifies the number of bytes written into the buffer. The value of the byte length is **0 < The byte length < = 6** .

**返回值:**返回偏移量加上写入的字节数。

下面的例子说明了在 Node.js 中使用 Buffer.writeUIntLE()方法:

**例 1:**

```
// Node.js program to demonstrate the  
// Buffer.writeUIntLE() method 

// Creating a buffer of size 4 
const buffer_1 = Buffer.allocUnsafe(4);

// Writes byteLength bytes of value to buf
// at the specified offset.
buffer_1.writeUIntLE(0x12127474, 0, 4);

// Display the result 
console.log(buffer_1);

// Creating a buffer of size 6
const buffer_2 = Buffer.allocUnsafe(6);
buffer_2.writeUIntLE(0x12127474abcd, 0, 6);

// Display the result 
console.log(buffer_2);
```

**输出:**

```
<Buffer 74 74 12 12>
<Buffer cd ab 74 74 12 12>

```

**例 2:**

```
// Node.js program to demonstrate the  
// Buffer.writeUIntLE() method 

// Creating a buffer of given size 
const buffer = Buffer.allocUnsafe(8);
//Before writing anything
console.log("Before filling buffer");
console.log(buffer);

// to fill first 6 bytes, take offset 0
// and bytelength 6
console.log("After filling 6 bytes");
buffer.writeUIntLE(0xcc1267280012, 0, 6);
console.log(buffer);

// to fill next 2 bytes add 6 offet
// and bytelength 2
console.log("After filling next 2 bytes");
buffer.writeUIntLE(0x1112, 6, 2)
console.log(buffer);
```

**输出:**

```
Before filling buffer
<Buffer 00 00 00 00 00 00 00 00>
After filling 6 bytes
<Buffer 12 00 28 67 12 cc 00 00>
After filling next 2 bytes
<Buffer 12 00 28 67 12 cc 12 11>

```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/API/buffer . html # buff _ writeuitrel _ value _ offset _ byte length](https://nodejs.org/api/buffer.html#buffer_buf_writeuintle_value_offset_bytelength)