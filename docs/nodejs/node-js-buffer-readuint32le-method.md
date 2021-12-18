# Node.js | Buffer.readUInt32LE()方法

> 原文:[https://www . geesforgeks . org/node-js-buffer-readuint 32 le-method/](https://www.geeksforgeeks.org/node-js-buffer-readuint32le-method/)

**Buffer.readUInt32LE()方法**是 Buffer 模块中类 Buffer 的内置应用编程接口，用于以小端格式从指定偏移量的已分配缓冲区中读取 32 位值。

**语法:**

```js
Buffer.readUInt32LE( offset )
```

**参数:**该方法接受单参数**偏移量**，该偏移量指定读取前要跳过的字节数，或者简单地表示缓冲区中的索引。偏移量的值为 **0 < =偏移量< =缓冲区长度–4**。其默认值为 0。

**返回值:**这个方法返回一个从缓冲区读取的小端格式的整数值。

下面的例子说明了在 Node.js 中使用 Buffer.readUInt32LE()方法:

**例 1:**

```js
// Node program to demonstrate the  
// Buffer.readUInt32LE() Method

// Allocating buffer from array
const buf = Buffer.from([0x21, 0x09, 0x19,
             0x98, 0x16, 0x09, 0x19, 0x96]);

// Printing allocated buffer
console.log(buf);

// Reading 32bits data from the buffer
// and printing it as a string
console.log(buf.readUInt32LE(0).toString(16));
console.log(buf.readUInt32LE(1).toString(16));
console.log(buf.readUInt32LE(2).toString(16));
console.log(buf.readUInt32LE(3).toString(16));
console.log(buf.readUInt32LE(4).toString(16));
```

**输出:**

```js
<Buffer 21 09 19 98 16 09 19 96>
98190921
16981909
9169819
19091698
96190916

```

**例 2:**

```js
// Node program to demonstrate the  
// Buffer.readUInt32LE() Method

// Allocating buffer from array
const buf = Buffer.from([0x21, 0x09, 0x19, 0x98,
                     0x34, 0xae, 0xe8, 0xff]);

// Printing allocated buffer
console.log(buf);

// Reading 16bits data from the buffer
// and printing it as a string
console.log(buf.readUInt32LE(0).toString(16));
console.log(buf.readUInt32BE(0).toString(16));
console.log(buf.readUInt32LE(1).toString(16));
console.log(buf.readUInt32BE(1).toString(16));
console.log(buf.readUInt32LE(2).toString(16));
console.log(buf.readUInt32BE(2).toString(16));
console.log(buf.readUInt32LE(3).toString(16));
console.log(buf.readUInt32BE(3).toString(16));
console.log(buf.readUInt32LE(4).toString(16));
console.log(buf.readUInt32BE(4).toString(16));
```

**输出:**

```js
<Buffer 21 09 19 98 34 ae e8 ff>
98190921
21091998
34981909
9199834
ae349819
199834ae
e8ae3498
9834aee8
ffe8ae34
34aee8ff

```

**例 3:**

```js
// Node program to demonstrate the  
// Buffer.readUInt32LE() Method

// Allocating buffer from array
const buf = Buffer.from([0x21, 0x09, 0x19, 0x98]);

// Printing allocated buffer
console.log(buf);

// Reading 16bits data from the buffer
// and printing it as a string
console.log(buf.readUInt32LE(0).toString(16));

// Wrong index is provoded to produce error
console.log(buf.readUInt32LE(1).toString(16));
```

**输出:**

```js
<Buffer 21 09 19 98>
98190921
internal/buffer.js:49
  throw new ERR_OUT_OF_RANGE(type || 'offset',
  ^
RangeError [ERR_OUT_OF_RANGE]: The value of "offset" is out of range. 
It must be >= 0 and <= 0\. Received 1
    at boundsError (internal/buffer.js:49:9)
    at Buffer.readUInt32LE (internal/buffer.js:105:5)
    at Object. (C:\nodejs\buf_readuint32le_2.js:10:17)
    . . .

```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**T2】https://nodejs . org/API/buffer . html # buffer _ buf _ readuint 32 le _ offset