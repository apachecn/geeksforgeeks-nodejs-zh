# node . js fs . ftruncaticesync()方法

> 原文:[https://www . geeksforgeeks . org/node-js-fs-ftruncatesync-method/](https://www.geeksforgeeks.org/node-js-fs-ftruncatesync-method/)

**fs . ftruncatsync()方法**用于同步改变文件大小，即增加或减少文件大小。它通过 len 字节改变文件在路径上的长度。如果 len 短于文件的当前长度，文件将被截断到该长度。如果它大于文件长度，则通过附加空字节(x00)来填充它，直到达到 len。它类似于截断同步()方法，只是它接受要截断的文件的文件描述符。

**语法:**

```
fs.ftruncateSync( fd, len )
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **FD:** It is an integer value that represents the file descriptor of the file to be truncated.
*   **len:** It is an integer value that specifies the length of the file, after which the file will be truncated. This is an optional parameter. The default value is 0, which means that the whole file will be truncated.

下面的例子说明了 Node.js 中的**方法:**

**例 1:**

```
// Node.js program to demonstrate the
// fs.ftruncateSync() method

// Import the filesystem module
const fs = require('fs');

console.log("Contents of file before truncate:")
console.log(fs.readFileSync('example_file.txt', 'utf8'));

// Get the file descriptor of the file
const fd = fs.openSync('example_file.txt', 'r+');

// Truncate the whole file
fs.ftruncateSync(fd);

console.log("Contents of file after truncate:")
console.log(fs.readFileSync('example_file.txt', 'utf8'));
```

**输出:**

```
Contents of file before truncate:
This is an example file for the ftruncateSync() method.
Contents of file after truncate:

```

**例 2:**

```
// Node.js program to demonstrate the
// fs.ftruncateSync() method

// Import the filesystem module
const fs = require('fs');

console.log("Contents of file before truncate:")
console.log(fs.readFileSync('example_file.txt', 'utf8'));

// Get the file descriptor of the file
const fd = fs.openSync('example_file.txt', 'r+');

// Decrease the file size
fs.ftruncateSync(fd, 18);

console.log("Contents of file after truncate:")
console.log(fs.readFileSync('example_file.txt', 'utf8'));

// Increase the file size
fs.ftruncateSync(fd, 25);

console.log("Contents of file in bytes after truncate:")
console.log(fs.readFileSync('example_file.txt'));
```

**输出:**

```
Contents of file before truncate:
This is an example file for the ftruncateSync() method.
Contents of file after truncate:
This is an example
Contents of file in bytes after truncate:

```

**参考:**[https://nodejs . org/API/fs . html # fs _ fs _ ftuncatesync _ FD _ len](https://nodejs.org/api/fs.html#fs_fs_ftruncatesync_fd_len)