# Node.js Buffer.includes()方法

> 原文:[https://www . geesforgeks . org/node-js-buffer-includes-method/](https://www.geeksforgeeks.org/node-js-buffer-includes-method/)

**缓冲区**是一个临时存储器，当数据从一个地方移动到另一个地方时，它存储数据。它就像一个整数数组。

**Buffer.includes()方法**检查所提供的值是否存在或包含在缓冲区中。

**语法:**

```js
buffer.includes( value, byteOffset, encoding );
```

**参数:**这个方法接受下面列出的三个参数:

*   **Value:** It holds the value you want to find in the buffer.
*   **ByteOffset:** is an optional parameter. It refers to the starting index at which the input buffer elements will be searched. The default value is 0.
*   **Code:** If the required value is a character string, then the code type can also be added. The default value is utf-8.

**返回值:**该方法根据值返回布尔值“真”或“假”。如果在缓冲区中找到值，则返回真，否则返回假。

下面的例子说明了 **Buffer.includes()方法**在 Node.js 中的使用:

**例 1:**

```js
// Node.js program to demonstrate the  
// Buffer.includes() Method 

// Creating a buffer
const buffer = new Buffer('Geek One');

console.log(buffer.includes('Geek'));
```

**输出:**

```js
true
```

**例 2:**

```js
// Node program to demonstrate the  
// Buffer.includes() Method 

const buffer = Buffer.from(
        'GeeksforGeeks: A computer science portal');

// Started checking the value from index 15 only
const output = buffer.includes('Geek', 15);

console.log(output);
```

**输出:**

```js
false
```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/API/buffer . html # buffer _ buf _ includes _ value _ byteofset _ encoding](https://nodejs.org/api/buffer.html#buffer_buf_includes_value_byteoffset_encoding)