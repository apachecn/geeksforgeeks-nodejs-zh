# Node.js Buffer.kMaxLength 属性

> 原文:[https://www . geesforgeks . org/node-js-buffer-kmaxlength-property/](https://www.geeksforgeeks.org/node-js-buffer-kmaxlength-property/)

**Buffer.kMaxLength** 属性是缓冲模块内类 **Buffer** 的内置应用编程接口，用于设置和获取单个缓冲实例允许的最大长度。

**语法:**

```
const Buffer.kMaxLength
```

**参数:**这个属性作为一个 getter 和 setter 工作，所以它有时会将整数值作为一个参数。

**返回值:**该属性返回单个缓冲实例允许的最大长度。

**示例 1:** **文件名:index.js**

## java 描述语言

```
// Node.js program to demonstrate the
// Buffer.kMaxLength property

// Creating and initializing arraybuffer object
const arrbuff = new ArrayBuffer(16);

// Getting buffer object form existing
// arraybuffer object
const buffer = Buffer.from(arrbuff);

// Setting the the maximum value
// into the buffer
buffer.kMaxLength = 23;

// Getting the maximum length by using
// kMaxLength property
const value = buffer.kMaxLength;

// Display the result
console.log("kMaxLength is: " + value);
```

**输出:**

```
kMaxLength is: 23
```

**示例 2:** **文件名:index.js**

**如果 kMaxLength 未初始化**

## Javascript

```
// Node.js program to demonstrate the
// Buffer.kMaxLength property

// If kMaxLengthis is not initialized

// Creating and initializing arraybuffer
// object
const arrbuff = new ArrayBuffer(16);

// Getting buffer object form existing
// arraybuffer object
const buffer = Buffer.from(arrbuff);

// Getting the maximum length by using
// kMaxLength property
const value = buffer.kMaxLength;

// Display the result
console.log("kMaxLength is: " + value);
```

**输出:**

```
kMaxLength is: undefined
```

使用以下命令运行 index.js 文件:

```
node index.js
```

**参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/buffer . html # buffer _ buffer _ kmaxlength](https://nodejs.org/dist/latest-v12.x/docs/api/buffer.html#buffer_buffer_kmaxlength)