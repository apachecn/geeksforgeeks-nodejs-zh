# Node.js Buffer.write()方法

> 原文:[https://www.geeksforgeeks.org/node-js-buffer-write-method/](https://www.geeksforgeeks.org/node-js-buffer-write-method/)

**Buffer.write()** 方法将指定的字符串写入缓冲区的指定位置。如果缓冲区没有包含足够的空间来容纳整个字符串，将只写入字符串的一部分。但是，部分编码的字符不会被写入。

**语法:**

```
buffer.write( string, offset, length, encoding )
```

**参数:**这个方法接受上面提到的和下面描述的四个参数:

*   **String:** It holds the string to be written into the buffer.
*   **Offset:** Save the number of bytes to skip before writing the string. Its default value is 0.
*   **Length:** Save the number of bytes written into the buffer. The default value is buffer.length-offset.
*   **Code:** It stores the code of the value. The default value is utf8.

**返回值:**这个方法返回一个代表写入字节数的数字。

**例 1:**

```
// Node.js program to demonstrate the  
// Buffer.write() method 

// Create a buffer
var buf = Buffer.from('GeeksforGeeks');

buf.write('EE', 1);

console.log(buf.toString());
```

**输出:**

```
GEEksforGeeks
```

**例 2:**

```
// Node.js program to demonstrate the  
// Buffer.write() method 

// Create a buffer
const buf = Buffer.allocUnsafe(100);

const len = buf.write('GeeksforGeeks', 2, 5, 'utf8');

console.log(len.toString());
```

**输出:**

```
5
```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://www . geeksforgeeks . org/node-js-buffer-allocunsafe-method/](https://www.geeksforgeeks.org/node-js-buffer-allocunsafe-method/)