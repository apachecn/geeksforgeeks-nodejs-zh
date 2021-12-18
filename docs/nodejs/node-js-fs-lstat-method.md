# Node.js fs.lstat()方法

> 原文:[https://www.geeksforgeeks.org/node-js-fs-lstat-method/](https://www.geeksforgeeks.org/node-js-fs-lstat-method/)

**fs.lstat()方法**类似于 fs.stat()方法，只是它用于返回正在用于引用文件或目录的符号链接的信息。fs。返回的 Stat 对象有几个字段和方法来获取文件的更多细节。

**语法:**

```js
fs.lstat( path, options, callback )
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **Path:** It is a String, Buffer or URL that holds the path of symbolic link.
*   **Option:** is an object that can be used to specify optional parameters that affect output. It has an optional parameter:
    *   **bigint:** It is a Boolean value that specifies whether the value returned in fs is. The Stats object is bigint. The default value is false.
*   **Callback:** is a function that will be called when the method is executed.
    *   **err:** If the method.
    *   **Stats:** is a stats object, which contains the detailed information of the file path.

下面的例子说明了 Node.js 中的 **fs.lstat()方法**:

**示例 1:** 本示例使用 fs.lstat()方法获取文件符号链接的详细信息。

```js
// Node.js program to demonstrate the
// fs.lstat() method

// Import the filesystem module
const fs = require('fs');

fs.symlinkSync(__dirname + "\\example_file.txt",
                        "symlinkToFile", 'file');
console.log("Symlink to file created")

fs.lstat("symlinkToFile", (err, stats) => {
  if (err)
    console.log(err);
  else {
    console.log("Stat of symlinkToFile")
    console.log(stats);
  }
});
```

**输出:**

```js
Symlink to file created
Stat of symlinkToFile
Stats {
  dev: 3229478529,
  mode: 41398,
  nlink: 1,
  uid: 0,
  gid: 0,
  rdev: 0,
  blksize: 4096,
  ino: 281474976780939,
  size: 45,
  blocks: 0,
  atimeMs: 1585207132017.4473,
  mtimeMs: 1585207132017.4473,
  ctimeMs: 1585207132017.4473,
  birthtimeMs: 1585207132017.4473,
  atime: 2020-03-26T07:18:52.017Z,
  mtime: 2020-03-26T07:18:52.017Z,
  ctime: 2020-03-26T07:18:52.017Z,
  birthtime: 2020-03-26T07:18:52.017Z
}
```

**示例 2:** 本示例使用 fs.lstat()方法获取指向文件夹的符号链接的详细信息。

```js
// Node.js program to demonstrate the
// fs.lstat() method

// Import the filesystem module
const fs = require('fs');

fs.symlinkSync(__dirname + "\\example_directory",
                          "symlinkToDir", 'dir');

console.log("Symlink to directory created")

fs.lstat("symlinkToDir", (err, stats) => {
  if (err)
    console.log(err);
  else {
    console.log("Stat of symlinkToDir")
    console.log(stats);
  }
});
```

**输出:**

```js
Symlink to directory created
Stat of symlinkToDir
Stats {
  dev: 3229478529,
  mode: 41398,
  nlink: 1,
  uid: 0,
  gid: 0,
  rdev: 0,
  blksize: 4096,
  ino: 281474976780940,
  size: 46,
  blocks: 0,
  atimeMs: 1585207184224.7136,
  mtimeMs: 1585207184224.7136,
  ctimeMs: 1585207184224.7136,
  birthtimeMs: 1585207184224.7136,
  atime: 2020-03-26T07:19:44.225Z,
  mtime: 2020-03-26T07:19:44.225Z,
  ctime: 2020-03-26T07:19:44.225Z,
  birthtime: 2020-03-26T07:19:44.225Z
}
```

**参考:**[https://nodejs . org/API/fs . html # fs _ fs _ lsat _ path _ options _ callback](https://nodejs.org/api/fs.html#fs_fs_lstat_path_options_callback)