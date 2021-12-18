# Node.js fs.fstat()方法

> 原文:[https://www.geeksforgeeks.org/node-js-fs-fstat-method/](https://www.geeksforgeeks.org/node-js-fs-fstat-method/)

**fs.fstat()方法**用于返回给定文件描述符的信息。fs。返回的 Stat 对象有几个字段和方法来获取文件的更多细节。

**语法:**

```js
fs.fstat( fd, options, callback )
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **FD:** It is an integer that represents the file descriptor used by this method.
*   **Option:** is an object that can be used to specify optional parameters that affect output. It has an optional parameter:
    *   **bigint:** It is a Boolean value that specifies whether the value returned in fs is. The Stats object is bigint. The default value is false.
*   **Callback:** is a function that will be called when the method is executed.
    *   **err:** If the method
    *   **Stats:** is a stats object. If it contains the detailed information of the file path, this error will be thrown.

以下示例说明了 Node.js 中的 **fs.fstat()方法**:

**示例 1:** 本示例使用 fs.fstat()方法获取文件和目录的详细信息。

```js
// Node.js program to demonstrate the
// fs.fstat() method

// Import the filesystem module
const fs = require('fs');

// Define the file descriptor for a file
let file_fd = fs.openSync('example_file.txt', 'r');

// Getting information for a file
fs.fstat(file_fd, (error, stats) => {
  if (error) {
    console.log(error);
  }
  else {
    console.log("Stats object for: example_file.txt");
    console.log(stats);

    // Using methods of the Stats object
    console.log("Path is file:", stats.isFile());
    console.log("Path is directory:", stats.isDirectory());
  }
});

// Define the file descriptor for a folder
let dir_fd = fs.openSync('example_directory', 'r');

// Getting information for a directory
fs.fstat(dir_fd, (error, stats) => {
  if (error) {
    console.log(error);
  }
  else {
    console.log("Stats object for: example_directory.txt");
    console.log(stats);

    // Using methods of the Stats object
    console.log("Path is file:", stats.isFile());
    console.log("Path is directory:", stats.isDirectory());
  }
});
```

**输出:**

```js
Stats object for: example_file.txt
Stats {
  dev: 3229478529,
  mode: 33206,
  nlink: 1,
  uid: 0,
  gid: 0,
  rdev: 0,
  blksize: 4096,
  ino: 281474976780635,
  size: 0,
  blocks: 0,
  atimeMs: 1584389463707.251,
  mtimeMs: 1582209885466.6848,
  ctimeMs: 1582209885466.6848,
  birthtimeMs: 1584389463707.251,
  atime: 2020-03-16T20:11:03.707Z,
  mtime: 2020-02-20T14:44:45.467Z,
  ctime: 2020-02-20T14:44:45.467Z,
  birthtime: 2020-03-16T20:11:03.707Z
}
Path is file: true
Path is directory: false
Stats object for: example_directory.txt
Stats {
  dev: 3229478529,
  mode: 16822,
  nlink: 1,
  uid: 0,
  gid: 0,
  rdev: 0,
  blksize: 4096,
  ino: 281474976780638,
  size: 0,
  blocks: 0,
  atimeMs: 1584429828080.8872,
  mtimeMs: 1581074249467.7114,
  ctimeMs: 1584389463715.2507,
  birthtimeMs: 1584389463715.2507,
  atime: 2020-03-17T07:23:48.081Z,
  mtime: 2020-02-07T11:17:29.468Z,
  ctime: 2020-03-16T20:11:03.715Z,
  birthtime: 2020-03-16T20:11:03.715Z
}
Path is file: false
Path is directory: true
```

**示例 2:** 本示例使用 fs.fstat()方法获取包含和不包含 bigint 选项的文件的详细信息。

```js
// Node.js program to demonstrate the
// fs.fstat() method

// Import the filesystem module
const fs = require('fs');

// Define the file descriptor for a file
let file_fd = fs.openSync('example_file.txt', 'r');

fs.fstat(file_fd, (error, stats) => {
  console.log(stats);
});

// Using the bigint option to return
// the values in big integer format
fs.fstat(file_fd, { bigint: true }, (error, stats) => {
  console.log(stats);
});
```

**输出:**

```js
Stats {
  dev: 3229478529,
  mode: 33206,
  nlink: 1,
  uid: 0,
  gid: 0,
  rdev: 0,
  blksize: 4096,
  ino: 281474976780635,
  size: 0,
  blocks: 0,
  atimeMs: 1584389463707.251,
  mtimeMs: 1582209885466.6848,
  ctimeMs: 1582209885466.6848,
  birthtimeMs: 1584389463707.251,
  atime: 2020-03-16T20:11:03.707Z,
  mtime: 2020-02-20T14:44:45.467Z,
  ctime: 2020-02-20T14:44:45.467Z,
  birthtime: 2020-03-16T20:11:03.707Z
}
BigIntStats {
  dev: 3229478529n,
  mode: 33206n,
  nlink: 1n,
  uid: 0n,
  gid: 0n,
  rdev: 0n,
  blksize: 4096n,
  ino: 281474976780635n,
  size: 0n,
  blocks: 0n,
  atimeMs: 1584389463707n,
  mtimeMs: 1582209885466n,
  ctimeMs: 1582209885466n,
  birthtimeMs: 1584389463707n,
  atimeNs: 1584389463707251000n,
  mtimeNs: 1582209885466684900n,
  ctimeNs: 1582209885466684900n,
  birthtimeNs: 1584389463707251000n,
  atime: 2020-03-16T20:11:03.707Z,
  mtime: 2020-02-20T14:44:45.466Z,
  ctime: 2020-02-20T14:44:45.466Z,
  birthtime: 2020-03-16T20:11:03.707Z
}
```

**参考:**T2【https://nodejs . org/API/fs . html # fs _ fs _ fstat _ FD _ options _ callback