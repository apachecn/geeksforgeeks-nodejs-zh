# node . js buffer . readuitrell()方法

> 原文:[https://www . geesforgeks . org/node-js-buffer-readuitrell-method/](https://www.geeksforgeeks.org/node-js-buffer-readuintle-method/)

**Buffer . readuitrell()方法**是 Buffer 模块中类 Buffer 的内置应用程序编程接口，用于从指定偏移量处的已分配缓冲区中读取指定数量的字节值。

**语法:**

```js
Buffer.readUIntLE( offset, byteLength )
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **Offset:** It specifies the number of bytes to skip before reading, or simply indicates the index in the buffer. The value of offset is **0 < = offset < = buffer length–byte length** . Its default value is 0.
*   **Byte Length:** Specify the number of bytes to be read. The value of the byte length is **0 < The byte length < = 6** .

**返回值:**这个方法返回一个从缓冲区读取的小端格式的整数值。

下面的例子说明了在 Node.js 中使用 Buffer.readUIntLE()方法:

**例 1:**

```js
// Node program to demonstrate the  
// Buffer.readUIntLE() Method

// Allocating buffer from array
const buf = Buffer.from([0x21, 0x09, 0x19, 0x98]);

// Printing allocated buffer
console.log(buf);

// Reading data from the buffer
// and printing it as a string
console.log(buf.readUIntLE(0, 3).toString(16));
console.log(buf.readUIntLE(1, 3).toString(16));
console.log(buf.readUIntLE(2, 2).toString(16));
```

**输出:**

```js
<Buffer 21 09 19 98>
190921
981909
9819

```

**例 2:**

```js
// Node program to demonstrate the  
// Buffer.readUIntLE() Method

// Allocating buffer from array
const buf = Buffer.from([0x21, 0x09, 0x19, 0x98]);

// Printing allocated buffer
console.log(buf);

// Reading data from the buffer
// and printing it as a string
console.log(buf.readUIntLE(0, 3).toString(16));
console.log(buf.readUIntBE(0, 3).toString(16));
console.log(buf.readUIntLE(1, 2).toString(16));
console.log(buf.readUIntBE(1, 2).toString(16));
console.log(buf.readUIntLE(2, 1).toString(16));
console.log(buf.readUIntBE(2, 1).toString(16));
```

**输出:**

```js
<Buffer 21 09 19 98>
190921
210919
1909
919
19
19

```

**例 3:**

```js
// Node program to demonstrate the  
// Buffer.readUIntLE() Method

// Allocating buffer from array
const buf = Buffer.from([0x21, 0x09, 0x19, 0x98]);

// Printing allocated buffer
console.log(buf);

// Reading  data from the buffer
// and printing it as a string
console.log(buf.readUIntLE(0, 4).toString(16));
console.log(buf.readUIntLE(1, 2).toString(16));
console.log(buf.readUIntLE(2, 3).toString(16));

// Wrong index is provoded to produce error
console.log(buf.readUIntLE(3, 6).toString(16));
```

**输出:**

```js
<Buffer 21 09 19 98>
98190921
1909
internal/buffer.js:49
  throw new ERR_OUT_OF_RANGE(type || 'offset',
  ^

RangeError [ERR_OUT_OF_RANGE]: The value of "offset" is out of range. 
It must be >= 0 and <= 1\. Received 2
    at boundsError (internal/buffer.js:49:9)
    at readUInt24LE (internal/buffer.js:118:5)
    at Buffer.readUIntLE (internal/buffer.js:61:12)
    . . .

```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/API/buffer . html # buffer _ buf _ readuitrel _ offset _ byte length](https://nodejs.org/api/buffer.html#buffer_buf_readuintle_offset_bytelength)