# Node.js stats.mtimeNs 属性

> 原文:[https://www . geesforgeks . org/node-js-stats-mtimens-property/](https://www.geeksforgeeks.org/node-js-stats-mtimens-property/)

属性是 fs 的一个内置应用编程接口。Stats 类用于获取自 POSIX 纪元以来文件最后一次被修改时的时间戳，以纳秒表示。

**语法:**

```js
stats.mtimeNs;
```

**参数:** Properties 没有任何参数，但是在创建 stats 对象期间{bigint:true}必须作为选项传递。

**返回值:**返回一个数字或 BigInt 值，表示自 POSIX 纪元以来最后一次修改文件时的时间戳，单位为纳秒。

下面的例子说明了 stats.mtimeNs 属性在 Node.js 中的使用:

**例 1:**

```js
// Node.js program to demonstrate the   
// stats.mtimeNs property

// Accessing fs module
const fs = require('fs');

// Calling fs.Stats stats.mtimeNs using stat
fs.stat('./', { bigint: true }, (err, stats) => {
    if (err) throw err;

    // The timestamp when the file
    // is last modified (in NS)
    console.log("Using stat: " + stats.mtimeNs);
});

// Using lstat
fs.lstat('./filename.txt',
    { bigint: true }, (err, stats) => {
        if (err) throw err;

        // The timestamp when the file
        // is last modified (in NS)
        console.log("Using lstat: " + stats.mtimeNs);
    });
```

**输出:**

```js
Using stat: 1592665056784809
Using lstat: 15926651836820176

```

**例 2:**

```js
// Node.js program to demonstrate the   
// stats.mtimeNs property

// Accessing fs module
const fs = require('fs').promises;

// Calling fs.Stats stats.mtimeNs
(async () => {
    const stats = await fs.stat(
        './filename.txt', { bigint: true });

    // The timestamp when the file
    // is last modified (in NS)
    console.log("Using stat synchronous: "
                + stats.mtimeNs);
})().catch(console.error)
```

**输出:**

```js
Using stat synchronous: 15926651836820176

```

**注意:**以上程序使用`node filename.js`命令编译运行，正确使用 file_path。

**参考资料:**[https://nodejs . org/API/fs . html # fs _ stats _ mtimis](https://nodejs.org/api/fs.html#fs_stats_mtimens)