# 来自 fs 的 Node.js stats.ctimeMs 属性。统计等级

> 原文:[https://www . geesforgeks . org/node-js-stats-CTI MEMS-property-from-fs-stats-class/](https://www.geeksforgeeks.org/node-js-stats-ctimems-property-from-fs-stats-class/)

**stats.ctimeMs 属性**是 fs 的内置应用编程接口。Stats 类，用于获取自 POSIX 纪元以来上次更改文件状态时的时间戳，以毫秒表示。

**语法:**

```
stats.ctimeMs;
```

**返回值:**它返回一个数字或 BigInt 值，表示自 POSIX 纪元以来最后一次更改文件状态时的时间戳，以毫秒表示。

下面的例子说明了 stats.ctimeMs 在 Node.js 中的使用:

**例 1:**

```
// Node.js program to demonstrate the
// stats.ctimeMs property

// Accessing fs module
const fs = require('fs');

// Calling fs.Stats stats.ctimeMs
// using stat
fs.stat('./', (err, stats) => {
    if (err) throw err;

    // The timestamp when the file status 
    // has been changed last time (in MS) 
    console.log("using stat: " + stats.ctimeMs);
});

// Using lstat
fs.lstat('./filename.txt', (err, stats) => {
    if (err) throw err;

    // The timestamp when the file status 
    // has been changed last time (in MS) 
    console.log("using lstat: " + stats.ctimeMs);
});
```

**输出:**

```
using stat: 1592665604516.1057
using lstat: 1592665807796.265

```

**例 2:**

```
// Node.js program to demonstrate the
// stats.ctimeMs property

// Accessing fs module
const fs = require('fs').promises;

// Calling fs.Stats stats.ctimeMs
(async () => {
    const stats = await fs.stat('./filename.txt');

    // The timestamp when the file status 
    // has been changed last time (in MS) 
    console.log("using stat synchronous: "
            + stats.ctimeMs);
})().catch(console.error)
```

**输出:**

```
using stat synchronous: 1592665807796.265

```

**注意:**以上程序使用`node filename.js`命令编译运行，正确使用 file_path。

**参考资料:**[https://nodejs . org/API/fs . html # fs _ stats _ ctimems](https://nodejs.org/api/fs.html#fs_stats_ctimems)