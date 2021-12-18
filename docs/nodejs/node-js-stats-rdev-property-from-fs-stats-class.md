# 来自 fs 的 Node.js stats.rdev 属性。统计等级

> 原文:[https://www . geesforgeks . org/node-js-stats-rdev-property-from-fs-stats-class/](https://www.geeksforgeeks.org/node-js-stats-rdev-property-from-fs-stats-class/)

**stats.rdev 属性**是 fs 的内置应用编程接口。Stats 类用于获取存储文件的设备的数字(number / bigint)标识，其中文件被认为是“特殊的”。

**语法:**

```js
stats.rdev;
```

**返回值:**它返回一个数字或 BigInt 值，表示文件存储在其中的设备的身份，该文件被认为是“特殊的”。

下面的例子说明了 stats.rdev 属性在 Node.js 中的使用:

**例 1:**

```js
// Node.js program to demonstrate the   
// stats.rdev property

// Accessing fs module
const fs = require('fs');

// Calling fs.Stats stats.rdev
// using stat
fs.stat('./filename.txt', (err, stats) => {
    if (err) throw err;
    console.log("using stat: numeric "
        + "identity of the device is " 
        + stats.rdev);
});

// Using lstat
fs.lstat('./filename.txt', (err, stats) => {
    if (err) throw err;
    console.log("using lstat: numeric "
        + "identity of the device is " 
        + stats.rdev);
});
```

**输出:**

```js
using stat: numeric identity of the device is 0
using lstat: numeric identity of the device is 0

```

**例 2:**

```js
// Node.js program to demonstrate the   
// stats.rdev property

// Accessing fs module
const fs = require('fs').promises;

// Calling fs.Stats stats.rdev
(async() => {
    const stats = await fs.stat('./filename.txt');
  console.log("using stat synchronous: numeric "
    + "identity of the device is " + stats.rdev);
})().catch(console.error)
```

**输出:**

```js
(node:1656) ExperimentalWarning: The fs.promises API 
is experimental 
using stat synchronous: numeric identity of the device is 0

```

**注意:**以上程序使用`node filename.js`命令编译运行，正确使用 file_path。

**参考资料:**[https://nodejs . org/API/fs . html # fs _ stats _ rdev](https://nodejs.org/api/fs.html#fs_stats_rdev)