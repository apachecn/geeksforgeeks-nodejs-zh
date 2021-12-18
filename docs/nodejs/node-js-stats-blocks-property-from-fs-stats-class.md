# Node.js stats.blocks 属性来自 fs。统计等级

> 原文:[https://www . geesforgeks . org/node-js-stats-blocks-property-from-fs-stats-class/](https://www.geeksforgeeks.org/node-js-stats-blocks-property-from-fs-stats-class/)

**stats.blocks 属性**是 fs 的一个内置应用编程接口。Stats 类用于获取为文件分配的块数。

**语法:**

```
stats.blocks;
```

**返回值:**它返回一个数字或 BigInt 值，表示为文件分配的块数。

下面的例子说明了 stats.blocks 属性在 Node.js 中的使用:

**例 1:**

```
// Node.js program to demonstrate the
// stats.blocks property

// Accessing fs module
const fs = require('fs');

// Calling fs.Stats stats.blocks
// using stat
fs.stat('./', (err, stats) => {
    if (err) throw err;

    // The number of blocks allocated
    // for the file 
    console.log("using stat: " 
                + stats.blocks);
});

// Using lstat
fs.lstat('./', (err, stats) => {
    if (err) throw err;

    // The number of blocks allocated
    // for the file 
    console.log("using lstat: " 
                + stats.blocks);
});
```

**输出:**

```
using stat: 8
using lstat: 8

```

**例 2:**

```
// Node.js program to demonstrate the
// stats.blocks property

// Accessing fs module
const fs = require('fs').promises;

// Calling fs.Stats stats.blocks
(async () => {
    const stats = await fs.stat('./filename.txt');

    // The number of blocks allocated
    // for the file
    console.log("using stat synchronous: "
                + stats.blocks);
})().catch(console.error)
```

**输出:**

```
using stat synchronous: 8

```

**注意:**以上程序使用`node filename.js`命令编译运行，正确使用 file_path。

**参考:**T2】https://nodejs.org/api/fs.html#fs_stats_blocks