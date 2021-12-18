# Node.js Buffer.compare()方法

> 原文:[https://www . geesforgeks . org/node-js-buffer-compare-method/](https://www.geeksforgeeks.org/node-js-buffer-compare-method/)

**缓冲区**是一个临时存储器，当数据从一个地方移动到另一个地方时，它存储数据。它就像一个整数数组。 **Buffer.compare()** 方法比较两个给定的缓冲液。

**语法:**

```js
buffer1.compare( targetBuffer, targetStart,
            targetEnd, sourceStart, sourceEnd )
```

**参数:**该方法接受 5 个参数，如上所述，如下所述:

*   **[Target buffer:** This parameter stores the buffer to be compared with other buffers.
*   **Targetstart:** refers to the starting index at which the elements of the target buffer begin to compare. Its default value is 0.
*   **Targetend:** refers to the index to which the elements of the target buffer will be compared. The default value is 0.
*   **Source start:** Enter the index of the comparison value in the buffer. The default value is 0.
*   **Source:** Enter the index in the buffer, before which the values will be compared. The default value is

**返回值:**返回一个数字，表示两个缓冲区的差异。退货编号为:

*   0: If equal.
*   1: if buffer1 is higher than buffer2, that is, whether buffer1 should be before buffer2 when sorting.
*   -1: if buffer2 is higher than buffer1, that is, whether buffer2 should be before buffer1 when sorting.

以下示例说明了 Node.js 中的 **Buffer.compare()方法**:

**例 1:**

```js
// Node.js program to demonstrate the  
// Buffer.compare() Method

// Creating a buffer
var buffer1 = Buffer.from('Geek');
var buffer2 = Buffer.from('Geek');
var op = Buffer.compare(buffer1, buffer2);
console.log(op);

var buffer1 = Buffer.from('GFG');
var buffer2 = Buffer.from('Python');
var op = Buffer.compare(buffer1, buffer2);
console.log(op);
```

**输出:**

```js
0
-1
```

**例 2:**

```js
// Node.js program to demonstrate the  
// Buffer.compare() Method

// Creating a buffer
var buffer1 = Buffer.from('2');
var buffer2 = Buffer.from('1');
var buffer3 = Buffer.from('3');
var array = [buffer1, buffer2, buffer3];

// Before sorting
console.log(array);

// After sorting array
console.log(array.sort(Buffer.compare));
```

**输出:**

```js
[ <Buffer 32>, <Buffer 31>, <Buffer 33> ]
[ <Buffer 31>, <Buffer 32>, <Buffer 33> ]
```

**例 3:**

```js
// Node.js program to demonstrate the  
// Buffer.compare() Method

var buffer1 = Buffer.from('GeeksOne');
var buffer2 = Buffer.from('GeekTwo');

// Print: -1 as size of buffer1 starting 
// from index 4 is less than buffer2 size
var op = buffer1.compare(buffer2, 4);

// Print: 1 as the size of buffer2 starting 
// from index 5 is less than size of buffer1
// starting from 0th index
var op1 = buffer1.compare(buffer2, 0, 7, 5);

console.log(op);
console.log(op1);
```

**输出:**

```js
-1
1
```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/API/buffer . html # buffe _ buf _ compare _ target start _ target end _ source start _ source end](https://nodejs.org/api/buffer.html#buffer_buf_compare_target_targetstart_targetend_sourcestart_sourceend)