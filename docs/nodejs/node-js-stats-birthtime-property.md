# Node.js stats.birthtime 属性

> 原文:[https://www . geesforgeks . org/node-js-stats-birthtime-property/](https://www.geeksforgeeks.org/node-js-stats-birthtime-property/)

属性是 fs 的一个内置应用程序编程接口。Stats 类用于获取文件创建时的时间戳。

**语法:**

```
stats.birthtime
```

**返回值:**返回一个日期，代表文件创建时的时间戳。

下面的例子说明了 stats.birthtime 属性在 Node.js 中的使用:

**例 1:**

```
// Node.js program to demonstrate the   
// stats.birthtime property

// Accessing fs module
const fs = require('fs');

// Calling stats.birthtime property
// from  fs.Stats class using stat
fs.stat('./', (err, stats) => {
    if (err) throw err;

    // The timestamp when the file is created
    console.log("Using stat: " + stats.birthtime);
});

// Using lstat
fs.lstat('./filename.txt', (err, stats) => {
    if (err) throw err;

    // The timestamp when the file is created
    console.log("Using lstat: " + stats.birthtime);
});
```

**输出:**

```
Using stat: Wed May 13 2020 18:38:31 GMT+0530 (India Standard Time)
Using lstat: Sun Jun 21 2020 01:22:55 GMT+0530 (India Standard Time)

```

**例 2:**

```
// Node.js program to demonstrate the   
// stats.birthtime property

// Accessing fs module
const fs = require('fs').promises;

// Calling fs.Stats stats.birthtime
(async () => {
    const stats = await fs.stat('./example_file.txt');

    // The timestamp when the file is created 
    console.log("Using stat synchronous: "
        + stats.birthtime);
})().catch(console.error)
```

**输出:**

```
Using stat synchronous: Sun Jun 21 2020 01:22:55 GMT+0530 
                                    (India Standard Time)

```

**注意:**以上程序使用`node filename.js`命令编译运行，正确使用 file_path。

**参考:**T2】https://nodejs.org/api/fs.html#fs_stats_birthtime