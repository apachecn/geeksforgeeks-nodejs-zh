# 来自 fs 的 Node.js stats.blksize 属性。统计等级

> 原文:[https://www . geesforgeks . org/node-js-stats-blk size-property-from-fs-stats-class/](https://www.geeksforgeeks.org/node-js-stats-blksize-property-from-fs-stats-class/)

**stats.blksize 属性**是 fs 的内置应用编程接口。Stats 类用于获取文件系统中输入/输出操作的块大小(以字节为单位)。

**语法:**

```js
stats.blksize;
```

**返回值:**它返回一个数字或 BigInt 值，以字节为单位表示文件系统中输入/输出操作的块大小。

下面的例子说明了 stats.blksize 在 Node.js 中的使用:

**例 1:**

```js
// Node.js program to demonstrate the   
// stats.blksize property

// Accessing fs module
const fs = require('fs');

// Calling fs.Stats stats.blksize
// using stat
fs.stat('./', (err, stats) => {
  if (err) throw err;
  console.log("using stat: the block "
    + "size for I/O operations in the"
    + " file system in bytes is "
    + stats.blksize);
});

// Using lstat
fs.lstat('./', (err, stats) => {
  if (err) throw err;
  console.log("using lstat: the block "
    + "size for I/O operations in the "
    + "file system in bytes is "
    + stats.blksize);
});
```

**输出:**

```js
using stat: the block size for I/O operations 
in the file in bytes is  4096
using lstat: the block size for I/O operations 
in the file in bytes is  4096

```

**例 2:**

```js
// Node.js program to demonstrate the   
// stats.blksize property

// Accessing fs module
const fs = require('fs').promises;

// Calling fs.Stats stats.blksize
(async () => {
    const stats = await fs.stat('./');
    console.log("using stat synchronous: "
        + "the block size for I/O operations"
        + " in the file system in bytes is " 
        + stats.blksize);
})().catch(console.error)
```

**输出:**

```js
(node:6376) ExperimentalWarning: The fs.promises
API is experimental
using stat synchronous: the block size for I/O 
operations in the file system in bytes is  4096

```

**注意:**以上程序使用`node filename.js`命令编译运行，正确使用 file_path。

**参考资料:**[https://nodejs . org/API/fs . html # fs _ stats _ blksi ze](https://nodejs.org/api/fs.html#fs_stats_blksize)