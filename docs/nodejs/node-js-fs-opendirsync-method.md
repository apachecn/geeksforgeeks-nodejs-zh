# Node.js fs.opendirSync()方法

> 原文:[https://www . geesforgeks . org/node-js-fs-opendirsync-method/](https://www.geeksforgeeks.org/node-js-fs-opendirsync-method/)

**fs.opendirSync()方法**用于同步打开文件系统中的一个目录。它返回一个 fs。用于表示目录的 Dir 对象。该对象包含可用于访问目录的各种方法。

**语法:**

```js
fs.opendirSync( path[, options] )
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **Path:** It is a string, buffer or web address that indicates the path of the directory that must be opened.
*   **Option:** It is a string or an object that can be used to specify optional parameters that will affect the output. It has two optional parameters:
    *   **Code:** It is a string that specifies the code of the path when opening the directory and the code of the subsequent reading operation. The default value is utf8.
    *   **Buffersize:** It is a number that specifies the number of directory entries buffered internally when reading the directory. A higher value means higher performance, but it will lead to higher memory usage. The default value is 32.

**返回值:**返回一个 fs。Dir 对象，表示目录并包含可用于访问它的各种方法。

下面的例子说明了 Node.js 中的 **fs.opendirSync()方法**:

**例 1:**

```js
// Node.js program to demonstrate the
// fs.opendirSync() method

// Import the filesystem module
const fs = require('fs');

// Open the directory
console.log("Opening the directory");
let openedDir = fs.opendirSync("example_dir");

// Print the pathname of the directory
console.log("\nPath of the directory:", openedDir.path);

// Close the directory
console.log("\nClosing the directory");
openedDir.closeSync();
```

**输出:**

```js
Opening the directory

Path of the directory: example_dir

Closing the directory

```

**例 2:**

```js
// Node.js program to demonstrate the
// fs.opendirSync() method

// Import the filesystem module
const fs = require('fs');

// Function to get current filenames
// in directory
filenames = fs.readdirSync("example_dir");

console.log("\nCurrent filenames in directory:");
filenames.forEach((file) => {
  console.log(file);
});

// Open the directory
openedDir = fs.opendirSync("example_dir");

// Print the pathname of the directory
console.log("\nPath of the directory:", openedDir.path);

// Read the files in the directory
// as fs.Dirent objects
console.log("First Dirent:", openedDir.readSync());
console.log("Next Dirent:", openedDir.readSync());
console.log("Next Dirent:", openedDir.readSync());
```

**输出:**

```js
Current filenames in directory:
example1.txt
example2.txt

Path of the directory: example_dir
First Dirent: Dirent { name: 'example1.txt', [Symbol(type)]: 1 }
Next Dirent: Dirent { name: 'example2.txt', [Symbol(type)]: 1 }
Next Dirent: null

```

**参考:**[https://nodejs . org/API/fs . html # fs _ fs _ openirssync _ path _ options](https://nodejs.org/api/fs.html#fs_fs_opendirsync_path_options)