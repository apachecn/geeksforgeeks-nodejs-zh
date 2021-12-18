# 来自 fs 的 Node.js stats.size 属性。统计等级

> 原文:[https://www . geesforgeks . org/node-js-stats-size-property-from-fs-stats-class/](https://www.geeksforgeeks.org/node-js-stats-size-property-from-fs-stats-class/)

**stats.size 属性**是 fs 内置的应用编程接口。Stats 类用于获取文件的大小(以字节为单位)。

**语法:**

```
stats.size;
```

**返回值:**它返回一个数字或 BigInt 值，以字节为单位表示文件的大小。

下面的例子说明了 stats.size 属性在 Node.js 中的使用:

**例 1:**

```
// Node.js program to demonstrate the   
// stats.size property

// Accessing fs module
const fs = require('fs');

// Calling fs.Stats stats.size
// for files using stat
fs.stat('./filename.txt', (err, stats) => {
  if (err) throw err;
  console.log("using stat: the size the "
    + "file in bytes is " + stats.size);
});

// Using lstat
fs.lstat('./filename.txt', (err, stats) => {
  if (err) throw err;
  console.log("using lstat: the size the"
    + " file in bytes is " + stats.size);
});
```

**输出:**

```
using stat: the size the file in bytes is 1112
using lstat: the size the file in bytes is 1112

```

**例 2:**

```
// Node.js program to demonstrate the   
// stats.size property

// Accessing fs module
const fs = require('fs').promises;

// Calling fs.Stats stats.size
(async () => {
    const stats = await fs.stat('./filename.txt');
    console.log("using stat synchronous: the size "
        + "the file in bytes is " + stats.size);
})().catch(console.error)
```

**输出:**

```
(node:7040) ExperimentalWarning: The fs.promises API 
is experimental 
using stat synchronous: the size the file 
in bytes is 1112
```

**注意:**以上程序使用`node filename.js`命令编译运行，正确使用 file_path。

**参考:**T2】https://nodejs.org/api/fs.html#fs_stats_size