# Node.js Buffer.subarray()方法

> 原文:[https://www . geesforgeks . org/node-js-buffer-subarray-method/](https://www.geeksforgeeks.org/node-js-buffer-subarray-method/)

**buffer.subarray()方法**是缓冲模块的内置应用编程接口，用于裁剪数组的一部分，即从数组创建子数组。

**语法:**

```js
Buffer.subarray( starting_index, ending_index )
```

**参数:**该方法有两个参数，如上所述，如下所述:

*   **starting _ index:** This parameter specifies an integer value, indicating the starting address of the new buffer. Its default value is 0.
*   [T0】 end _ index: 【T1] It specifies an integer value indicating the end address of the buffer where a new buffer is to be created. The default value is the length of the buffer.

**返回值:**该方法返回裁剪后的数组。该缓冲区指向相同的内存，但带有裁剪的开始和结束索引。如果参数中的 end _ index 大于缓冲区长度，则将缓冲区长度作为结束索引。

**注意:**如果新缓冲区被修改，那么当它们指向相同的内存时，相同的内容将反映在原始缓冲区中。

下面的例子说明了 **buffer.subarray()方法**在 Node.js 中的使用:

**例 1:**

```js
// Node.js program to demonstrate the   
// Buffer.subarray() method

// Allocating buffer 
const buf = Buffer.from('GeeksforGeeks', 'ascii');

// Printing original buffer
console.log("Original buffer is: " + buf);

// Cropping buffer, here starting index
// is 5 and ending endex is 10
cropped_buf = buf.subarray(5, 10);

// Printing cropped buffer
console.log("Cropped buffer is: " + cropped_buf);

// Modifying cropped buffer
cropped_buf[0] = 70;  // F
cropped_buf[1] = 79;  // O
cropped_buf[2] = 82;  // R

// Printing cropped buffer
console.log("Cropped buffer after modification is: " + cropped_buf);

// Printing original buffer
console.log("Original buffer after modification is: " + buf);
```

**输出:**

```js
Original buffer is: GeeksforGeeks
Cropped buffer is: forGe
Cropped buffer after modification is: FORGe
Original buffer after modification is: GeeksFORGeeks

```

**例 2:**

```js
// Node.js program to demonstrate the   
// Buffer.subarray() method

// Allocating buffer 
const buf = Buffer.from('GeeksforGeeks', 'ascii');

// Printing original buffer
console.log("Original buffer is: " + buf);

// Cropping buffer, here starting index
// is -10 and ending endex is -1
cropped_buf = buf.subarray(-12, -1);

// Printing cropped buffer
console.log("Cropped buffer is:" + cropped_buf);

// Cropping buffer again, here starting
// index is -10 and ending endex is -5
cropped_buf = buf.subarray(-10, -5);

// Printing cropped buffer
console.log("Cropped buffer is: " + cropped_buf);

// Cropping buffer again with no parameter
cropped_buf = buf.subarray();

// Printing cropped buffer
console.log("Cropped buffer is: " + cropped_buf);
```

**输出:**

```js
Original buffer is: GeeksforGeeks
Cropped buffer is:eeksforGeek
Cropped buffer is: ksfor
Cropped buffer is: GeeksforGeeks

```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/API/buffer . html # buffer _ buf _ subarray _ start _ end](https://nodejs.org/api/buffer.html#buffer_buf_subarray_start_end)