# Node.js stats.atimeNs 属性

> 原文:[https://www . geesforgeks . org/node-js-stats-atimens-property/](https://www.geeksforgeeks.org/node-js-stats-atimens-property/)

属性是 fs 的一个内置应用程序编程接口。Stats 类用于获取自 POSIX 纪元以来最后一次访问文件时的时间戳，以纳秒表示。

**语法:**

```js
stats.atimeNs;
```

**参数:**该属性没有任何参数，但是在创建 stats 对象期间{bigint:true}必须作为选项传递。

**返回值:**它返回一个数字或 BigInt 值，表示自 POSIX 纪元以来最后一次访问文件时的时间戳，用纳秒表示。

以下示例说明了 stats.atimeNs 属性在 Node.js 中的使用:
**示例 1:**

```js
// Node.js program to demonstrate the   
// stats.atimeNs property

// Accessing fs module
const fs = require('fs');

// Calling fs.Stats stats.atimeNs
// using stat
fs.lstat('./', { bigint: true }, (err, stats) => {
    if (err) throw err;

    // The timestamp when the file
    // is last accessed (in NS)
    console.log("Using stat: " + stats.atimeNs);
});

// Using lstat
fs.lstat('./filename.txt',
    { bigint: true }, (err, stats) => {
        if (err) throw err;

        // The timestamp when the file is
        // last accessed (in NS) 
        console.log("Using lstat: " + stats.atimeNs);
    });
```

**输出:**

```js
Using stat: 1592654526560650
Using lstat: 1592664546730291

```

**例 2:**

```js
// Node.js program to demonstrate the   
// stats.atimeNs property

// Accessing fs module
const fs = require('fs').promises;

// Calling fs.Stats stats.atimeNs
(async() => {
  const stats = await fs.stat(
        './filename.txt', {BigInt:true});

  // The timestamp when the file 
  // is last accessed (in NS)
  console.log("Using stat synchronous: "
            + stats.atimeNs);
})().catch(console.error)
```

**输出:**

```js
Using stat synchronous: 1592664546730291

```

**注意:**以上程序使用`node filename.js`命令编译运行，正确使用 file_path。

**参考资料:**[https://nodejs . org/API/fs . html # fs _ stats _ atimen](https://nodejs.org/api/fs.html#fs_stats_atimens)