# Node.js Buffer.from()方法

> 原文:[https://www.geeksforgeeks.org/node-js-buffer-from-method/](https://www.geeksforgeeks.org/node-js-buffer-from-method/)

**Buffer.from()方法**用于创建包含指定字符串、数组或缓冲区的新缓冲区。

**语法:**

```js
Buffer.from( object, encoding )
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **Object:** This parameter can hold strings, buffers, arrays or array buffers.
*   **Code:** If the object is a string, it is used to specify its code. It is an optional parameter. Its default value is utf8.

**例 1:**

```js
// Node.js program to demonstrate the  
// Buffer.from() Method

// Returns a new buffer with
// copy of the given string
var buf1 = Buffer.from("hello");

// Display the buffer object
// of the given string
console.log(buf1);

// Convert the buffer to the 
// string and displays it
console.log(buf1.toString());
```

**输出:**

```js
<Buffer 68 65 6c 6c 6f>
hello

```

**例 2:**

```js
// Node.js program to demonstrate the  
// Buffer.from() Method

// Creates an arrayBuffer with
// length 10
var arbuff = new ArrayBuffer(8);

// Returns a new buffer with a
// specified memory range within
// the arrayBuffer
var buf = Buffer.from(arbuff, 0, 2);

// Displays the length
console.log(buf.length);
```

**输出:**

```js
2
```

**例 3:**

```js
// Node.js program to demonstrate the  
// Buffer.from() Method

// Create a new buffer with
// copy of the given string
var buf1 = Buffer.from("John");

// Create another buffer with
// copy of given buffer
var buf2 = Buffer.from(buf1);

// Display the buffer object
console.log(buf2);

// Convert the buffer to
// string and displays it
console.log(buf2.toString());
```

**输出:**

```js
<Buffer 4a 6f 68 6e>
John

```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**T2【https://nodejs . org/API/buffer . html # buffer _ class _ method _ buffer _ from _ string _ encoding