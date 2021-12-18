# Node.js fs.close()方法

> 原文:[https://www.geeksforgeeks.org/node-js-fs-close-method/](https://www.geeksforgeeks.org/node-js-fs-close-method/)

**fs.close()方法**用于异步关闭给定的文件描述符，从而清除与之关联的文件。这将允许文件描述符被其他文件重用。在文件描述符上执行其他操作时调用 fs.close()可能会导致未定义的行为。

**语法:**

```
fs.close( fd, callback )
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **FD:** is an integer that represents the file descriptor of the file to be closed.
*   **Callback:** is a function that will be called when the method is executed.
    *   **err:** This is an error that will be thrown if the method fails.

下面的例子说明了 Node.js 中的 **fs.close()方法**:

**示例 1:** 此示例显示了文件描述符的关闭。

```
// Node.js program to demonstrate the
// fs.close() method

// Import the filesystem module
const fs = require('fs');

// Get the file descriptor of the given path
file_descriptor = fs.openSync("example.txt");
console.log("The file descriptor is:", file_descriptor);

// Close the file descriptor
fs.close(file_descriptor, (err) => {
  if (err)
    console.error('Failed to close file', err);
  else {
    console.log("\n> File Closed successfully");
  }
});
```

**输出:**

```
The file descriptor is: 3

> File Closed successfully

```

**示例 2:** 此示例显示了关闭文件描述符并尝试再次访问该关闭的文件描述符。

```
// Node.js program to demonstrate the
// fs.close() method

// Import the filesystem module
const fs = require('fs');

// Get the file descriptor of the given path
file_descriptor = fs.openSync("example.txt");
console.log("The file descriptor is:", file_descriptor);

console.log("\n> Finding the stats of the file");
try {

  // Attempting to find stats of file before closing
  statsObj = fs.fstatSync(file_descriptor);
  console.log("Stats of the file generated");

  // Closing the file descriptor
  console.log("\n> Closing the file descriptor");
  fs.close(file_descriptor, (err) => {
    if (err)
      console.error("Failed to close file", err);
    else {
      console.log("File Closed successfully");

      try {
        // Attempting to find stats of file after closing
        console.log("\n> Finding the stats of the file again");
        statsObj = fs.fstatSync(file_descriptor);
        console.log("Stats of the file generated");
      }
      catch (err) {
        console.error("Cannot find stats of file", err);
      }
    }
  });

} catch (err) {
  console.error("Cannot find stats of file", err);
}
```

**输出:**

```
The file descriptor is: 3

> Finding the stats of the file
Stats of the file generated

> Closing the file descriptor
File Closed successfully

> Finding the stats of the file again
Cannot find stats of file Error: EBADF: bad file descriptor, fstat
    at Object.fstatSync (fs.js:897:3)
    at G:\tutorials\nodejs-fs-close\index.js:42:23
    at FSReqCallback.oncomplete (fs.js:146:23) {
  fd: 3,
  errno: -4083,
  syscall: 'fstat',
  code: 'EBADF'
}

```

**参考:**T2】https://nodejs.org/api/fs.html#fs_fs_close_fd_callback