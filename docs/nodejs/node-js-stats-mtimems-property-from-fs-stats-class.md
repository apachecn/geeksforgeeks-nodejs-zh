# 来自 fs 的 Node.js stats.mtimeMs 属性。统计等级

> 原文:[https://www . geesforgeks . org/node-js-stats-MTI MEMS-property-from-fs-stats-class/](https://www.geeksforgeeks.org/node-js-stats-mtimems-property-from-fs-stats-class/)

**stats.mtimeMs 属性**是 fs 的内置应用编程接口。Stats 类用于获取自 POSIX 纪元以来最后一次修改文件时的时间戳，以毫秒表示。

**语法:**

```js
stats.mtimeMs;
```

**参数:**该属性不接受任何参数。

**返回值:**它返回一个数字或 BigInt 值，表示自 POSIX 纪元以来最后一次修改文件时的时间戳，以毫秒表示。

以下示例说明了 stats.mtimeMs 属性在 Node.js:
**中的使用示例 1:**

```js
// Node.js program to demonstrate the   
// stats.mtimeMs Property

// Accessing fs module
const fs = require('fs');

// Calling fs.Stats stats.mtimeMs
// property using stat
fs.stat('./', (err, stats) => {
    if (err) throw err;

    // The timestamp when the file
    // is last modified (in MS) 
    console.log("Using stat: " + stats.mtimeMs);
});

// Using lstat
fs.lstat('./filename.txt', (err, stats) => {
    if (err) throw err;

    // The timestamp when the file 
    // is last modified (in MS)
    console.log("Using lstat: " 
            + stats.mtimeMs);
});
```

**输出:**

```js
Using stat: 1592665056784.809
Using lstat: 1592665183682.0176

```

**例 2:**

```js
// Node.js program to demonstrate the   
// stats.mtimeMs Property

// Accessing fs module
const fs = require('fs').promises;

// Calling fs.Stats stats.mtimeMs
(async () => {
    const stats = await fs.stat('./filename.txt');

    // The timestamp when the file
    // is last modified (in MS) 
    console.log("using stat synchronous: "
                + stats.mtimeMs);
})().catch(console.error)
```

**输出:**

```js
Using stat synchronous: 1592665183682.0176

```

**注意:**以上程序使用`node filename.js`命令编译运行，正确使用 file_path。

**参考资料:**[https://nodejs . org/API/fs . html # fs _ stats _ mtimems](https://nodejs.org/api/fs.html#fs_stats_mtimems)