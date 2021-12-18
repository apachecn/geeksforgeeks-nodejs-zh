# Node.js fs.rename()方法

> 原文:[https://www.geeksforgeeks.org/node-js-fs-rename-method/](https://www.geeksforgeeks.org/node-js-fs-rename-method/)

**fs.rename()方法**用于将给定旧路径的文件异步重命名为给定新路径。如果目标文件已经存在，它将覆盖该文件。

**语法:**

```
fs.rename( oldPath, newPath, callback )
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **[Old path]:** Save the file path to be renamed. It can be a string, a buffer or a web address.
*   **New Path:** A new path that needs to be renamed to save the file. It can be a string, a buffer or a web address.
*   **Callback:** is a function that will be called when the method is executed. It has an optional parameter to display any errors that occur during the process.

下面的例子说明了 Node.js 中的 **fs.rename()方法**:

**示例 1:** 本示例使用 fs.rename()方法重命名文件。

```
// Node.js program to demonstrate the    
// fs.rename() method 

// Import filesystem module
const fs = require('fs');

// List all the filenames before renaming
getCurrentFilenames();

// Rename the file
fs.rename('hello.txt', 'world.txt', () => {
  console.log("\nFile Renamed!\n");

  // List all the filenames after renaming
  getCurrentFilenames();
});

// Function to get current filenames
// in directory
function getCurrentFilenames() {
  console.log("Current filenames:");
  fs.readdirSync(__dirname).forEach(file => {
    console.log(file);
  });
}
```

**输出:**

```
Current filenames:
hello.txt
index.js

File Renamed!

Current filenames:
index.js
world.txt
```

**示例 2:** 本示例使用 fs.rename()方法演示文件重命名过程中的一个错误。

```
// Node.js program to demonstrate the    
// fs.rename() method 

// Import filesystem module
const fs = require('fs');

// List all the filenames before renaming
getCurrentFilenames();

// Rename the file
fs.rename('hello.txt', 'geeks.txt', (error) => {
  if (error) {

    // Show the error 
    console.log(error);
  }
  else {

    // List all the filenames after renaming
    console.log("\nFile Renamed\n");

    // List all the filenames after renaming
    getCurrentFilenames();
  }
});

// Function to get current filenames
// in directory
function getCurrentFilenames() {
  console.log("Current filenames:");
  fs.readdirSync(__dirname).forEach(file => {
    console.log(file);
  });
}
```

**输出:**

```
Current filenames:
index.js
package.json
world.txt
[Error: ENOENT: no such file or directory, rename 
'G:\tutorials\nodejs-fs-rename\hello.txt' ->
'G:\tutorials\nodejs-fs-rename\geeks.txt'] {
  errno: -4058,
  code: 'ENOENT',
  syscall: 'rename',
  path: 'G:\\tutorials\\nodejs-fs-rename\\hello.txt',
  dest: 'G:\\tutorials\\nodejs-fs-rename\\geeks.txt'
}
```

**参考:**T2【https://nodejs . org/API/fs . html # fs _ fs _ rename _ old path _ new path _ callback