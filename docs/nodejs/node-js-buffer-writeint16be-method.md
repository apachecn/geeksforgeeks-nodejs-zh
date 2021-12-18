# Node.js Buffer.writeInt16BE()方法

> 原文:[https://www . geesforgeks . org/node-js-buffer-write int 16 be-method/](https://www.geeksforgeeks.org/node-js-buffer-writeint16be-method/)

**Buffer.writeInt16BE()方法**是 Buffer 模块内类 Buffer 的内置应用编程接口，用于以大端格式将整数值写入指定偏移量处的 Buffer。整数值应该是有效的带符号 16 位整数。如果该值超出有符号 16 位整数的范围，则会引发错误。整数值被解释并写成二进制补码有符号整数。

**语法:**

```
Buffer.writeInt16BE( value, offset )
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **值:**是必须写入缓冲区的 16 位有符号整数。
*   **偏移量:**是一个整数值，即开始写入缓冲区之前要跳过的字节数。偏移值位于 **0 到 buf.length-2** 之间。它是可选参数，默认值为 0。

**返回值:**返回一个整数值，即偏移量加上写入的字节数之和。

下面的例子说明了 Node.js 中 **buf.writeInt16BE()** 方法的使用:

**例 1:**

```
// Node.js program to demonstrate the   
// Buffer.writeInt16BE() Method 

// Allocate a buffer
const buf = Buffer.allocUnsafe(2);

// Writing the value to the buffer
buf.writeInt16BE(0x7bca);

// Display the buffer value
console.log(buf);
```

**输出:**

```
<Buffer 7b ca>
```

**例 2:**

```
// Node.js program to demonstrate the   
// Buffer.writeInt16BE() Method 

// Allocate a buffer
const buf = Buffer.allocUnsafe(4);

// Writing the value to the buffer
// from 0 offset
buf.writeInt16BE(0x7bca, 0);

// Writing the value to the buffer
// from 2 offset
buf.writeInt16BE(0x7fff, 2);

// Display the result
console.log(buf); 
```

**输出:**

```
<Buffer 7b ca 7f ff>
```

**例 3:**

```
// Node.js program to demonstrate the   
// Buffer.writeInt16BE() Method 

// Allocate a buffer
const buf = Buffer.allocUnsafe(4);

// Writing the value to the buffer
// from 0 offset
buf.writeInt16BE(0x7bca, 0);

// Writing the value to the buffer
// from 2 offset
buf.writeInt16BE(0x7fff, 3);

// Display the result
console.log(buf); 
```

**输出:**

```
internal/buffer.js:72
  throw new ERR_OUT_OF_RANGE(type || 'offset',
  ^
RangeError [ERR_OUT_OF_RANGE]: The value of "offset" is out of range.
It must be >= 0 and <= 3 2\. received . .< pre>**参考:**[https://nodejs . org/API/buffer . html # buff _ writeint 16 be _ value _ offset](https://nodejs.org/api/buffer.html#buffer_buf_writeint16be_value_offset)

=>
```