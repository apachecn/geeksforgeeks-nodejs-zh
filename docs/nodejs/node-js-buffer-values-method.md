# Node.js Buffer.values()方法

> 原文:[https://www.geeksforgeeks.org/node-js-buffer-values-method/](https://www.geeksforgeeks.org/node-js-buffer-values-method/)

缓冲区是一种临时内存存储，当数据从一个地方移动到另一个地方时，它存储数据。它就像一个整数数组。

**Buffer.values()方法**用于创建一个循环或迭代对象，该对象包含缓冲实例的每个字节的值。当在 for…语句中使用缓冲区时，会自动调用此方法。

**语法:**

```
Buffer.values()
```

**返回值:**它返回一个遍历缓冲区每个字节的迭代器。

下面的例子说明了 **Buffer.values()** 方法在 Node.js 中的使用:

**例 1:**

```
// Node.js program to demonstrate the  
// Buffer.values() Method
const buffer = Buffer.from('geek');

// Display the buffer ASCII character
for (const value of buffer.values()) {
      console.log(value);
}
```

**输出:**

```
103
101
101
107
```

**例 2:**

```
// Node.js program to demonstrate the  
// Buffer.values() Method
const buffer = Buffer.from('geek');

// Display the ASCII values
for (const value of buffer.values()) {
  console.log(value);
}
// Prints:
// 103
// 101
// 101
// 107

const buffer2 = Buffer.from('GEEK');

// Display the ASCII values
for (const value of buffer2.values()) {
  console.log(value);
} 
// Prints:
// 71
// 69
// 69
// 75

var op = Buffer.compare(buffer, buffer2);
console.log(op); 
// Prints: 1 
// As buffer is higher than buffer2 i.e if
// Buffer should come before buffer2 when sorted.
```

**输出:**

```
103
101
101
107
71
69
69
75
1

```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**T2】https://nodejs.org/api/buffer.html#buffer_buf_values