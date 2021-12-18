# Node.js Buffer.alloc()方法

> 原文:[https://www.geeksforgeeks.org/node-js-buffer-alloc-method/](https://www.geeksforgeeks.org/node-js-buffer-alloc-method/)

**Buffer.alloc()方法**用于创建指定大小的新缓冲区对象。此方法比**Buffer . alloconsafe()方法**慢，但它确保新创建的 Buffer 实例永远不会包含可能敏感的旧信息或数据。

**语法**

```js
Buffer.alloc(size, fill, encoding)
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **大小:**指定缓冲区的大小。
*   **填充:**为可选参数，指定填充缓冲区的值。其默认值为 0。
*   **编码:**如果缓冲区值是字符串，它是指定值的可选参数。其默认值为**‘utf8’**。

**返回值:**这个方法返回一个新的指定大小的初始化缓冲区。如果给定的大小不是数字，将引发类型错误。

**例 1:**

```js
// Node.js program to demonstrate the   
// Buffer.alloc() Method

// Allocate buffer of given size
// using buffer.alloc() method
var buf = Buffer.alloc(6);

// Prints: <Buffer 00 00 00 00 00 00>
console.log(buf);
```

**输出:**

```js
<Buffer 00 00 00 00 00 00>
```

**例 2:**

```js
// Node.js program to demonstrate the   
// Buffer.alloc() Method

// Allocate buffer of given size
// using buffer.alloc() method
var buf = Buffer.alloc(6, 'a');

// Prints <Buffer 61 61 61 61 61>
console.log(buf);
```

**输出:**T2<缓冲区 61 61 61 61 61 >

**参考:**
[https://nodejs . org/docs/latest-v 11 . x/API/buffer . html # buffer _ class _ method _ buffer _ alloc _ size _ fill _ encoding](https://nodejs.org/docs/latest-v11.x/api/buffer.html#buffer_class_method_buffer_alloc_size_fill_encoding)