# Node.js Buffer.readInt16BE()方法

> 原文:[https://www . geesforgeks . org/node-js-buffer-readint 16 be-method/](https://www.geeksforgeeks.org/node-js-buffer-readint16be-method/)

**Buffer.readInt16BE()方法**是一个内置的类 Buffer 的应用编程接口，带有 in Buffer 模块，以大端格式从指定偏移量的缓冲区中读取一个 16 位有符号整数。

**语法:**

```js
Buffer.readInt16BE( offset )
```

**参数:**该方法接受单个参数**偏移量**，指定开始写入前要跳过的字节数(整数)。偏移值在范围 **0 < =偏移<= buf . length–2**内。它的默认值为零。

**返回值:**返回偏移量和写入的字节数。

**例 1:**

```js
// Node.js program to demonstrate the   
// Buffer.readInt16BE() method  

// Create a buffer 
const buf = Buffer.from([0, 3]);

// Display the result
console.log(buf.readInt16BE(0));
```

**输出:**

```js
3
```

**例 2:**

```js
// Node.js program to demonstrate the   
// Buffer.readInt16BE() method  

// Create a buffer 
const buf = Buffer.from([0, 3]);

// Display the result
console.log(buf.readInt16BE(1));
```

**输出:**

```js
internal/buffer.js:72
  throw new ERR_OUT_OF_RANGE(type || 'offset',
  ^

RangeError [ERR_OUT_OF_RANGE]: The value of "offset" is out of range.
It must be >= 0 and <= 1 0\. received . .< pre>**参考:**[https://nodejs . org/API/buffer . html # buffer _ buf _ readint 16 be _ offset](https://nodejs.org/api/buffer.html#buffer_buf_readint16be_offset)=>
```