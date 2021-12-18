# Node.js stats.mtime 属性

> 原文:[https://www.geeksforgeeks.org/node-js-stats-mtime-property/](https://www.geeksforgeeks.org/node-js-stats-mtime-property/)

**stats.mtime** 属性是 fs 的内置应用程序编程接口。Stats 类用于获取上次修改文件时的时间戳。

**语法:**

```
stats.mtime;
```

**参数:**属性没有任何参数。

**返回值:**返回一个日期，代表文件上次修改的时间戳。

下面的例子说明了 stats.mtime 属性在 Node.js 中的使用:

**例 1:**

```
// Node.js program to demonstrate the   
// stats.mtime Property

// Accessing fs module
const fs = require('fs');

// Calling fs.Stats stats.mtime
// using stat
fs.stat('./', (err, stats) => {
    if (err) throw err;

    // The timestamp when the file
    // is last modified   
    console.log("Using stat: " + stats.mtime);
});

//using lstat
fs.lstat('./filename.txt', (err, stats) => {
    if (err) throw err;

    // The timestamp when the file
    // is last modified   
    console.log("Using lstat: " + stats.mtime);
});
```

**输出:**

```
Using stat: Sun Jun 21 2020 01:08:08 GMT+0530 (India Standard Time)
Using lstat: Sun Jun 21 2020 01:10:16 GMT+0530 (India Standard Time)

```

**例 2:**

```
// Node.js program to demonstrate the   
// stats.mtime Property

// Accessing fs module
const fs = require('fs').promises;

// Calling fs.Stats stats.mtime
(async () => {
    const stats = await fs.stat('./filename.txt');

    // The timestamp when the file
    // is last modified  
    console.log("Using stat synchronous: "
                + stats.mtime);
})().catch(console.error)
```

**输出:**

```
Using stat synchronous: Sun Jun 21 2020 01:10:16 GMT+0530
                                    (India Standard Time)

```

**注意:**以上程序使用`node filename.js`命令编译运行，正确使用 file_path。

**参考资料:**[https://nodejs . org/API/fs . html # fs _ stats _ mtime](https://nodejs.org/api/fs.html#fs_stats_mtime)