# Node.js fs.closeSync()方法

> 原文:[https://www.geeksforgeeks.org/node-js-fs-closesync-method/](https://www.geeksforgeeks.org/node-js-fs-closesync-method/)

**fs.closeSync()方法**用于同步关闭给定的文件描述符，从而清除与之关联的文件。它允许文件描述符被其他文件重用。在文件描述符上调用 fs.closeSync()同时对其执行其他操作可能会导致未定义的行为。

**语法:**

```
fs.closeSync( fd )
```

**参数:**该方法接受单个参数，如上所述，如下所述:

*   **FD:** is an integer that represents the file descriptor of the file to be closed.

下面的例子说明了 Node.js 中的 **fs.closeSync()方法**:

**示例 1:** 此示例显示了文件描述符的关闭。

```
// Node.js program to demonstrate the
// fs.closeSync() method

// Import the filesystem module
const fs = require('fs');

// Get the file descriptor of the given path
file_descriptor = fs.openSync("example.txt");
console.log("The file descriptor is:", file_descriptor);

// Close the file descriptor
try {
  fs.closeSync(file_descriptor);
  console.log("\n> File Closed successfully");
} catch (err) {
  console.error('Failed to close file');
}
```

**输出:**

```
The file descriptor is: 3

> File Closed successfully
```

**示例 2:** 此示例显示了关闭文件描述符并尝试再次访问关闭的文件描述符。

```
// Node.js program to demonstrate the
// fs.closeSync() method

// Import the filesystem module
const fs = require('fs');

// Get the file descriptor of the given path
file_descriptor = fs.openSync("example.txt");
console.log("The file descriptor is:", file_descriptor);

// Attempting to get stats before closing
console.log("\n> Finding the stats of the file");
try {
  statsObj = fs.fstatSync(file_descriptor);
  console.log("Stats of the file generated");
} catch (err) {
  console.error('Cannot find stats of file', err);
}

// Close the file descriptor
try {
  fs.closeSync(file_descriptor);
  console.log("\n> File Closed successfully");
} catch (err) {
  console.error('Failed to close file', err);
}

// Attempting to find stats after closing
console.log("\n> Finding the stats of the file again");
try {
  statsObj = fs.fstatSync(file_descriptor);
  console.log("Stats of the file generated");
} catch (err) {
  console.error('Cannot find stats of file', err);
}
```

**输出:**

```
The file descriptor is: 3

> Finding the stats of the file
Stats of the file generated

> File Closed successfully

> Finding the stats of the file again
Cannot find stats of file Error: EBADF: bad file descriptor, fstat
    at Object.fstatSync (fs.js:897:3)
    at Object. (G:\tutorials\nodejs-fs-closeSync\index.js:46:17)
    at Module._compile (internal/modules/cjs/loader.js:956:30)
    at Object.Module._extensions..js (internal/modules/cjs/loader.js:973:10)
    at Module.load (internal/modules/cjs/loader.js:812:32)
    at Function.Module._load (internal/modules/cjs/loader.js:724:14)
    at Function.Module.runMain (internal/modules/cjs/loader.js:1025:10)
    at internal/main/run_main_module.js:17:11 {
  fd: 3,
  errno: -4083,
  syscall: 'fstat',
  code: 'EBADF'
}
```

**参考资料:**[https://nodejs . org/API/fs . html # fs _ fs _ close NC _ FD](https://nodejs.org/api/fs.html#fs_fs_closesync_fd)