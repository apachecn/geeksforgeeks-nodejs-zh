# Node.js stats.ctimeNs 属性

> 原文:[https://www . geesforgeks . org/node-js-stats-ctimens-property/](https://www.geeksforgeeks.org/node-js-stats-ctimens-property/)

属性是 fs 的一个内置应用程序编程接口。Stats 类用于获取自 POSIX 纪元以来文件状态最后一次更改时的时间戳，以纳秒表示。

**语法:**

```
stats.ctimeNs;
```

**参数:** Properties 没有任何参数，但是在创建 stats 对象期间{bigint:true}必须作为选项传递。

**返回值:**它返回一个数字或 BigInt 值，表示自 POSIX 纪元以来最后一次更改文件状态时的时间戳，单位为纳秒。

下面的例子说明了 stats.ctimeNs 属性在 Node.js 中的使用:

**例 1:**

```
// Node.js program to demonstrate the   
// stats.ctimeNs property

// Accessing fs module
const fs = require('fs');

// Calling stats.ctimeNs property
// from fs.Stats class using stat
fs.stat('./', { bigint: true }, (err, stats) => {
    if (err) throw err;

    // The timestamp when the file status
    // has been changed last time (in NS)
    console.log("Using stat: " + stats.ctimeNs);
});

// Using lstat
fs.lstat('./filename.txt',
    { bigint: true }, (err, stats) => {
        if (err) throw err;

        // The timestamp when the file status
        // has been changed last time (in NS)
        console.log("Using lstat: " + stats.ctimeNs);
    });
```

**输出:**

```
Using stat: 1592665604516105.7
Using lstat: 1592665807796265

```

**例 2:**

```
// Node.js program to demonstrate the   
// stats.ctimeNs property

// Accessing fs module
const fs = require('fs').promises;

// Calling fs.Stats stats.ctimeNs
(async () => {
    const stats = await fs.stat(
        './filename.txt', { bigint: true });

    // The timestamp when the file
    // status has been changed last
    // time (in NS)
    console.log("Using stat synchronous: "
                + stats.ctimeNs);
})().catch(console.error)
```

**输出:**

```
Using stat synchronous: 1592665807796265

```

**注意:**以上程序使用`node filename.js`命令编译运行，正确使用 file_path。

**参考资料:**[https://nodejs . org/API/fs . html # fs _ stats _ ctimen](https://nodejs.org/api/fs.html#fs_stats_ctimens)