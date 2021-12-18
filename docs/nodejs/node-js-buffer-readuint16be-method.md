# Node.js Buffer.readUInt16BE()方法

> 原文:[https://www . geesforgeks . org/node-js-buffer-readuint 16 be-method/](https://www.geeksforgeeks.org/node-js-buffer-readuint16be-method/)

**Buffer.readUInt16BE()方法**是 Buffer 模块中类 Buffer 的内置应用编程接口，用于从指定偏移量处分配的缓冲区中读取 16 位值。

**语法:**

```
Buffer.readUInt16BE( offset )
```

**参数:**该方法接受单参数**偏移量**，该偏移量指定读取前要跳过的字节数，或者简单地表示缓冲区中的索引。缓冲值位于 **0 < =偏移< =缓冲长度–2**。其默认值为 0。

**返回值:**这个方法返回一个无符号的 16 位整数值，它是从缓冲区以大端格式读取的(Buffer.readUInt16LE()以小端格式读取 16 位)。

下面的例子说明了在 Node.js 中使用 Buffer.readUInt16BE()方法:

**例 1:**

```
// Node.js program to demonstrate the 
// Buffer.readUInt16BE() method 

// Allocating buffer from array
const buf = Buffer.from([0x21, 0x09, 0x19, 0x98]);

// Printing allocated buffer
console.log(buf);

// Reading 16bits data from the buffer
// and printing it as a string
console.log(buf.readUInt16BE(0).toString(16));
console.log(buf.readUInt16BE(1).toString(16));
console.log(buf.readUInt16BE(2).toString(16));
```

**输出:**

```
<Buffer 21 09 19 98>
2109
919
1998

```

**例 2:**

```
// Node.js program to demonstrate the 
// Buffer.readUInt16BE() method 

// Allocating buffer from array
const buf = Buffer.from([0x21, 0x09, 0x19, 0x98]);

// Printing allocated buffer
console.log(buf);

// Reading 16bits data from the buffer
// and printing it as a string
console.log(buf.readUInt16BE(0).toString(16));
console.log(buf.readUInt16LE(0).toString(16));
console.log(buf.readUInt16BE(1).toString(16));
console.log(buf.readUInt16LE(1).toString(16));
console.log(buf.readUInt16BE(2).toString(16));
console.log(buf.readUInt16LE(2).toString(16));
```

**输出:**

```
<Buffer 21 09 19 98>
2109
921
919
1909
1998
9819

```

**例 3:**

```
// Node.js program to demonstrate the 
// Buffer.readUInt16BE() method 

// Allocating buffer from array
const buf = Buffer.from([0x21, 0x09, 0x19, 0x98]);

// Printing allocated buffer
console.log(buf);

// Reading 16bits data from the buffer
// and printing it as a string
console.log(buf.readUInt16BE(0).toString(16));
console.log(buf.readUInt16BE(1).toString(16));
console.log(buf.readUInt16BE(2).toString(16));

// Wrong index is provided to produce error
console.log(buf.readUInt16BE(3).toString(16));
```

**输出:**

```
<Buffer 21 09 19 98>
2109
919
1998
internal/buffer.js:49
  throw new ERR_OUT_OF_RANGE(type || 'offset',
  ^
RangeError [ERR_OUT_OF_RANGE]: The value of "offset" is out of range.
It must be >= 0 and <= 2\. Received 3
    at boundsError (internal/buffer.js:49:9)
    at Buffer.readUInt16BE (internal/buffer.js:215:5)
    . . .

```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/API/buffer . html # buffer _ buf _ readuint 16 be _ offset](https://nodejs.org/api/buffer.html#buffer_buf_readuint16be_offset)