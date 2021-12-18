# Node.js Buffer.indexOf()方法

> 原文:[https://www . geesforgeks . org/node-js-buffer-indexof-method/](https://www.geeksforgeeks.org/node-js-buffer-indexof-method/)

**缓冲区**是一个临时存储器，当数据从一个地方移动到另一个地方时，它存储数据。它就像整数数组。

**Buffer.indexOf()方法**首先检查输入值，如果输入值存在于缓冲区中，则返回值开始的第一个位置(索引)。

**语法:**

```
buffer.indexOf( value, start, encoding )
```

**参数:**这个方法接受三个参数，如上所述，如下所述:

*   **Value:** This parameter holds the value you want to find in the buffer.
*   **start:** is an optional parameter. It refers to the starting index at which the input buffer elements will be searched. The default value is 0.
*   **code:** is an optional parameter. If the required value is a string, you can add an encoding type. The default value is utf-8.

**返回值:**搜索值开始的索引。如果缓冲区中没有该值，则返回 **-1** 。

下面的例子说明了 **Buffer.indexOf()方法**在 Node.js 中的使用:

**例 1:**

```
// Node.js program to demonstrate the  
// Buffer.indexOf() method 

// Creating a buffer
const buffer = Buffer.from(
    'GeeksforGeeks: A computer science portal');

const output = buffer.indexOf('computer');

console.log(output);
```

**输出:**

```
17
```

**例 2:**

```
// Node.js program to demonstrate the  
// Buffer.indexOf() method 

const buffer = Buffer.from('geeks community');

const output = buffer.indexOf(101);

// Print: 1 as 101 is the ASCII value of 'e'
// and 'e' occurs first at index 1
const output1 = buffer.indexOf('geeks community');

// Print: 0 as the whole value starts from 0 index only
const output2 = buffer.indexOf('geeks', 6);

// Print: -1 as we are starting the search from
// 6 index but 'geek' is not present before it
console.log(output);

console.log(output1);

console.log(output2);
```

**输出:**

```
1
0
-1
```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/API/buffer . html # buffer _ buf _ indexof _ value _ byteofset _ encoding](https://nodejs.org/api/buffer.html#buffer_buf_indexof_value_byteoffset_encoding)