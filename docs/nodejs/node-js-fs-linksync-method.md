# Node.js fs.linksync()方法

> 原文:[https://www.geeksforgeeks.org/node-js-fs-linksync-method/](https://www.geeksforgeeks.org/node-js-fs-linksync-method/)

**fs.linkSync()方法**用于同步创建到指定路径的硬链接。创建的硬链接仍然指向同一个文件，即使该文件被重命名。硬链接也有链接文件的实际文件内容。

**语法:**

```
fs.linkSync( existingPath, newPath )
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **Existing path:** It is a string, buffer or web address, which indicates the file to which the symbolic link must be created.
*   **New path:** It is a string, buffer or web address, which represents the file path where the symbolic link will be created.

下面的例子说明了 Node.js 中的 **fs.linkSync()方法**:

**示例 1:** 本示例创建到文件的硬链接。

```
// Node.js program to demonstrate the
// fs.linkSync() method

// Import the filesystem module
const fs = require('fs');

console.log("Contents of the text file:");
console.log(fs.readFileSync('example_file.txt', 'utf8'));

fs.linkSync(__dirname + "\\example_file.txt", "hardlinkToFile", 'file');

console.log("\nHard link created\n");
console.log("Contents of the hard link created:");
console.log(fs.readFileSync('hardlinkToFile', 'utf8'));
```

**输出:**

```
Contents of the text file:
Hello GeeksForGeeks

Hard link created

Contents of the hard link created:
Hello GeeksForGeeks
```

**示例 2:** 本示例创建文件的硬链接，并删除原始文件。原始文件的内容仍然可以通过硬链接访问。

```
// Node.js program to demonstrate the
// fs.linkSync() method

// Import the filesystem module
const fs = require('fs');

console.log("Contents of the text file:");
console.log(fs.readFileSync('example_file.txt', 'utf8'));

fs.linkSync(__dirname + "\\example_file.txt", "hardlinkToFile", 'file');

console.log("\nHard link created\n");
console.log("Contents of the hard link created:");
console.log(fs.readFileSync('hardlinkToFile', 'utf8'));

console.log("\nDeleting the original file");
fs.unlinkSync("example_file.txt");

console.log("\nContents of the hard link created:");
console.log(fs.readFileSync('hardlinkToFile', 'utf8'));
```

**输出:**

```
Contents of the text file:
Hello GeeksForGeeks

Hard link created

Contents of the hard link created:
Hello GeeksForGeeks

Deleting the original file

Contents of the hard link created:
Hello GeeksForGeeks
```

**参考:**[https://nodejs . org/API/fs . html # fs _ fs _ linksync _ existing path _ new path](https://nodejs.org/api/fs.html#fs_fs_linksync_existingpath_newpath)