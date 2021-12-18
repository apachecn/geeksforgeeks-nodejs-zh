# Node.js fs .截断同步()方法

> 原文:[https://www . geesforgeks . org/node-js-fs-截断同步-method/](https://www.geeksforgeeks.org/node-js-fs-truncatesync-method/)

**fs .截断同步()方法**用于同步改变文件大小，即增加或减少文件大小。它通过 len 字节改变文件在路径上的长度。如果 len 短于文件的当前长度，文件将被截断到该长度。如果它大于文件长度，则通过附加空字节(x00)来填充它，直到达到 len。

**语法:**

```js
fs.truncateSync( path, len )
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **Path:** It is a string, buffer and web address, which indicates the path of the file that must be transmitted.
*   **len:** It is an integer that specifies the length of the file, after which the file will be truncated. This is an optional parameter. The default value is 0, which means that the whole file will be truncated.

以下示例说明了 Node.js 中的 **fs .截断同步()方法**:

**例 1:**

```js
// Node.js program to demonstrate the
// fs.truncateSync() method

// Import the filesystem module
const fs = require('fs');

console.log("Contents of file before truncate:")
console.log(fs.readFileSync('example_file.txt', 'utf8'));

fs.truncateSync('example_file.txt', 18);

console.log("Contents of file after truncate:")
console.log(fs.readFileSync('example_file.txt', 'utf8'));
```

**输出:**

```js
Contents of file before truncate:
This is an example file for the truncateSync() method.
Contents of file after truncate:
This is an example
```

**例 2:**

```js
// Node.js program to demonstrate the
// fs.truncateSync() method

// Import the filesystem module
const fs = require('fs');

console.log("Contents of file before truncate:")
console.log(fs.readFileSync('example_file.txt', 'utf8'));

// Truncate the whole file
fs.truncateSync('example_file.txt');

console.log("Contents of file after truncate:")
console.log(fs.readFileSync('example_file.txt', 'utf8'));
```

**输出:**

```js
Contents of file before truncate:
This is an example file for the truncateSync() method.
Contents of file after truncate:

```

**参考:**T2】https://nodejs.org/api/fs.html#fs_fs_truncatesync_path_len