# Node.js fs.opendir()方法

> 原文:[https://www.geeksforgeeks.org/node-js-fs-opendir-method/](https://www.geeksforgeeks.org/node-js-fs-opendir-method/)

**fs.opendir()方法**用于异步打开文件系统中的一个目录。它会创建一个 fs。用于表示目录的 Dir 对象。该对象包含可用于访问目录的各种方法。

**语法:**

```
fs.opendir( path[, options], callback )
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **Path:** It is a string, buffer or web address that indicates the path of the directory that must be opened.
*   **Option:** It is a string or an object that can be used to specify optional parameters that will affect the output. It has two optional parameters:
    *   **Code:** It is a string that specifies the code of the path when opening the directory and the code of the subsequent reading operation. The default value is utf8.
    *   **Buffersize:** It is a number that specifies the number of directory entries buffered internally when reading the directory. A higher value means higher performance, but it will lead to higher memory usage. The default value is 32.
*   **Callback:** is a function that will be called when the method is executed.
    *   **err:** If the method fails, this error will be thrown.
    *   **dir:** is an fs. A Dir object created by the method that represents the directory.

下面的例子说明了 Node.js 中的 **fs.opendir()方法**:

**例 1:**

```
// Node.js program to demonstrate the
// fs.opendir() method

// Import the filesystem module
const fs = require('fs');

// Open the directory
console.log("Opening the directory");
fs.opendir(

  // Path of the directory
  "example_dir",

  // Options for modifying the operation
  { encoding: "utf8", bufferSize: 64 },

  // Callback with the error and returned
  // directory
  (err, dir) => {
    if (err) console.log("Error:", err);
    else {
      // Print the pathname of the directory
      console.log("Path of the directory:", dir.path);

      // Close the directory
      console.log("Closing the directory");
      dir.closeSync();
    }
  }
);
```

**输出:**

```
Opening the directory
Path of the directory: example_dir
Closing the directory

```

**例 2:**

```
// Node.js program to demonstrate the
// fs.opendir() method

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
fs.opendir("example_dir", (err, dir) => {
  if (err) console.log("Error:", err);
  else {
    // Print the pathname of the directory
    console.log("\nPath of the directory:", dir.path);

    // Read the files in the directory
    // as fs.Dirent objects
    console.log("First Dirent:", dir.readSync());
    console.log("Next Dirent:", dir.readSync());
    console.log("Next Dirent:", dir.readSync());
  }
});
```

**输出:**

```
Current filenames in directory:
file_a.txt
file_b.txt

Path of the directory: example_dir
First Dirent: Dirent { name: 'file_a.txt', [Symbol(type)]: 1 }
Next Dirent: Dirent { name: 'file_b.txt', [Symbol(type)]: 1 }
Next Dirent: null

```

**参考:**[https://nodejs . org/API/fs . html # fs _ fs _ opendir _ path _ options _ callback](https://nodejs.org/api/fs.html#fs_fs_opendir_path_options_callback)