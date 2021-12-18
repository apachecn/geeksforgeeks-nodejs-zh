# Node.js fs.statSync()方法

> 原文:[https://www.geeksforgeeks.org/node-js-fs-statsync-method/](https://www.geeksforgeeks.org/node-js-fs-statsync-method/)

**fs.statSync()方法**用于同步返回给定文件路径的信息。fs。返回的 Stat 对象有几个字段和方法来获取文件的更多细节。
**语法:**

```js
fs.statSync( path, options )
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **路径:**保存需要检查的文件的路径。它可以是字符串、缓冲区或网址。
*   **选项:**是一个可以用来指定影响输出的可选参数的对象。它有一个可选参数:
    *   **bigint:** 它是一个布尔值，指定在 fs 中返回的数值。Stats 对象是 bigint。默认值为假。

**返回:**返回一个 Stats 对象，其中包含文件路径的详细信息。
以下示例说明了 Node.js:
**示例 1:** 中的 **fs.statSync()方法**本示例使用 fs.statSync()方法获取路径的详细信息。

## java 描述语言

```js
// Node.js program to demonstrate the
// fs.statSync() method

// Import the filesystem module
const fs = require('fs');

// Getting information for a file
statsObj = fs.statSync("test_file.txt");

console.log(statsObj); 
console.log("Path is file:", statsObj.isFile());
console.log("Path is directory:", statsObj.isDirectory());

// Getting information for a directory
statsObj = fs.statSync("test_directory");

console.log(statsObj);
console.log("Path is file:", statsObj.isFile());
console.log("Path is directory:", statsObj.isDirectory());
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
  ino: 1970324837039946,
  size: 0,
  blocks: 0,
  atimeMs: 1582306776282,
  mtimeMs: 1582482953967,
  ctimeMs: 1582482953968.2532,
  birthtimeMs: 1582306776282.142,
  atime: 2020-02-21T17:39:36.282Z,
  mtime: 2020-02-23T18:35:53.967Z,
  ctime: 2020-02-23T18:35:53.968Z,
  birthtime: 2020-02-21T17:39:36.282Z
}
Path is file: true
Path is directory: false
Stats {
  dev: 3229478529,
  mode: 16822,
  nlink: 1,
  uid: 0,
  gid: 0,
  rdev: 0,
  blksize: 4096,
  ino: 562949953486669,
  size: 0,
  blocks: 0,
  atimeMs: 1582482965037.8445,
  mtimeMs: 1581074249467.7114,
  ctimeMs: 1582482964979.8303,
  birthtimeMs: 1582306776288.1958,
  atime: 2020-02-23T18:36:05.038Z,
  mtime: 2020-02-07T11:17:29.468Z,
  ctime: 2020-02-23T18:36:04.980Z,
  birthtime: 2020-02-21T17:39:36.288Z
}
Path is file: false
Path is directory: true
```

**示例 2:** 本示例使用 fs.statSync()方法，通过 bigint 选项获取文件的详细信息。

## java 描述语言

```js
// Node.js program to demonstrate the
// fs.stat() method

// Import the filesystem module
const fs = require('fs');

statsObj = fs.statSync("test_file.txt");
console.log(statsObj);

// Using the bigint option to return
// the values in big integer format
statsObj = fs.statSync("test_file.txt", {bigint: true});
console.log(statsObj);
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
  ino: 1970324837039946,
  size: 0,
  blocks: 0,
  atimeMs: 1582306776282,
  mtimeMs: 1582482953967,
  ctimeMs: 1582482953968.2532,
  birthtimeMs: 1582306776282.142,
  atime: 2020-02-21T17:39:36.282Z,
  mtime: 2020-02-23T18:35:53.967Z,
  ctime: 2020-02-23T18:35:53.968Z,
  birthtime: 2020-02-21T17:39:36.282Z
}
BigIntStats {
  dev: 3229478529n,
  mode: 33206n,
  nlink: 1n,
  uid: 0n,
  gid: 0n,
  rdev: 0n,
  blksize: 4096n,
  ino: 1970324837039946n,
  size: 0n,
  blocks: 0n,
  atimeMs: 1582306776282n,
  mtimeMs: 1582482953967n,
  ctimeMs: 1582482953968n,
  birthtimeMs: 1582306776282n,
  atimeNs: 1582306776282000000n,
  mtimeNs: 1582482953967000000n,
  ctimeNs: 1582482953968253100n,
  birthtimeNs: 1582306776282142200n,
  atime: 2020-02-21T17:39:36.282Z,
  mtime: 2020-02-23T18:35:53.967Z,
  ctime: 2020-02-23T18:35:53.968Z,
  birthtime: 2020-02-21T17:39:36.282Z
}
```

**参考:**T2https://nodejs.org/api/fs.html#fs_fs_statsync_path_options