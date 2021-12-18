# Node.js stats.ino 属性

> 原文:[https://www.geeksforgeeks.org/node-js-stats-ino-property/](https://www.geeksforgeeks.org/node-js-stats-ino-property/)

属性是 fs 的一个内置应用程序编程接口。Stats 类用于获取文件系统指定的文件的“Inode”号。

**语法:**

```
stats.ino;
```

**参数:**该属性没有任何参数。

**返回值:**返回一个数字或 BigInt 值，代表文件系统指定的文件的“Inode”号。

下面的例子说明了 stats.ino 属性在 Node.js 中的使用:

**例 1:**

```
// Node.js program to demonstrate the   
// stats.ino Property

// Accessing fs module
const fs = require('fs');

// Calling stats.ino property from
// fs.Stats  class
// For files using stat
fs.stat('./filename.txt', (err, stats) => {
    if (err) throw err;
    console.log("using stat: the \"Inode\" "
        + "number of the file is  " + stats.ino);
});

// Using lstat
fs.lstat('./filename.txt', (err, stats) => {
    if (err) throw err;
    console.log("using lstat: the \"Inode\" "
        + "number of the file is  " + stats.ino);
});

// For directories using stat
fs.stat('./', (err, stats) => {
    if (err) throw err;
    console.log("using stat: the \"Inode\" "
        + "number of the file is  " + stats.ino);
});

//using lstat
fs.lstat('./', (err, stats) => {
    if (err) throw err;
    console.log("using lstat: the \"Inode\" "
    + "number of the file is  " + stats.ino);
});
```

**输出:**

```
using stat: the "Inode" number of the file is  1125899907737972
using lstat: the "Inode" number of the file is  1125899907737972
using stat: the "Inode" number of the file is  14918173765820528
using lstat: the "Inode" number of the file is  14918173765820528

```

**例 2:**

```
// Node.js program to demonstrate the   
// stats.ino Property

// Accessing fs module
const fs = require('fs').promises;

// Calling stats.ino property from
// fs.Stats class
(async() => {
  const stats = await fs.stat('./filename.txt');

  // Using stat synchronous
  console.log("The \"Inode\" number "
    + "of the file is  "+stats.ino);
})().catch(console.error)
```

**输出:**

```
The "Inode" number of the file is  1125899907737972

```

**注意:**以上程序使用`node filename.js`命令编译运行，正确使用 file_path。

**参考资料:**[https://nodejs . org/API/fs . html # fs _ stats _ ino](https://nodejs.org/api/fs.html#fs_stats_ino)