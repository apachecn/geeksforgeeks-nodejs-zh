# Node.js fs.symlink()函数

> 原文:[https://www.geeksforgeeks.org/node-js-fs-symlink-function/](https://www.geeksforgeeks.org/node-js-fs-symlink-function/)

**fs.symlink()方法**用于创建到指定路径的 symlink。这将创建一个使`path`指向`target`的链接。相对目标是相对于链接的父目录。

**语法:**

```
fs.symlink( target, path, type, callback )
```

**参数:**这个方法接受上面提到的和下面描述的四个参数:

*   **Target:** It is a string, buffer or URL that indicates the path to which symbolic links must be created.
*   **Path:** It is a string, buffer or web address that represents the path to create symbolic links.
*   **Type:** is a string representing the type of symbolic link to be created. It can be specified with "file", "dir" or "junction". If the target does not exist, File will be used.
*   **Callback:** is a function that will be called when the method is executed.
    *   **err:** If the operation fails, this error will be thrown.

下面的例子说明了 Node.js 中的 **fs.symlink()方法**:

**示例 1:** 本示例创建一个指向文件的符号链接。

```
// Node.js program to demonstrate the
// fs.symlink() method

// Import the filesystem module
const fs = require('fs');

console.log("Contents of the text file:");
console.log(fs.readFileSync('example_file.txt', 'utf8'));

fs.symlink(__dirname + "\\example_file.txt",
        "symlinkToFile", 'file', (err) => {
  if (err)
    console.log(err);
  else {
    console.log("\nSymlink created\n");
    console.log("Contents of the symlink created:");
    console.log(fs.readFileSync('symlinkToFile', 'utf8'));
  }
})
```

**输出:**

```
Contents of the text file:
Hello Geeks

Symlink created

Contents of the symlink created:
Hello Geeks
```

**示例 2:** 本示例创建一个指向目录的符号链接。

```
// Node.js program to demonstrate the
// fs.symlink() method

// Import the filesystem module
const fs = require('fs');

fs.symlink(__dirname + "\\example_directory",
           "symlinkToDir", 'dir', (err) => {
  if (err)
    console.log(err);
  else {
    console.log("Symlink created");
    console.log("Symlink is a directory:",
       fs.statSync("symlinkToDir").isDirectory()
    );
  }
});
```

**输出:**

```
Symlink created
Symlink is a directory: true
```

**参考:**T2【https://nodejs . org/API/fs . html # fs _ fs _ symlink _ target _ path _ type _ callback