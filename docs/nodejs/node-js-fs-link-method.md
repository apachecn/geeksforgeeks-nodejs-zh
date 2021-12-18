# Node.js fs.link()方法

> 原文:[https://www.geeksforgeeks.org/node-js-fs-link-method/](https://www.geeksforgeeks.org/node-js-fs-link-method/)

**fs.link()方法**用于创建到给定路径的硬链接。创建的硬链接仍然指向同一个文件，即使该文件被重命名。硬链接还包含链接文件的实际内容。

**语法:**

```
fs.link( existingPath, newPath, callback )
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **Existing path:** It is a string, buffer or web address, which indicates the file to which the symbolic link must be created.
*   **New path:** It is a string, buffer or web address, which represents the file path where the symbolic link will be created.
*   **Callback:** is a function that will be called when the method is executed.
    *   **err:** If the method fails, this error will be thrown.

下面的例子说明了 Node.js 中的 **fs.link()方法**:

**示例 1:** 本示例创建到文件的硬链接。

```
// Node.js program to demonstrate the
// fs.link() method

// Import the filesystem module
const fs = require('fs');

console.log("Contents of the text file:");
console.log(fs.readFileSync('example_file.txt', 'utf8'));

fs.link(__dirname + "\\example_file.txt", "hardlinkToFile", (err) => {
  if (err) console.log(err)
  else {
    console.log("\nHard link created\n");
    console.log("Contents of the hard link created:");
    console.log(fs.readFileSync('hardlinkToFile', 'utf8'));
  }
});
```

**输出:**

```
Contents of the text file:
This is an example of the fs.link() method.

Hard link created

Contents of the hard created:
This is an example of the fs.link() method.

```

**示例 2:** 本示例创建文件的硬链接，并删除原始文件。原始文件的内容仍然可以通过硬链接访问。

```
// Node.js program to demonstrate the
// fs.link() method

// Import the filesystem module
const fs = require('fs');

console.log("Contents of the text file:");
console.log(fs.readFileSync('example_file.txt', 'utf8'));

fs.link(__dirname + "\\example_file.txt", "hardlinkToFile", (err) => {
  if (err) console.log(err)
  else {
    console.log("\nHard link created\n");
    console.log("Contents of the hard link created:");
    console.log(fs.readFileSync('hardlinkToFile', 'utf8'));

    console.log("\nDeleting the original file");
    fs.unlinkSync("example_file.txt");

    console.log("\nContents of the hard link created:");
    console.log(fs.readFileSync('hardlinkToFile', 'utf8'));
  }
});
```

**输出:**

```
Contents of the text file:
This is an example of the fs.link() method.

Hard link created

Contents of the hard link created:
This is an example of the fs.link() method.

Deleting the original file

Contents of the hard link created:
This is an example of the fs.link() method.

```

**参考:**T2【https://nodejs . org/API/fs . html # fs _ fs _ link _ existing path _ new path _ callback