# node . js buffer . writebigint 64 le()方法

> 原文:[https://www . geesforgeks . org/node-js-buffer-writebigint 64 le-method/](https://www.geeksforgeeks.org/node-js-buffer-writebigint64le-method/)

**Buffer.writeBigInt64LE()方法**是 Buffer 模块中类 Buffer 的内置应用编程接口，用于将小端 64 位大整数值写入指定偏移量处的已分配缓冲区。

**语法:**

```js
Buffer.writeBigInt64LE( value, offset )
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **值:**此参数指定要写入缓冲区的大整数值。它应该是一个有效的 64 位小端大整数值。当值不是这个值时，行为是未定义的。
*   **偏移量:**它指定写入前要跳过的字节数，或者简单地表示缓冲区中的索引。偏移值为 **0 < =偏移< =缓冲长度–8**。其默认值为 0。

**返回值:**这个方法返回一个整数值，它是偏移量和写入字节数的和。

下面的例子说明了在 Node.js 中使用 Buffer.writeBigInt64LE()方法:

**示例 1:**
**文件名:index.js**

```js
// Node.js program to demonstrate the
// buffer.writeBigInt64lE() method 
const buf = Buffer.allocUnsafe(8);

// Writing big integer value into buffer
// by using writeBigInt64LE() method
buf.writeBigInt64LE(0x01030405060708n, 0);

// Display the buffer
console.log(buf);
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
<Buffer 08 07 06 05 04 03 01 00>

```

**示例 2:**
**文件名:index.js**

```js
// Node.js program to demonstrate the
// buffer.writeBigInt64lE() method 
const buf = Buffer.allocUnsafe(8);

// Writing big integer value into buffer
// by using writeBigInt64LE() method
buf.writeBigInt64LE(0xaa03040506efffn, 0);

// Display the buffer
console.log(buf);
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
<Buffer ff ef 06 05 04 03 aa 00>

```

**参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/buffer . html # buffer _ buf _ writebigint 64 le _ value _ offset](https://nodejs.org/dist/latest-v12.x/docs/api/buffer.html#buffer_buf_writebigint64le_value_offset)