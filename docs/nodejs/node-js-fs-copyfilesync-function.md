# Node.js fs.copyFileSync()函数

> 原文:[https://www . geesforgeks . org/node-js-fs-copy filesync-function/](https://www.geeksforgeeks.org/node-js-fs-copyfilesync-function/)

**fs.copyFileSync()方法**用于将文件从源路径同步复制到目标路径。如果文件已经存在于目标中，Node.js 将覆盖该文件。可选模式参数可用于指定复制操作的行为。

**语法:**

```js
fs.copyFileSync(src, dest, mode)
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **src:** 它是一个字符串、缓冲区或网址，表示要复制的源文件名。
*   **dest:** 它是一个字符串、缓冲区或网址，表示复制操作将创建的目标文件名。
*   **模式:**是指定复制操作行为的整数。这些值可以被赋予具有各自行为的预定义常数:
    *   **fs . constants . copy file _ EXCO:**该常量指定如果目标文件名已经存在，复制操作将失败。
    *   **fs . constants . copyfile _ FICLONE:**该常量指定复制操作将尝试创建写时复制 reflink。如果平台不支持写入时复制，则使用回退机制。
    *   **fs . constants . copyfile _ FICLONE _ FORCE:**该常量指定复制操作将尝试创建一个写时复制 reflink。如果平台不支持写入时复制，操作将会失败，这与上一个不同。

以下示例说明了 Node.js:
**示例 1:** 中的 **fs.copyFileSync()方法**本示例显示了将“hello.txt”文件复制到“world.txt”文件的操作。

## java 描述语言

```js

// Node.js program to demonstrate the
// fs.copyFileSync() method

// Import the filesystem module
const fs = require('fs');

// Get the current filenames
// before the function
getCurrentFilenames();
console.log("\nFile Contents of hello.txt:",
      fs.readFileSync("hello.txt", "utf8"));

fs.copyFileSync("hello.txt", "world.txt");

// Get the current filenames
// after the function
getCurrentFilenames();
console.log("\nFile Contents of world.txt:",
      fs.readFileSync("world.txt", "utf8"));

// Function to get current filenames
// in directory
function getCurrentFilenames() {
  console.log("\nCurrent files in directory:");
  fs.readdirSync(__dirname).forEach(file => {
    console.log(file);
  });
}
```