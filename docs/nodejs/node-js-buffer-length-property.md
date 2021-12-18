# Node.js Buffer.length 属性

> 原文:[https://www . geesforgeks . org/node-js-buffer-length-property/](https://www.geeksforgeeks.org/node-js-buffer-length-property/)

**Buffer.length** 属性是缓冲模块中类 **Buffer** 的内置应用编程接口，用于获取该缓冲对象的长度。

**语法:**

```
const Buffer.length
```

**参数:**该属性不接受任何参数。

**返回值:**该属性返回该缓冲区对象的长度。

**示例 1:** **文件名:index.js**

## java 描述语言

```
// Node.js program to demonstrate the
// Buffer.length property

// Creating and initializing arraybuffer object
const arrbuff = new ArrayBuffer(16);

// Getting buffer object form existing
// arraybuffer object
const buffer = Buffer.from(arrbuff);

// Getting byteoffset of buffer
// by using byoffset api
const length = buffer.length;

// Display the result
console.log("Length is : " + length);
```

**输出:**

```
Length is : 16
```

**示例 2:** **文件名:index . js**

## Javascript

```
// Node.js program to demonstrate the
// Buffer.length property

// Creating and initializing arraybuffer object
const arrbuff = new ArrayBuffer(16);

// Getting buffer object form existing
// arraybuffer object
const buffer = Buffer.from(arrbuff);

// Getting byteoffset of buffer
// by using byoffset api
const length = buffer.length;

// Creating and initializing Int8Array object
const buff = new Int8Array(buffer, buffer.byteoffset, length);

// Display the result
console.log("Int8Arry object :- " + buff);
```

**输出:**

```
Int8Arry object :- 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0
```

使用以下命令运行 index.js 文件:

```
node index.js
```

**参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/buffer . html # buffer _ buf _ length](https://nodejs.org/dist/latest-v12.x/docs/api/buffer.html#buffer_buf_length)