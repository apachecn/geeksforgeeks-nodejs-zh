# node . js buffer . write float()方法

> 原文:[https://www . geesforgeks . org/node-js-buffer-write float-method/](https://www.geeksforgeeks.org/node-js-buffer-writefloatle-method/)

**Buffer . writefloattle()方法**是一个内置的类 Buffer 的应用编程接口，带有 in Buffer 模块，以指定的小端格式在指定的偏移量向缓冲区写入一个值。请注意，该值必须是有效的 32 位浮点值。

**语法:**

```js
Buffer.writeFloatLE( value, offset )
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **Value:** This parameter holds a number to be written into the buffer.
*   **Offset:** This parameter stores the number of bytes (integer) to skip before writing. The offset value of is between 0 and buf.length-4\. Its default value is 0.

**返回值:**返回偏移量和写入的字节数。

**例 1:**

```js
// Node.js program to demonstrate the  
// Buffer.writeFloatLE() method 

// Creating a buffer of size 6
const buf = Buffer.allocUnsafe(10);

buf.writeFloatLE(0x1234567890ab, 0);

console.log(buf);
```

**输出:**

```js
<Buffer b4 a2 91 55 62 01 00 00 38 e0>
```

**例 2:**

```js
// Node.js program to demonstrate the  
// Buffer.writeFloatLE() method 

// Creating a buffer of size 6
const buf = Buffer.allocUnsafe(4);

buf.writeFloatLE(0xabcafebabe, 0);

console.log(buf);
```

**输出:**

```js
<Buffer ff ca 2b 53>
```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/API/buffer . html # buffer _ buf _ write float _ value _ offset](https://nodejs.org/api/buffer.html#buffer_buf_writefloatle_value_offset)