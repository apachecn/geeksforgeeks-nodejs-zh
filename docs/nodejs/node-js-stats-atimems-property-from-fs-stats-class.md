# 来自 fs 的 Node.js stats.atimeMs 属性。统计等级

> 原文:[https://www . geesforgeks . org/node-js-stats-ATI MEMS-property-from-fs-stats-class/](https://www.geeksforgeeks.org/node-js-stats-atimems-property-from-fs-stats-class/)

**stats.atimeMs 属性**是 fs 的内置应用编程接口。Stats 类用于获取自 POSIX 纪元以来最后一次访问文件时的时间戳，以毫秒表示。

**语法:**

```
stats.atimeMs;
```

**参数:**该属性不使用任何参数。

**返回值:**它返回一个数字或 BigInt 值，表示自 POSIX 纪元以来最后一次访问文件时的时间戳，以毫秒表示。

下面的例子说明了 stats.atimeMs 属性在 Node.js 中的使用:

**例 1:**

```
// Node.js program to demonstrate the   
// stats.atimeMs Property

// Accessing fs module
const fs = require('fs');

// Calling fs.Stats stats.atimeMs
// using stat
fs.stat('./', (err, stats) => {
    if (err) throw err;

    // The timestamp when the file
    // is last accessed (in MS) 
    console.log("Using stat: "
            + stats.atimeMs);
});

// Using lstat
fs.lstat('./filename.txt', (err, stats) => {
    if (err) throw err;

    // The timestamp when the file 
    // is last accessed (in MS) 
    console.log("Using lstat: "
            + stats.atimeMs);
});
```

**输出:**

```
Using stat: 1592664011243.8335
Using lstat: 1592664189785.7615

```

**例 2:**

```
// Node.js program to demonstrate the   
// stats.atimeMs Property

// Accessing fs module
const fs = require('fs').promises;

// Calling fs.Stats stats.atimeMs
(async() => {
   const stats = await fs.stat('./filename.txt');

   // The timestamp when the file 
   // is last accessed (in MS) 
   console.log("Using stat synchronous: "
            + stats.atimeMs);
})().catch(console.error)
```

**输出:**

```
Using stat synchronous: 1592664546730.291

```

**注意:**以上程序使用`node filename.js`命令编译运行，正确使用 file_path。

**参考资料:**[https://nodejs . org/API/fs . html # fs _ stats _ atimems](https://nodejs.org/api/fs.html#fs_stats_atimems)