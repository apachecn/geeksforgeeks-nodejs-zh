# Node.js fsPromises.stat()方法

> 原文:[https://www . geesforgeks . org/node-js-fspromiss-stat-method/](https://www.geeksforgeeks.org/node-js-fspromises-stat-method/)

**fsPromises.stat()** 方法用于返回给定文件或目录的信息。*承诺*与 fs 解决。给定路径的 Stats 对象。

**语法:**

```js
fsPromises.stat( path, options )
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **Path:** The path to save the file or directory to be checked. It can be a string, a buffer or a web address.
*   **Option:** is an object that can be used to specify optional parameters that affect output. It has an optional parameter:
    *   **bigint:** It is a Boolean value that specifies whether the value returned in fs is. The Stats object is bigint. The default value is false.

下面的例子说明了 Node.js 中的 **fsPromises.stat()** 方法:

**示例 1:** 本示例使用 fsPromises.stat()方法获取路径的详细信息。

```js
// Node.js program to demonstrate the 
// fsPromises.stat() method 

// Import the filesystem module 
const fsPromises = require("fs").promises;
(async () => {
  try {
    await fsPromises.rename("GFG.txt", 
                "GeeksforGeeks.txt");

    // Using the fsPromises.stat() method
    const stats = await fsPromises.stat(
          "GeeksforGeeks.txt");
    console.log(stats);
  } 
  catch (error) {
    console.log(error);
  }
})();
```

**输出:**

```js
Stats {
  dev: 654202934,
  mode: 85416,
  nlink: 1,
  uid: 0,
  gid: 0,
  rdev: 0,
  blksize: undefined,
  ino: 6192449489177455,
  size: 0,
  blocks: undefined,
  atimeMs: 5126587454188,
  mtimeMs: 8845632838067,
  ctimeMs: 5214789541254.1998,
  birthtimeMs: 1572568634187.734,
  atime: 2020-06-10T00:25:14.198ZZ,
  mtime: 2020-06-10T00:38:38.068Z,
  ctime: 2020-06-10T00:38:47.450Z,
  birthtime: 2020-06-101T00:25:14.198Z }

```

**示例 2:** 本示例使用 **fsPromises.stat()** 方法，使用 bigint 选项获取文件的详细信息:

```js
// Node.js program to demonstrate the 
// fsPromises.stat() method 

// Import the filesystem module 
const fsPromises = require("fs").promises;
(async () => {
  try {
    await fsPromises.rename("GFG.txt", 
                 "GeeksforGeeks.txt");

    // Using the fsPromises.stat() method
    const stats = await fsPromises.stat(
      ("GeeksforGeeks.txt"), {bigint: true});
    console.log(stats);
  } 
  catch (error) {
    console.log(error);
  }
})();
```

**输出:**

```js
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

```

**参考:**[https://nodejs . org/API/fs . html # fs _ fspromises _ stat _ path _ options](https://nodejs.org/api/fs.html#fs_fspromises_stat_path_options)