# 如何使用 Node.js 显示一个目录下的所有文件？

> 原文:[https://www . geesforgeks . org/如何使用节点 js 显示目录中的所有文件/](https://www.geeksforgeeks.org/how-to-display-all-files-in-a-directory-using-node-js/)

目录中的文件可以使用 Node.js 中的两种方法来显示，这两种方法将在下面讨论:

**方法 1:使用 [fs.readdirSync()方法](https://www.geeksforgeeks.org/node-js-fs-readdirsync-method/) :** 方法`fs.readdirSync()`是 Node.js 的文件系统模块中提供的一种方法，用于读取目录的内容。它返回文件路径、缓冲区或文件系统的数组。直接物体。

可以使用 forEach()循环来循环返回的文件数组，并从中显示文件名。这样可以显示目录中的所有文件名。

方法`[fs.readdir()](https://www.geeksforgeeks.org/node-js-fs-readdir-method/)`的异步变体也可以用来代替这个用文件而不是文件本身返回回调的函数。

**示例:**

```
// Import the filesystem module
const fs = require("fs");

let directory_name = "example_dir";

// Function to get current filenames
// in directory
let filenames = fs.readdirSync(directory_name);

console.log("\nFilenames in directory:");
filenames.forEach((file) => {
    console.log("File:", file);
});
```

**输出:**

```
Filenames in directory:
File: file_a.txt
File: file_b.txt
File: file_c.txt

```

**方法二:使用 fs.opendirSync()方法:**node . js 的文件系统模块中有`fs.opendirSync()`方法，可以用来读取目录的内容。它返回一个代表给定目录的`fs.Dir`对象。

使用`readSync()`方法，可以使用`fs.Dir`对象访问该目录中的文件。该方法返回一个`fs.Dirent`对象，该对象包含目录条目的表示。这个对象有一个`name`属性，可以用来获取这个`fs.Dirent`对象引用的文件名。该名称可以被访问并显示给该用户。`readSync()`方法会自动读取下一个目录条目，当没有条目时返回 null。这可用于连续循环条目，并使用 while 循环获得所有文件名。

方法`fs.opendir()`的异步变化也可以用来代替这个函数，这个函数用`fs.Dir`对象而不是对象本身返回一个回调。

**示例:**

```
// Import the filesystem module
const fs = require("fs");

let directory_name = "example_dir";

// Open the directory
let openedDir = fs.opendirSync(directory_name);

// Print the pathname of the directory
console.log("\nPath of the directory:", openedDir.path);

// Get the files present in the directory
console.log("Files Present in directory:");

let filesLeft = true;
while (filesLeft) {
  // Read a file as fs.Dirent object
  let fileDirent = openedDir.readSync();

  // If readSync() does not return null
  // print its filename
  if (fileDirent != null)
    console.log("Name:", fileDirent.name);

  // If the readSync() returns null
  // stop the loop
  else filesLeft = false;
}
```

**输出:**

```
Path of the directory: example_dir
Files Present in directory:
Name: file_a.txt
Name: file_b.txt
Name: file_c.tx

```