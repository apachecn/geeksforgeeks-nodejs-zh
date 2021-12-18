# node . js buffer . readfloatile()方法

> 原文:[https://www . geesforgeks . org/node-js-buffer-read float-method/](https://www.geeksforgeeks.org/node-js-buffer-readfloatle-method/)

**buf . ReadFloattle()方法**用于从具有指定字节序格式的缓冲区类中读取 32 位浮点数。它有助于 TCP 流中八位字节流之间的交互、文件系统的操作以及各种其他因素。

**语法:**

```
buffer.readFloatLE( integer )
```

**参数:**该方法接受单个参数**偏移量**，该偏移量保存一个值，该值指示在初始化读取操作之前要跳过多少字节。偏移值介于 **0 到缓冲长度–4**之间。默认值为 0。

**返回值:**返回小端格式的整数值。

下面的例子说明了 buf.readFloatLE()方法在 Node.js 中的使用:

**例 1:**

```
// Node.js program to demonstrate the  
// buffer.readFloatLE() Method

// Creating a buffer of given size 
const buf = Buffer.from([5, 6, 7, 8]); 

// Display the result 
console.log(buf.readFloatLE(0)); 

console.log(buf); 
```

**输出:**

```
4.063216068939723e-34
<Buffer 05 06 07 08>
```

**例 2:**

```
// Node.js program to demonstrate the  
// buffer.readFloatLE() Method

// Creating a buffer of given size 
const buf = Buffer.from([55, 66, 77, 88]); 

// Display the result 
console.log(buf.readFloatLE(0)); 

console.log(buf); 
```

**输出:**

```
internal/buffer.js:72
  throw new ERR_OUT_OF_RANGE(type || 'offset',
  ^

RangeError [ERR_OUT_OF_RANGE]: The value of "offset" is out of range.
 It must be >= 0 and <= 2 0\. received . < pre>**注意:**以上程序使用`node index.js`命令编译运行。**参考:**[https://nodejs . org/API/buffer . html # buffer _ buf _ readfloattle _ offset](https://nodejs.org/api/buffer.html#buffer_buf_readfloatle_offset)=>
```