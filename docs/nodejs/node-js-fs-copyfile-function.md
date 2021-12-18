# Node.js | fs.copyFile()函数

> 原文:[https://www.geeksforgeeks.org/node-js-fs-copyfile-function/](https://www.geeksforgeeks.org/node-js-fs-copyfile-function/)

**fs.copyFile()方法**用于将文件从源路径异步复制到目标路径。默认情况下，如果文件已经存在于给定的目标位置，Node.js 将覆盖该文件。可选模式参数可用于修改复制操作的行为。

**语法:**

```
fs.copyFile( src, dest, mode, callback )
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **src:** 它是一个字符串、缓冲区或网址，表示要复制的源文件名。
*   **dest:** 它是一个字符串、缓冲区或网址，表示复制操作将创建的目标文件名。
*   **模式:**是指定复制操作行为的整数。这些值可以被赋予具有各自行为的预定义常数:
    *   **fs . constants . copy file _ EXCO:**该常量指定如果目标文件名已经存在，复制操作将失败。
    *   **fs . constants . copyfile _ FICLONE:**该常量指定复制操作将尝试创建写时复制 reflink。如果平台不支持写入时复制，则使用回退机制。
    *   **fs . constants . copyfile _ FICLONE _ FORCE:**该常量指定复制操作将尝试创建一个写时复制 reflink。如果平台不支持写入时复制，操作将会失败，这与上一个不同。

这些常数还可以与按位“或”相结合，创建一个多个值的掩码。这是一个可选参数。参数的默认值为 0。

*   **回调:**这是一个在执行方法时会被调用的函数。
    *   **err:** 这是一个如果方法失败会抛出的错误。

下面的例子说明了 Node.js 中的 **fs.copyFile()方法**:

**例 1:** 本例展示了“example_file.txt”文件到“copy _ file . txt”文件的复制操作。

## java 描述语言

```
// Node.js program to demonstrate the
// fs.copyFile() method

// Import the filesystem module
const fs = require('fs');

// Get the current filenames
// before the function
getCurrentFilenames();
console.log("\nFile Contents of example_file:",
  fs.readFileSync("example_file.txt", "utf8"));

// Copying the file to a the same name
fs.copyFile("example_file.txt", "copied_file.txt", (err) => {
  if (err) {
    console.log("Error Found:", err);
  }
  else {

    // Get the current filenames
    // after the function
    getCurrentFilenames();
    console.log("\nFile Contents of copied_file:",
      fs.readFileSync("copied_file.txt", "utf8"));
  }
});

// Function to get current filenames
// in directory
function getCurrentFilenames() {
  console.log("\nCurrent filenames:");
  fs.readdirSync(__dirname).forEach(file => {
    console.log(file);
  });
}
```

**输出:**

```
Current filenames:
example_file.txt
index.js

File Contents of example_file: This is a test file.

Current filenames:
copied_file.txt
example_file.txt
index.js

File Contents of copied_file: This is a test file.
```

**示例 2:** 该示例显示了当目标已经存在时复制操作的失败。

## java 描述语言

```
// Node.js program to demonstrate the
// fs.copyFile() method

// Import the filesystem module
const fs = require('fs');

// Get the current filenames
// before the function
getCurrentFilenames();
console.log("\nFile Contents of example_file:",
      fs.readFileSync("example_file.txt", "utf8"));

// Copying the file to a the same name
fs.copyFile("example_file.txt", "copied_file.txt",
      fs.constants.COPYFILE_EXCL, (err) => {
  if (err) {
    console.log("Error Found:", err);
  }
  else {

    // Get the current filenames
    // after the function
    getCurrentFilenames();
    console.log("\nFile Contents of copied_file:",
      fs.readFileSync("copied_file.txt", "utf8"));
  }
});

// Function to get current filenames
// in directory
function getCurrentFilenames() {
  console.log("\nCurrent filenames:");
  fs.readdirSync(__dirname).forEach(file => {
    console.log(file);
  });
}
```

**输出:**

```
Current filenames:
copied_file.txt
example_file.txt
index.js

File Contents of example_file: This is a test file.
Error: [Error: EEXIST: file already exists, copyfile 
  'G:\tutorials\nodejs-fs-copyFile\example_file.txt' -> 
  'G:\tutorials\nodejs-fs-copyFile\copied_file.txt'] {
  errno: -4075,
  code: 'EEXIST',
  syscall: 'copyfile',
  path: 'G:\\tutorials\\nodejs-fs-copyFile\\example_file.txt',
  dest: 'G:\\tutorials\\nodejs-fs-copyFile\\copied_file.txt'
}
```

**参考:**[https://nodejs . org/API/fs . html # fs _ fs _ copy file _ src _ dest _ mode _ callback](https://nodejs.org/api/fs.html#fs_fs_copyfile_src_dest_mode_callback)