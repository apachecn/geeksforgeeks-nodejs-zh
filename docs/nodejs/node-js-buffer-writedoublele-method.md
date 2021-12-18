# Node.js Buffer.writeDoubleLE()方法

> 原文:[https://www . geesforgeks . org/node-js-buffer-write double-method/](https://www.geeksforgeeks.org/node-js-buffer-writedoublele-method/)

**Buffer.writeDoubleLE()方法**是 Buffer 模块中类 Buffer 的内置应用编程接口，它以指定的字节序格式在指定的偏移量处将值写入缓冲区。请注意，该值必须是有效的 64 位双精度值。
**语法:**

```js
Buffer.writeDoubleLE(value, offset)
```

参数 **:** 该方法接受两个参数，如上所述，描述如下:

*   **值:**此参数保存要写入缓冲区的数字。
*   **偏移量:**此参数保存开始写入前要跳过的字节数(整数)。

**返回值:**返回偏移量和写入的字节数。
**例 1:**

## java 描述语言

```js
// Node.js program to demonstrate the
// Buffer.writeDoubleLE() method

// Create a buffer
const buf = Buffer.allocUnsafe(8);

// Use writeDoubleLE() method
buf.writeDoubleLE(123.456, 0);

// Display the buffer value
console.log(buf);
```

**输出:**

```js
<Buffer 77 be 9f 1a 2f dd 5e 40>
```

**例 2:**

## java 描述语言

```js
// Node.js program to demonstrate the
// Buffer.writeDoubleLE() method

// Create a buffer
var buf = Buffer.allocUnsafe(16);

// Use writeDoubleLE() method
buf.writeDoubleLE(0xcafebabe, 4);

// Display the buffer value
console.log(buf);
```

**输出:**

```js
<Buffer 28 83 db 7c 00 00 c0 57 d7 5f e9 41 00 00 00 00>
```

**参考:**T2T4】