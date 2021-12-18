# Node.js Buffer.fill()方法

> 原文:[https://www.geeksforgeeks.org/node-js-buffer-fill-method/](https://www.geeksforgeeks.org/node-js-buffer-fill-method/)

缓冲区是一种临时内存存储，当数据从一个地方移动到另一个地方时，它存储数据。就像整数数组一样。

**Buffer.fill()方法**将数据放入缓冲实例。如果没有给出偏移量和结束值，则整个缓冲区将被填满。

**语法:**

```js
buffer.fill( string, offset, end, encoding )
```

**参数:**这个方法接受上面提到的和下面描述的四个参数:

*   **String:** It holds the data you need to put into the buffer.
*   **Start:** You need to start filling the index of the buffer. Its default value is 0.
*   **End:** The index of the buffer needs to be filled. The default value is buffer.length
*   **Code:** If the data is in string format, it is the code of the data. The default value is utf8.

**返回值:**这个方法返回一个包含值的缓冲区对象。

下面的例子说明了 **Buffer.fill()方法**在 Node.js 中的使用:

**例 1:**

```js
// Node.js program to demonstrate the  
// Buffer.fill() Method

// Allocating the space to buffer instance
var buffer = Buffer.alloc(13);

buffer.fill('GeeksforGeeks');

console.log(buffer.toString());
```

**输出:**

```js
GeeksforGeeks
```

**例 2:**

```js
// Node.js program to demonstrate the  
// Buffer.fill() Method

// Allocating the space to buffer instance
var buffer = Buffer.alloc(7);

buffer.fill('geek', 3);

// Prints : '   geek' as we are starting
// from index 3 to fill the buffer
console.log(buffer.toString());
```

**输出:**

```js
   geek
```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/API/buffer . html # buffer _ buf _ fill _ value _ offset _ end _ encoding](https://nodejs.org/api/buffer.html#buffer_buf_fill_value_offset_end_encoding)