# Node.js Buffer.slice()方法

> 原文:[https://www.geeksforgeeks.org/node-js-buffer-slice-method/](https://www.geeksforgeeks.org/node-js-buffer-slice-method/)

**Buffer** 是一个临时内存存储，当数据从一个地方移动到另一个地方时，它存储数据，就像整数数组一样。

**Buffer.slice()方法**返回一个新的 Buffer，该 Buffer 指向与输入 Buffer 相同的存储位置，只有裁剪的元素。

**语法:**

```
buffer.slice( start, end )
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **Start:** refers to the starting index of the input buffer elements to be copied to the output buffer.
*   **end:** refers to the ending index before the elements of the input buffer are copied to the output buffer. (When slicing the buffer, the ending index is not included in the count)

**返回值:**返回包含改变的缓冲区的缓冲区。

**注意:**起始索引和结束索引的默认值分别为 0 和 buffer.length。负索引从数组的末尾开始。

下面的例子说明了**缓冲.切片()方法**在 Node.js 中的使用:

**例 1:**

```
// Node program to demonstrate the  
// Buffer.slice() method 

// Creating a buffer
var buffer1 = new Buffer('GeeksForGeeks');

// Slicing a buffer
var output = buffer1.slice(8, 12);

// Converting the output buffer to string
console.log("Sliced Buffer is: " + output.toString());
```

**输出:**

```
Sliced Buffer is: Geek
```

**例 2:**

```
// Node program to demonstrate the  
// Buffer.slice() method 

const buffer = Buffer.from('Geek One');

const opBuffer = buffer.slice(0, 4) + " Two";

// Prints: Geek One
console.log(buffer.toString());

// Prints: Geek Two
console.log(opBuffer.toString());
```

**输出:**

```
Geek One
Geek Two
```

**注意:**以上程序使用`node fileName.js`命令编译运行。

**参考:**[https://nodejs . org/API/buffer . html # buffer _ buf _ slice _ start _ end](https://nodejs.org/api/buffer.html#buffer_buf_slice_start_end)