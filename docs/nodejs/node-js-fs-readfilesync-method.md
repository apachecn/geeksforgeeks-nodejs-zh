# Node.js fs.readFileSync()方法

> 原文:[https://www . geesforgeks . org/node-js-fs-readfilesync-method/](https://www.geeksforgeeks.org/node-js-fs-readfilesync-method/)

**fs.readFileSync()方法**是 fs 模块的内置应用编程接口，用于读取文件并返回其内容。
在 fs.readFile()方法中，我们可以以非阻塞异步方式读取文件，但是在 fs.readFileSync()方法中，我们可以以同步方式读取文件，即我们告诉 node.js 阻塞其他并行进程，并执行当前的文件读取进程。也就是说，当 fs.readFileSync()方法被调用时，原始节点程序停止执行，节点等待 fs.readFileSync()函数被执行，在获得该方法的结果后，剩余的节点程序被执行。

**语法:**

```js
fs.readFileSync( path, options )
```

**参数:**

*   **路径:**取文本文件的相对路径。路径可以是网址类型。该文件也可以是文件描述符。如果两个文件在同一个文件夹中，只需用引号将文件名括起来。
*   **选项:**是包含编码和标志的可选参数，编码包含数据规范。它的默认值是*空值*，返回原始缓冲区，标志包含文件中操作的指示。它的默认值是“r”。

**返回值:**此方法返回文件的内容。
T3】例 1:

*   **input.txt 文件内容:**

```js
This is some text data which is stored in input.txt file.
```

*   **index.js 文件:**

## java 描述语言

```js
// Node.js program to demonstrate the 
// fs.readFileSync() method

// Include fs module
const fs = require('fs');

// Calling the readFileSync() method
// to read 'input.txt' file
const data = fs.readFileSync('./input.txt',
            {encoding:'utf8', flag:'r'});

// Display the file data
console.log(data);
```