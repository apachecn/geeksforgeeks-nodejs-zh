# Node.js fs.stat()方法

> 原文:[https://www.geeksforgeeks.org/node-js-fs-stat-method/](https://www.geeksforgeeks.org/node-js-fs-stat-method/)

**fs.stat()方法**用于返回给定文件或目录的信息。它返回一个 **fs。Stat** 对象，它有几个属性和方法来获取文件或目录的详细信息。

**语法:**

```
fs.stat( path, options, callback )
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **Path:** The path to save the file or directory to be checked. It can be a string, a buffer or a web address.
*   **Option:** is an object that can be used to specify optional parameters that affect output. It has an optional parameter:
    *   **bigint:** It is a Boolean value that specifies whether the value returned in fs is. The Stats object is bigint. The default value is false.
*   **Callback:** is a function that will be called when the method is executed.
    *   **err:** If the method
    *   **stats:** is a stats object. If it contains the detailed information of the file path, this error will be thrown.

下面的例子说明了 Node.js 中的 **fs.stat()方法**:

**示例 1:** 本示例使用 **fs.stat()方法**获取路径的详细信息。

```
// Node.js program to demonstrate the
// fs.stat() method

// Import the filesystem module
const fs = require('fs');

// Getting information for a file
fs.stat("example_file.txt", (error, stats) => {
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

// Getting information for a directory
fs.stat("example_directory.txt", (error, stats) => {
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

```
Stats object for: example_file.txt
Stats {
  dev: 2269,
  mode: 33188,
  nlink: 1,
  uid: 1000,
  gid: 1000,
  rdev: 0,
  blksize: 4096,
  ino: 271,
  size: 0,
  blocks: 0,
  atimeMs: 1582871562365.894,
  mtimeMs: 1582871556897.5554,
  ctimeMs: 1582871556897.5554,
  birthtimeMs: 1582871556897.5554,
  atime: 2020-02-28T06:32:42.366Z,
  mtime: 2020-02-28T06:32:36.898Z,
  ctime: 2020-02-28T06:32:36.898Z,
  birthtime: 2020-02-28T06:32:36.898Z }
Path is file: true
Path is directory: false
Stats object for: example_directory.txt
Stats {
  dev: 2269,
  mode: 33188,
  nlink: 1,
  uid: 1000,
  gid: 1000,
  rdev: 0,
  blksize: 4096,
  ino: 270,
  size: 0,
  blocks: 0,
  atimeMs: 1582871562357.8936,
  mtimeMs: 1582871553413.3396,
  ctimeMs: 1582871553417.3398,
  birthtimeMs: 1582871553413.3396,
  atime: 2020-02-28T06:32:42.358Z,
  mtime: 2020-02-28T06:32:33.413Z,
  ctime: 2020-02-28T06:32:33.417Z,
  birthtime: 2020-02-28T06:32:33.413Z }
Path is file: true
Path is directory: false
```

**示例 2:** 本示例使用 **fs.stat()方法**通过 bigint 选项获取文件的详细信息。

```
// Node.js program to demonstrate the
// fs.stat() method

// Import the filesystem module
const fs = require('fs');

fs.stat("example_file.txt", (error, stats) => {
  console.log(stats);
});

// Using the bigint option to return
// the values in big integer format
fs.stat("example_file.txt", { bigint: true }, (error, stats) => {
  console.log(stats);
});
```

**输出:**

```
Stats {
  dev: 2269,
  mode: 33188,
  nlink: 1,
  uid: 1000,
  gid: 1000,
  rdev: 0,
  blksize: 4096,
  ino: 271,
  size: 0,
  blocks: 0,
  atimeMs: 1582871562365.894,
  mtimeMs: 1582871556897.5554,
  ctimeMs: 1582871556897.5554,
  birthtimeMs: 1582871556897.5554,
  atime: 2020-02-28T06:32:42.366Z,
  mtime: 2020-02-28T06:32:36.898Z,
  ctime: 2020-02-28T06:32:36.898Z,
  birthtime: 2020-02-28T06:32:36.898Z }
Stats {
  dev: 2269n,
  mode: 33188n,
  nlink: 1n,
  uid: 1000n,
  gid: 1000n,
  rdev: 0n,
  blksize: 4096n,
  ino: 271n,
  size: 0n,
  blocks: 0n,
  atimeMs: 1582871562365n,
  mtimeMs: 1582871556897n,
  ctimeMs: 1582871556897n,
  birthtimeMs: 1582871556897n,
  atime: 2020-02-28T06:32:42.365Z,
  mtime: 2020-02-28T06:32:36.897Z,
  ctime: 2020-02-28T06:32:36.897Z,
  birthtime: 2020-02-28T06:32:36.897Z }
```

**参考:**[https://nodejs . org/API/fs . html # fs _ fs _ stat _ path _ options _ callback](https://nodejs.org/api/fs.html#fs_fs_stat_path_options_callback)