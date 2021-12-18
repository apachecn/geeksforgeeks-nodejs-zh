# Node.js Buffer.readInt16LE()方法

> 原文:[https://www . geesforgeks . org/node-js-buffer-readint 16le-method/](https://www.geeksforgeeks.org/node-js-buffer-readint16le-method/)

**Buffer.readUInt16LE()方法**是 Buffer 模块中类 Buffer 的内置应用编程接口，用于以小端格式从指定偏移量的已分配缓冲区中读取 16 位值。

**语法:**

```js
Buffer.readUInt16LE(offset)
```

**参数:**该方法接受单参数**偏移量**，该偏移量指定读取前要跳过的字节数，或者简单地表示缓冲区中的索引。偏移量的值为 **0 < =偏移量< =缓冲区长度–2**。其默认值为 0。

**返回值:**这个方法返回一个从缓冲区读取的小端格式的整数值。

下面的例子说明了在 Node.js 中使用 Buffer.readUInt16LE()方法:

**例 1:**

```js
// Node program to demonstrate the  
// Buffer.readInt16LE() Method

// Allocating buffer from array
const buf = Buffer.from([0x21, 0x09, 0x19, 0x98]);

// Printing allocated buffer
console.log(buf);

// Reading 16bits data from the buffer
// and printing it as a string
console.log(buf.readUInt16LE(0).toString(16));
console.log(buf.readUInt16LE(1).toString(16));
console.log(buf.readUInt16LE(2).toString(16));
```

**输出:**

```js
<Buffer 21 09 19 98>
921
1909
9819

```

**例 2:**

```js
// Node program to demonstrate the  
// Buffer.readInt16LE() Method

// Allocating buffer from array
const buf = Buffer.from([0x21, 0x09, 0x19, 0x98]);

// Printing allocated buffer
console.log(buf);

// Reading 16bits data from the buffer
// and printing it as a string
console.log(buf.readUInt16LE(0).toString(16));
console.log(buf.readUInt16BE(0).toString(16));
console.log(buf.readUInt16LE(1).toString(16));
console.log(buf.readUInt16BE(1).toString(16));
console.log(buf.readUInt16LE(2).toString(16));
console.log(buf.readUInt16BE(2).toString(16));
```

**输出:**

```js
<Buffer 21 09 19 98>
921
2109
1909
919
9819
1998

```

**例 3:**

```js
// Node program to demonstrate the  
// Buffer.readInt16LE() Method

// Allocating buffer from array
const buf = Buffer.from([0x21, 0x09, 0x19, 0x98]);

// Printing allocated buffer
console.log(buf);

// Reading 16bits data from the buffer
// and printing it as a string
console.log(buf.readUInt16LE(0).toString(16));
console.log(buf.readUInt16LE(1).toString(16));
console.log(buf.readUInt16LE(2).toString(16));

// Wrong index is provoded to produce error
console.log(buf.readUInt16LE(3).toString(16));
```

**输出:**

```js
<Buffer 21 09 19 98>
921
1909
9819
internal/buffer.js:49
  throw new ERR_OUT_OF_RANGE(type || 'offset',
  ^
RangeError [ERR_OUT_OF_RANGE]: The value of "offset" is out of range.
It must be >= 0 and <= 2\. Received 3
    at boundsError (internal/buffer.js:49:9)
    at Buffer.readUInt16LE (internal/buffer.js:128:5)
    . . .

```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**T2】https://nodejs . org/API/buffer . html # buffer _ buf _ readuint 16 le _ offset