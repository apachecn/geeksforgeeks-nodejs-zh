# 来自 fs 的 Node.js stats.nlink 属性。统计等级

> 原文:[https://www . geesforgeks . org/node-js-stats-nlink-property-from-fs-stats-class/](https://www.geeksforgeeks.org/node-js-stats-nlink-property-from-fs-stats-class/)

**stats.nlink 属性**是 fs 内置的应用编程接口。用于获取文件硬链接数量的 Stats 类。

**语法:**

```js
stats.nlink;
```

**返回值:**返回一个数字或 BigInt 值，代表文件的硬链接数。

下面的例子说明了 stats.nlink 属性在 Node.js 中的使用:

**例 1:**

```js
// Node.js program to demonstrate the   
// stats.nlink property

// Accessing fs module
const fs = require('fs');

// Calling fs.Stats stats.nlink for 
// files using stat
fs.stat('./filename.txt', (err, stats) => {
  if (err) throw err;
  console.log("using stat: number of "
    + "hard-links for the file is "
    + stats.nlink);
});

// Using lstat
fs.lstat('./filename.txt', (err, stats) => {
  if (err) throw err;
  console.log("using lstat: number of "
    + "hard-links for the file is "
    + stats.nlink);
});

// For directories
// Using stat
fs.stat('./', (err, stats) => {
  if (err) throw err;
  console.log("using stat: number of "
    + "hard-links for the file is "
    + stats.nlink);
});

// Using lstat
fs.lstat('./', (err, stats) => {
  if (err) throw err;
  console.log("using lstat: number of "
    + "hard-links for the file is "
    + stats.nlink);
});
```

**输出:**

```js
using stat: number of hard-links for the file is  1
using lstat: number of hard-links for the file is  1
using stat: number of hard-links for the file is  1
using lstat: number of hard-links for the file is  1

```

**例 2:**

```js
// Node.js program to demonstrate the   
// stats.nlink property

// Accessing fs module
const fs = require('fs').promises;

// Calling fs.Stats stats.nlink
(async () => {
    const stats = await fs.stat('./filename.txt');
    console.log("using stat synchronous: number "
        + "of hard-links for the file is "
        + stats.nlink);
})().catch(console.error)
```

**输出:**

```js
(node:13780) ExperimentalWarning: The fs.promises API 
is experimental 
using stat synchronous: number of hard-links for the file is 1
```

**注意:**以上程序使用`node filename.js`命令编译运行，正确使用 file_path。

**参考资料:**[https://nodejs . org/API/fs . html # fs _ stats _ online](https://nodejs.org/api/fs.html#fs_stats_nlink)