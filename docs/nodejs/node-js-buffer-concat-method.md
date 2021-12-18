# Node.js Buffer.concat()方法

> 原文:[https://www.geeksforgeeks.org/node-js-buffer-concat-method/](https://www.geeksforgeeks.org/node-js-buffer-concat-method/)

**Buffer.concat()** 方法用于将给定数组中的所有缓冲区对象连接成一个缓冲区对象。这个方法的返回值也是一个缓冲区。如果未提供缓冲区长度，则根据列表中的缓冲区实例进行计算。

**语法:**

```
Buffer.concat( list, length )
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **列表:**包含要连接的缓冲区列表。
*   **长度:**定义串联缓冲区的长度。此参数是可选的。

**例 1:**

```
// Returns a new buffer with the
// copy of the passed string
var buf1 = Buffer.from("Geeks");

// Returns another buffer with
// copy of the passed string
var buf2 = Buffer.from("for");

var buf3 = Buffer.from("Geeks");

// Creates an array of buffers
var list = [buf1, buf2, buf3];

// Concatenates all buffer objects into one buffer
var newbuff = Buffer.concat(list);

console.log("The concatenated buffer:");

// Displays the concatenated buffer
console.log(newbuff); 
```

**输出:**

```
The concatenated buffer:
<Buffer 47 65 65 6b 73 66 6f 72 47 65 65 6b 73>
```

**例 2:**

```
// Returns a new buffer with the
// copy of the passed string
var buf1 = Buffer.from("Good");

// Returns another buffer with
// copy of the passed string
var buf2 = Buffer.from("morning");

var buf3 = Buffer.from("everyone");

// Creates an array of buffers
var list = [buf1, buf2, buf3];

// Concatenates all buffer objects
// into one buffer
var newbuff = Buffer.concat(list);

console.log("The concatenated buffer:");

// Displays the concatenated buffer
console.log(newbuff); 
```

**输出:**

```
The concatenated buffer:
<Buffer 47 6f 6f 64 6d 6f 72 6e 69 6e 67 65 76 65 72 79 6f 6e 65>

```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**
[https://nodejs . org/dist/latest-v 13 . x/docs/API/buffer . html # buffer _ class _ method _ buffer _ concat _ list _ total ngth](https://nodejs.org/dist/latest-v13.x/docs/api/buffer.html#buffer_class_method_buffer_concat_list_totallength)