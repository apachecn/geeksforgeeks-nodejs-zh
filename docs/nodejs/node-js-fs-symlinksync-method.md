# Node.js fs.symlinkSync()方法

> 原文:[https://www . geesforgeks . org/node-js-fs-symlinksync-method/](https://www.geeksforgeeks.org/node-js-fs-symlinksync-method/)

**fs.symlinkSync()方法**用于同步创建到指定路径的 symlink。该方法创建一个链接，使`path`指向`target`。相对目标是相对于链接的父目录。

**语法:**

```js
fs.symlinkSync( target, path, type )
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **Target:** It is a string, buffer or web address, which represents the path where symbolic links must be created.
*   **Path:** It is a string, buffer or web address that represents the path to create symbolic links.
*   **Type:** is a string representing the type of symbolic link to be created. It can be specified with "file", "dir" or "junction". If the target does not exist, File will be used.

下面的例子说明了 Node.js 中的 **fs.symlinkSync()方法**:

**示例 1:** 本示例创建一个指向文件的符号链接。

```js
// Node.js program to demonstrate the
// fs.symlinkSync() method

// Import the filesystem module
const fs = require('fs');

console.log("Contents of the text file:");
console.log(
  fs.readFileSync('example_file.txt', 'utf8')
);

fs.symlinkSync(__dirname + "\\example_file.txt",
               "symlinkToFile", 'file');

console.log("\nSymlink created\n");
console.log("Contents of the symlink created:");
console.log(
  fs.readFileSync('symlinkToFile', 'utf8')
);
```

**输出:**

```js
Contents of the text file:
Hello Geeks

Symlink created

Contents of the symlink created:
Hello Geeks
```

**示例 2:** 本示例创建一个指向目录的符号链接。

```js
// Node.js program to demonstrate the
// fs.symlinkSync() method

// Import the filesystem module
const fs = require('fs');

fs.symlinkSync(__dirname + "\\example_directory",
               "symlinkToDir", 'dir');

console.log("Symlink created");
console.log("Symlink is a directory:", 
  fs.statSync("symlinkToDir").isDirectory()
);
```

**输出:**

```js
Symlink created
Symlink is a directory: true
```

**参考:**[https://nodejs . org/API/fs . html # fs _ fs _ symlinksync _ target _ path _ type](https://nodejs.org/api/fs.html#fs_fs_symlinksync_target_path_type)