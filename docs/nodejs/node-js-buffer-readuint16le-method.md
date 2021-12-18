# Node.js Buffer.readUInt16LE()方法

> 原文:[https://www . geesforgeks . org/node-js-buffer-readuint 16le-method/](https://www.geeksforgeeks.org/node-js-buffer-readuint16le-method/)

**Buffer.readUInt16LE()方法**是 Buffer 模块中类 **Buffer** 的内置应用编程接口，用于以指定的小端格式从指定偏移量的缓冲区中读取无符号 16 位整数。

**语法:**

```
Buffer.readUInt16LE( offset )
```

**参数:**该方法接受单参数**偏移量**，表示开始从缓冲区读取之前要跳过的字节数。偏移量可以在范围 **0 < =偏移量<= buf . length–2**内。偏移量的默认值为 0。

**返回值:**以小端格式从指定偏移量返回一个整数。

下面的例子说明了 **Buffer.readUInt16LE()** 方法在 Node.js 中的使用:

**例 1:**

```
// Node.js program to demonstrate the 
// Buffer.readUInt16LE() method 

// Creating a buffer 
const buf = Buffer.from([0x7, 0x0,
       0x1, 0x1, 0x4, 0x5, 0x4, 0x6]); 

// Using Buffer.readUInt16LE() method
console.log(buf.readUInt16BE(0).toString(16));

// Using Buffer.readUInt16LE() method
console.log(buf.readUInt16BE(6).toString(16));

// Using Buffer.readUInt16LE() method
console.log(buf.readUInt16BE(2).toString(16));
```

**输出:**

```
700
406
101

```

**例 2:**

```
// Node.js program to demonstrate the 
// Buffer.readUInt16LE() method 

// Creating a buffer 
const buf = Buffer.from([0x1714, 0x1024, 0x2113,
       0x2121, 0x1245, 0x1675, 0x1725, 0x1856]); 

// Using Buffer.readUInt16LE() method
console.log(buf.readUInt16BE(0).toString(16));

// Using Buffer.readUInt16LE() method
console.log(buf.readUInt16BE(6).toString(16));

// Using Buffer.readUInt16LE() method
console.log(buf.readUInt16BE(10).toString(16));
```

**输出:**

```
1424
2556
RangeError [ERR_OUT_OF_RANGE]: The value of "offset" is out ofrange. 
It must be >= 0 and <= 6\. Received 10    at boundsError (internal/buffer.js:49:9)
    at Buffer.readUInt16BE (internal/buffer.js:215:5)
    at /home/runner/index.js:14:17
    ......

```

上面的示例显示了错误，因为它的参数不在有效范围内。

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/dist/latest-v 13 . x/docs/API/buffer . html # buffer _ buf _ readuint 16 le _ offset](https://nodejs.org/dist/latest-v13.x/docs/api/buffer.html#buffer_buf_readuint16le_offset)