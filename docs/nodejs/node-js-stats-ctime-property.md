# Node.js stats.ctime 属性

> 原文:[https://www.geeksforgeeks.org/node-js-stats-ctime-property/](https://www.geeksforgeeks.org/node-js-stats-ctime-property/)

**stats.ctime** 属性是 fs 的一个内置应用编程接口。Stats 类，用于获取上次更改文件状态时的时间戳。

**语法:**

```
stats.ctime
```

**返回值:**返回一个日期值，代表上次文件状态改变时的时间戳。

下面的例子说明了 stats.ctime 属性在 Node.js 中的使用:

**例 1:**

```
// Node.js program to demonstrate the   
// stats.ctime property

// Accessing fs module
const fs = require('fs');

// Calling stats.ctime property from
// fs.Stats class using stat
fs.stat('./', (err, stats) => {
    if (err) throw err;

    // The timestamp when the file status
    // has been changed last time
    console.log("Using stat: " + stats.ctime);
});

// Using lstat
fs.lstat('./filename.txt', (err, stats) => {
    if (err) throw err;

    // The timestamp when the file status
    // has been changed last time 
    console.log("Using lstat: " + stats.ctime);
});
```

**输出:**

```
Using stat: Sun Jun 21 2020 01:17:13 GMT+0530 (India Standard Time)
Using lstat: Sun Jun 21 2020 01:19:02 GMT+0530 (India Standard Time)

```

**例 2:**

```
// Node.js program to demonstrate the   
// stats.ctime property

// Accessing fs module
const fs = require('fs').promises;

// Calling fs.Stats stats.ctime
(async() => {
  const stats = await fs.stat('./filename.txt');

  // The timestamp when the file status
  // has been changed last time 
  console.log("Using stat synchronous: "
                + stats.ctime);
})().catch(console.error)
```

**输出:**

```
(node:2748) ExperimentalWarning: The fs.promises API is experimental
Using stat synchronous: Sun Jun 21 2020 01:19:02 GMT+0530 
                                     (India Standard Time)

```

**注意:**以上程序使用`node filename.js`命令编译运行，正确使用 file_path。

**参考资料:**[https://nodejs . org/API/fs . html # fs _ stats _ victim](https://nodejs.org/api/fs.html#fs_stats_ctime)