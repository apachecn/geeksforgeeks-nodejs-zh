# Node.js fs.unlinkSync()方法

> 原文:[https://www.geeksforgeeks.org/node-js-fs-unlinksync-method/](https://www.geeksforgeeks.org/node-js-fs-unlinksync-method/)

**fs.unlinkSync()方法**用于从文件系统中同步删除文件或符号链接。此函数不适用于目录，因此建议使用 fs.rmdir()删除目录。
**语法:**

```
fs.unlinkSync( path )
```

**参数:**该方法接受一个参数，如上所述，如下所述:

*   **路径:**它是一个字符串、缓冲区或网址，代表必须删除的文件或符号链接。

以下示例说明了 Node.js:
**示例 1:** 中的 **fs.unlinkSync()方法**本示例从文件系统中删除一个文件。

## java 描述语言

```
// Node.js program to demonstrate the
// fs.unlinkSync() method

// Import the filesystem module
const fs = require('fs');

// Get the files in current directory
// before deletion
getFilesInDirectory();

// Delete readme.md
fs.unlinkSync("readme.md");
console.log("\nFile readme.md is deleted");

// Get the files in current directory
// after deletion
getFilesInDirectory();

// Function to get current filenames
// in directory with specific extension
function getFilesInDirectory() {
  console.log("\nFiles present in directory:");
  let files = fs.readdirSync(__dirname);
  files.forEach(file => {
    console.log(file);
  });
}
```

**输出:**

```
Files present in directory:
index.html
index.js
package.json
readme.md

File readme.md is deleted

Files present in directory:
index.html
index.js
package.json
```

**示例 2:** 本示例从文件系统中移除符号链接。

## java 描述语言

```
// Node.js program to demonstrate the
// fs.unlinkSync() method

// Import the filesystem module
const fs = require('fs');

// Creating symlink to file
fs.symlinkSync(__dirname + "\\readme.md", "symlinkToReadme");
console.log("\nSymbolic link to readme.md created");

// Function to get current filenames
// in directory with specific extension
getFilesInDirectory();

// Deleting symbolic link to readme.md
fs.unlinkSync("symlinkToReadme");
console.log("\nSymbolic link to readme.md deleted")

getFilesInDirectory();

// Function to get current filenames
// in directory with specific extension
function getFilesInDirectory() {
  console.log("\nFiles present in directory:");
  let files = fs.readdirSync(__dirname);
  files.forEach(file => {
    console.log(file);
  });
}
```

**输出:**

```
Symbolic link to readme.md created

Files present in directory:
index.html
index.js
package.json
readme.md
symlinkToReadme

Symbolic link to readme.md deleted

Files present in directory:
index.html
index.js
package.json
readme.md
```

**参考:**T2】https://nodejs.org/api/fs.html#fs_fs_unlinksync_path