# Node.js fs.readlinkSync()方法

> 原文:[https://www . geesforgeks . org/node-js-fs-readlinksync-method/](https://www.geeksforgeeks.org/node-js-fs-readlinksync-method/)

**fs.readlinkSync()方法**是 fs 模块的内置应用编程接口，用于同步返回符号链接的值，即链接到的路径。可选参数可用于指定链接路径的字符编码。

**语法:**

```
fs.readlinkSync( path, options )
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **Path:** It is a String, Buffer or URL that represents the path of symbolic link.
*   **Option:** It is an object or string that can be used to specify optional parameters that will affect the output. It has an optional parameter:
    *   **Code:** It is a string value that specifies the character code of the return link path. The default value is utf8.

下面的例子说明了 Node.js 中的 **fs.readlinkSync()方法**:

**例 1:**

```
// Node.js program to demonstrate the
// fs.readlinkSync() method

// Import the filesystem module
const fs = require('fs');

// Create a symbolic link
fs.symlinkSync(__dirname + "\\example_file.txt",
         "symlinkToFile", 'file');

console.log("\nSymlink created\n");

// Get the path of the symbolic link
symlinkPath = fs.readlinkSync("symlinkToFile");
console.log("Path of the symlink:", symlinkPath);
```

**输出:**

```
Symlink created

Path of the symlink: G:\tutorials\nodejs-fs-readlinkSync\example_file.txt
```

**示例 2:** 本示例创建一个指向目录的符号链接。

```
// Node.js program to demonstrate the
// fs.readlinkSync() method

// Import the filesystem module
const fs = require('fs');

// Create a symbolic link
fs.symlinkSync(__dirname + 
    "\\example_directory", "symlinkToDir", 'dir');

console.log("\nSymlink created\n");

// Get the path of the symbolic link
symlinkPath = fs.readlinkSync("symlinkToDir");
console.log("Path of the symlink:", symlinkPath);
```

**输出:**

```
Symlink created

Path of the symlink: G:\tutorials\nodejs-fs-readlinkSync\example_directory
```

**参考:**[https://nodejs . org/API/fs . html # fs _ fs _ readlinksync _ path _ options](https://nodejs.org/api/fs.html#fs_fs_readlinksync_path_options)