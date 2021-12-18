# Node.js Buffer.readInt8()方法

> 原文:[https://www . geesforgeks . org/node-js-buffer-readint 8-method/](https://www.geeksforgeeks.org/node-js-buffer-readint8-method/)

**Buffer.readUInt8()方法**用于从具有特定偏移量的中读取缓冲区中的无符号 8 位整数。

**语法:**

```
Buffer.readInt8( offset )
```

**参数:**该方法接受单参数**偏移量**，表示开始读取前要跳过的字节数。偏移值位于范围 **0 到缓冲区长度–1**之间。其默认值为 0。

**返回值:**该方法返回指定偏移量处的 8 位有符号整数值。

**例 1:**

```
// Node.js program to demonstrate the
// buffer.readUInt8() method
const value = Buffer.from([ -2, 3 ]);

// Reads the first value
console.log(value.readInt8(0));

// Reads the second value
console.log(value.readInt8(1));

// Throws an error
console.log(value.readInt8(2));
```

**输出:**

```
-2
3
RangeError [ERR_OUT_OF_RANGE]: The value of "offset" is out of range.

```

**例 2**

```
// Node.js program to demonstrate the
// buffer.readUInt8() method
const obj = Buffer.from([ 0X52, 0X40, 0X78 ]);

// It returns the first value
console.log(obj.readUInt8(0));

// It returns the third value
console.log(obj.readUInt8(2));
const temp = Buffer.from("XYZ");

// It returns the ASCII value of capital 'X'
console.log(temp.readUInt8(0));
```

**输出:**

```
82
120
88

```

**注意:**从缓冲区读取的整数显示为二进制补码有符号值。

**参考:**[https://nodejs . org/API/buffer . html # buffer _ buf _ readint 8 _ offset](https://nodejs.org/api/buffer.html#buffer_buf_readint8_offset)