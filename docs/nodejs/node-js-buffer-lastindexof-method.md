# Node.js Buffer.lastIndexOf()方法

> 原文:[https://www . geesforgeks . org/node-js-buffer-last indexof-method/](https://www.geeksforgeeks.org/node-js-buffer-lastindexof-method/)

缓冲区是一种临时内存存储，当数据从一个地方移动到另一个地方时，它存储数据。它就像一个整数数组。

**Buffer.lastIndexOf()方法**检查缓冲区中的给定值，并返回其存在的索引。如果同一个值出现不止一次，那么它将返回该值出现的最后一个索引。

**语法:**

```
Buffer.lastIndexOf( value, byteOffset, encoding )
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **Value:** specifies the data to be searched in the buffer.
*   **Byte offset:** You need to start searching the index of the buffer. Its default value is 0.
*   **Encoding:** It holds a string value which determines the binary representation of the string searched in the buffer. Its default value is utf8.

**返回值:**这个方法返回一个代表索引值的整数值。

下面的例子说明了在 Node.js 中**buffer . lastindeof()方法**的使用:

**例 1:**

```
// Node program to demonstrate the  
// Buffer.lastIndexOf() Method

var buffer = Buffer.from('GeeksForGeeks');

console.log(buffer.lastIndexOf('G'));
```

**输出**

```
8
```

**例 2:**

```
// Node program to demonstrate the  
// Buffer.lastIndexOf() Method

var buffer = Buffer.from('GeeksForGeeks');

console.log(buffer.lastIndexOf(101));
// Prints : 10
// 101 is the ascii value of 'e'
// e occurs last at index 10

console.log(buffer.lastIndexOf('computer portal'));
//Prints : -1
//as it is not present in the given value
```

**输出:**

```
10
-1

```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/API/buffer . html # buffe _ buf _ last indexof _ value _ byteofset _ encoding](https://nodejs.org/api/buffer.html#buffer_buf_lastindexof_value_byteoffset_encoding)