# Node.js Buffer.copy()方法

> 原文:[https://www.geeksforgeeks.org/node-js-buffer-copy-method/](https://www.geeksforgeeks.org/node-js-buffer-copy-method/)

**缓冲区**是一个临时存储器，当数据从一个地方移动到另一个地方时，它存储数据。它就像一个整数数组。

**Buffer.copy()方法**只需将所有值从输入缓冲区复制到另一个缓冲区。

**语法:**

```
buffer.copy( target, targetStart, sourceStart, sourceEnd )
```

**参数:**这个方法接受两个参数，如上所述，如下所述:

*   **Target:** It is a buffer where all values need to be copied.
*   **Targetstart:** refers to the starting index at which the elements of the target buffer start writing. Its default value is 0.
*   **Source start:** is the index of the input buffer from which the value is copied. Its default value is 0.
*   **sourceend:** The index of the input buffer where the value copy will be completed. Its default value is buffer.lengthsize.

**返回值:**该方法返回指示复制字节数的数字。

**注意:**从输入缓冲区复制值，并将其覆盖到输出缓冲区，即使目标内存区域(索引)已经存在。即使目标内存区域与输入缓冲区重叠，也将数据从输入缓冲区的一个区域复制到目标缓冲区的一个区域。

下面的例子说明了 **Buffer.includes()方法**在 Node.js 中的使用:

**例 1:**

```
// Node.js program to demonstrate the  
// Buffer.copy() Method 

// Creating a buffer
var buffer2 = Buffer.from('for');

var buffer1 = Buffer.from('GeeksandGeeks');

buffer2.copy(buffer1, 5, 0);

console.log(buffer1.toString());
```

**输出:**

```
GeeksforGeeks
```

**例 2:**

```
// Node.js program to demonstrate the  
// Buffer.copy() Method

var buffer2 = Buffer.allocUnsafe(5);

var buffer1 = Buffer.from('Geeks');

for (let i = 0; i < 5; i++) {

    // Adds: 'a b c d e' as 97 98 99 100 101
    // are their respective ASCII values
    buffer2[i] = i + 97;
}

buffer2.copy(buffer1, 2);

// Prints 'Geabc' as the input buffer1
// carries 'Geeks' and we provided the
// targetStart index as 2
// so elements will replace the values in
// buffer1 starting from index 2

console.log(buffer1.toString());
```

**输出:**

```
Geabc
```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**T2【https://nodejs . org/API/buffer . html # buffer _ buf _ copy _ target start _ source start _ source end