# Node.js fs.ftruncate()方法

> 原文:[https://www.geeksforgeeks.org/node-js-fs-ftruncate-method/](https://www.geeksforgeeks.org/node-js-fs-ftruncate-method/)

**fs.ftruncate()方法**用于更改文件大小，即增加或减少文件大小。它通过 len 字节改变文件在路径上的长度。如果 len 短于文件的当前长度，文件将被截断到该长度。如果它大于文件长度，则通过附加空字节(x00)来填充它，直到达到 len。它类似于 truncate()方法，只是它接受要截断的文件的文件描述符。

**语法:**

```
fs.ftruncate(fd, len, callback)
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **[FD:** is an integer value that represents the file descriptor of the file to be truncated.
*   **len:** It is an integer value that specifies the length of the file, after which the file will be truncated. This is an optional parameter. The default value is 0, which means that the whole file will be truncated.
*   **Callback:** is a function that will be called when the method is executed.
    *   **err:** If the method fails, this error will be thrown.

下面的例子说明了 Node.js 中的 **fs.ftruncate()方法**:

**例 1:**

```
// Node.js program to demonstrate the
// fs.ftruncate() method

// Import the filesystem module
const fs = require('fs');

console.log("Contents of file before truncate:")
console.log(fs.readFileSync('example_file.txt', 'utf8'));

// Get the file descriptor of the file
const fd = fs.openSync('example_file.txt', 'r+');

fs.ftruncate(fd, 24, (err) => {
  if (err)
    console.log(err)
  else {
    console.log("Contents of file after truncate:")
    console.log(fs.readFileSync('example_file.txt', 'utf8'));
  }
});
```

**输出:**

```
Contents of file before truncate:
This is an example file for the ftruncate() method.
Contents of file after truncate:
This is an example file
```

**例 2:**

```
// Node.js program to demonstrate the
// fs.ftruncate() method

// Import the filesystem module
const fs = require('fs');

console.log("Contents of file before truncate:")
console.log(fs.readFileSync('example_file.txt', 'utf8'));

// get the file descriptor of the file
const fd = fs.openSync('example_file.txt', 'r+');

// Truncate the whole file
fs.ftruncate(fd, (err) => {
  if (err)
    console.log(err)
  else {
    console.log("Contents of file after truncate:")
    console.log(fs.readFileSync('example_file.txt', 'utf8'));
  }
});
```

**输出:**

```
Contents of file before truncate:
This is an example file for the ftruncate() method.
Contents of file after truncate:
```

**参考:**[https://nodejs . org/API/fs . html # fs _ fs _ ftuncate _ FD _ len _ callback](https://nodejs.org/api/fs.html#fs_fs_ftruncate_fd_len_callback)