# Node.js Buffer.toString()方法

> 原文:[https://www . geesforgeks . org/node-js-buffer-tostring-method/](https://www.geeksforgeeks.org/node-js-buffer-tostring-method/)

**Buffer.toString()** 方法用于根据指定的编码类型将缓冲区数据解码为字符串。**开始**和**结束**偏移仅用于解码缓冲器的特定子集。如果根据所提供的编码，缓冲数据中的字节序列无效，则用默认替换字符替换，即 **U+FFFD** 。

**语法:**

```js
Buffer.toString( encoding, start, end )
```

**参数:**该方法接受上面提到的和下面描述的两个参数:

*   **Encoding:** The format in which the buffer data characters must be encoded. The default value is **' UTF8'** .
*   **Start:** The start index of the buffer data that must be encoded. The default value is **0** .
*   **end:** The last index of buffer data must be encoded. The default value is **buffer length.**

**返回值:**根据指定的字符编码将解码后的字符串从缓冲区返回到字符串。

**例 1:**

```js
// Node.js program to demonstrate the   
// Buffer.toString() Method  

// Creating a buffer 
var buffer = new Buffer.alloc(5);

// Loop to add value to the buffer
for (var i = 0; i < 5; i++) {
    buffer[i] = i + 97;
}

// Display the value of buffer
// in string format
console.log(buffer.toString());
console.log(buffer.toString('utf-8', 1, 4));
console.log(buffer.toString('hex'));
```

**输出:**

```js
abcde
bcd
6162636465

```

**说明:**在上面的例子中，我们已经声明了一个大小为 5 的变量缓冲区，并填充了从“a”到“e”的 ASCII 值。接下来，我们使用了不带任何参数的 **toString()** 方法，返回带有默认编码风格的字符串，即完整缓冲区的“UTF-8”。在下一行，它返回从索引 1 到 3 的编码样式为“UTF-8”的字符串(这里不包括 4)。最后，返回编码方式为“HEX”的字符串表示形式。

**例 2:**

```js
// Node.js program to demonstrate the   
// Buffer.toString() Method  

// Creating a buffer 
var buffer = new Buffer.alloc(5);

// Loop to add value to the buffer
for (var i = 0; i < 5; i++) {
    buffer[i] = i + 97;
}

// Display the value of buffer
// in string format
console.log(buffer.toString(undefined));
```

**输出:**

```js
abcde

```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/API/buffer . html # buffer _ buf _ tostring _ encoding _ start _ end](https://nodejs.org/api/buffer.html#buffer_buf_tostring_encoding_start_end)