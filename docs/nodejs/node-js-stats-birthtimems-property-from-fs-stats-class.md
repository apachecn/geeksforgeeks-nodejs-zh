# 来自 fs 的 Node.js stats.birthtimeMs 属性。统计等级

> 原文:[https://www . geesforgeks . org/node-js-stats-birthtimems-property-from-fs-stats-class/](https://www.geeksforgeeks.org/node-js-stats-birthtimems-property-from-fs-stats-class/)

属性是 fs 的一个内置应用编程接口。Stats 类用于获取文件创建时的时间戳，因为 POSIX 纪元以毫秒表示。

**语法:**

```
stats.birthtimeMs;
```

**返回值:**它返回一个数字或 BigInt 值，表示自 POSIX 纪元以来创建文件时的时间戳，以毫秒表示。

下面的例子说明了 stats.birthtimeMs 属性在 Node.js 中的使用:

**例 1:**

```
// Node.js program to demonstrate the
// stats.birthtimeMs property

// Accessing fs module
const fs = require('fs');

// Calling fs.Stats stats.birthtimeMs
// property using stat
fs.stat('./', (err, stats) => {
    if (err) throw err;

    // The timestamp when the file 
    // is created (in MS)  
    console.log("using stat: "
            + stats.birthtimeMs);
});

// Using lstat
fs.lstat('./filename.txt', (err, stats) => {
    if (err) throw err;

    // The timestamp when the file
    // is created (in MS) 
    console.log("using lstat: " 
            + stats.birthtimeMs);
});
```

**输出:**

```
using stat: 1589375311991.9453
using lstat: 1592667100334.387

```

**例 2:**

```
// Node.js program to demonstrate the
// stats.birthtimeMs property

// Accessing fs module
const fs = require('fs').promises;

// Calling fs.Stats stats.birthtimeMs
(async () => {
    const stats = await fs.stat('./filename.txt');

    // The timestamp when the file 
    // is created (in MS)
    console.log("using stat synchronous: " 
            + stats.birthtimeMs);
})().catch(console.error)
```

**输出:**

```
using stat synchronous: 1592667100334.387

```

**注意:**以上程序使用`node filename.js`命令编译运行，正确使用 file_path。

**参考:**T2】https://nodejs.org/api/fs.html#fs_stats_birthtimems