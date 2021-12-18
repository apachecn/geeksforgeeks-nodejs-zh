# Node.js fs.unlink()方法

> 原文:[https://www.geeksforgeeks.org/node-js-fs-unlink-method/](https://www.geeksforgeeks.org/node-js-fs-unlink-method/)

**fs.unlink()方法**用于从文件系统中移除文件或符号链接。此函数不适用于目录，因此建议使用 fs.rmdir()删除目录。
**语法:**

```
fs.unlink( path, callback )
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **路径:**它是一个字符串、缓冲区或网址，代表必须删除的文件或符号链接。
*   **回调:**这是一个在执行方法时会被调用的函数。
*   **err:** 这是一个如果方法失败会抛出的错误。

以下示例说明了 Node.js:
**示例 1:** 中的 **fs.unlink()方法**本示例从文件系统中删除一个文件。

## java 描述语言

```
// Node.js program to demonstrate the
// fs.unlink() method

// Import the filesystem module
const fs = require('fs');

// Get the files in current directory
// before deletion
getFilesInDirectory();

// Delete example_file.txt
fs.unlink("example_file.txt", (err => {
  if (err) console.log(err);
  else {
    console.log("\nDeleted file: example_file.txt");

    // Get the files in current directory
    // after deletion
    getFilesInDirectory();
  }
}));

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
example_file.txt
index.js
package.json

Deleted file: example_file.txt

Files present in directory:
index.js
package.json
```

**示例 2:** 本示例从文件系统中移除符号链接。

## java 描述语言

```
// Node.js program to demonstrate the
// fs.unlink() method

// Import the filesystem module
const fs = require('fs');

// Creating symlink to file
fs.symlinkSync(__dirname + "\\example_file.txt", "symlinkToFile");
console.log("\nSymbolic link to example_file.txt created");

// Function to get current filenames
// in directory with specific extension
getFilesInDirectory();

// Deleting symbolic link to example_file.txt
// Delete example_file.txt
fs.unlink("symlinkToFile", (err => {
  if (err) console.log(err);
  else {
    console.log("\nDeleted Symbolic Link: symlinkToFile");

    // Get the files in current directory
    // after deletion
    getFilesInDirectory();
  }
}));

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
Symbolic link to example_file.txt created

Files present in directory:
example_file.txt
index.js
package.json
symlinkToFile

Deleted Symbolic Link: symlinkToFile

Files present in directory:
example_file.txt
index.js
package.json
```

**参考:**T2】https://nodejs.org/api/fs.html#fs_fs_unlink_path_callback