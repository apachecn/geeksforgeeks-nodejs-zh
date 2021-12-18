# Node.js Buffer.byteOffset 属性

> 原文:[https://www . geesforgeks . org/node-js-buffer-byteofset-property/](https://www.geeksforgeeks.org/node-js-buffer-byteoffset-property/)

**Buffer.byteOffset** 属性是 **buffer** 模块中类 **Buffer** 的内置应用编程接口，用于获取该缓冲区的字节偏移值。

**语法:**

```
const Buffer.byteOffset
```

**返回值:**该属性返回数组缓冲区的对象。

**示例 1:** **文件名:index . js**

## Javascript

```
// Node.js program to demonstrate the
// Buffer.byteOffset property

// Creating and initializing arraybuffer object
const arrbuff = new ArrayBuffer(16);

// Getting buffer object form existing 
// arraybuffer object
const buffer = Buffer.from(arrbuff);

// Getting byteoffset of buffer
// by using byoffset property
const bytoff = buffer.byteOffset;

// Display the result
console.log("byteoffset is : " + bytoff);
```