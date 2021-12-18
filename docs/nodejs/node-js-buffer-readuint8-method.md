# Node.js Buffer.readUInt8()方法

> 原文:[https://www . geesforgeks . org/node-js-buffer-readuint 8-method/](https://www.geeksforgeeks.org/node-js-buffer-readuint8-method/)

**Buffer.readUInt8()方法**用于从 Buffer 对象中读取无符号 8 位整数。

**语法:**

```js
buffer.readUInt8( offset )
```

**参数:**该方法接受指定缓冲对象位置的单个参数偏移量。它表示开始读取前要跳过的字节数。偏移值位于范围 **0 到缓冲区长度–1**之间。默认值为 0。

**返回值:**返回偏移量指定的整数值。

**例 1:**

```js
// Node.js program to demonstrate the
// buffer.readUInt8() method 
const ob=Buffer.from([1, 2, 3]);

// It reads the first value
console.log(ob.readUInt8(0));

// It reads the second value
console.log(ob.readUInt8(1));

// It throws an error
console.log(ob.readUInt8(4));
```

**输出:**

```js
1
2
RangeError [ERR_OUT_OF_RANGE]: The value of "offset" is out of range.
It must be >= 0 and <= 2\. Received 3
    at boundsError (internal/buffer.js:53:9)
    at Buffer.readUInt8 (internal/buffer.js:141:5)

```

**例 2:**

```js
// Node.js program to demonstrate the
// buffer.readUInt8() method 
const ob1 = Buffer.from([0X32, 0X44, 0X48]);

// It returns the first value
console.log(ob1.readUInt8(0));

// It returns the third value
console.log(ob1.readUInt8(2));
const t = Buffer.from("abc");

// It returns the ASCII value of 'a'
console.log(t.readUInt8(0));
```

**输出:**

```js
68
72
97

```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/API/buffer . html # buffer _ buf _ readuint8 _ offset](https://nodejs.org/api/buffer.html#buffer_buf_readuint8_offset)