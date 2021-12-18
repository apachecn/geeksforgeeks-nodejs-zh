# node . js buffer . writebiguint64be()方法

> 原文:[https://www . geesforgeks . org/node-js-buffer-writebiguint 64 be-method/](https://www.geeksforgeeks.org/node-js-buffer-writebiguint64be-method/)

**Buffer.writeBigUInt64BE()方法**是 Buffer 模块中类 Buffer 的内置应用编程接口，用于将大端 64 位大整数值写入指定偏移量处的已分配缓冲区。

**语法:**

```
Buffer.writeBigUInt64BE( value, offset )
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **值:**此参数指定要写入缓冲区的大整数值。它应该是一个有效的 64 位大端大整数值。当值不是这个值时，行为是未定义的。
*   **偏移量:**它指定写入前要跳过的字节数，或者简单地表示缓冲区中的索引。偏移值为 **0 < =偏移< =缓冲长度–8**。其默认值为 0。

**返回值:**该方法返回一个无符号整数值，即偏移量和写入字节数之和。

下面的例子说明了在 Node.js 中使用 Buffer.writeBigUInt64BE()方法:

**示例 1:**
**文件名:index.js**

```
// Node.js program to demonstrate the
// buffer.writeBigUInt64BE() method 
const buf = Buffer.allocUnsafe(8);

// wWiting big integer value into buffer
// by using writeBigUInt64BE() method
buf.writeBigUInt64BE(0x01030405060708n, 0);

// Display the buffer
console.log(buf);
```

使用以下命令运行 **index.js** 文件“
:

```
node index.js
```

**输出:**

```
<Buffer 00 01 03 04 05 06 07 08>

```

**示例 2:**
**文件名:index.js**

```
// Node.js program to demonstrate the
// buffer.writeBigUInt64BE() method 
const buf = Buffer.allocUnsafe(8);

// writing big integer value into buffer
// by using writeBigUInt64BE() method
buf.writeBigUInt64BE(0xaa03040506efffn, 0);

// display the buffer
console.log(buf);
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
<Buffer 00 aa 03 04 05 06 ef ff>

```

**参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/buffer . html # buffer _ buf _ writebiguint64 be _ value _ offset](https://nodejs.org/dist/latest-v12.x/docs/api/buffer.html#buffer_buf_writebiguint64be_value_offset)