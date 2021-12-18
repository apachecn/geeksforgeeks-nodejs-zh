# 节点. js stats.mode 属性来自 fs。统计等级

> 原文:[https://www . geesforgeks . org/node-js-stats-mode-property-from-fs-stats-class/](https://www.geeksforgeeks.org/node-js-stats-mode-property-from-fs-stats-class/)

**stats.mode 属性**是 fs 的内置应用编程接口。Stats 类，用于获取文件类型和模式作为位字段。

**语法:**

```js
stats.mode;
```

**返回值:**它返回一个数字或 BigInt 值，表示描述文件类型和模式的位字段。

下面的例子说明了 stats.mode 在 Node.js 中的使用:

**例 1:**

```js
// Node.js program to demonstrate the   
// stats.mode property

// Accessing fs module
const fs = require('fs');

// Calling fs.Stats stats.mode for files
// using stat
fs.stat('./filename.txt', (err, stats) => {
    if (err) throw err;
    console.log("using stat: the type and "
        + "mode bit-field of the file is " 
        + stats.mode);
});

// Using lstat
fs.lstat('./filename.txt', (err, stats) => {
    if (err) throw err;
    console.log("using lstat: the type and "
        + "mode bit-field of the file is " 
        + stats.mode);
});

// For directories
// Using stat
fs.stat('./', (err, stats) => {
    if (err) throw err;
    console.log("using stat: the type and "
        + "mode bit-field of the file is " 
        + stats.mode);
});

// Using lstat
fs.lstat('./', (err, stats) => {
    if (err) throw err;
    console.log("using lstat: the type and "
        + "mode bit-field of the file is " 
        + stats.mode);
});
```

**输出:**

```js
using stat: the type and mode bit-field of the file is  33206
using lstat: the type and mode bit-field of the file is  33206
using stat: the type and mode bit-field of the file is  16822
using lstat: the type and mode bit-field of the file is  16822

```

**例 2:**

```js
// Node.js program to demonstrate the   
// stats.mode property

// Accessing fs module
const fs = require('fs').promises;

// Calling fs.Stats stats.mode
(async() => {
    const stats = await fs.stat('./filename.txt');
    console.log("using stat synchronous: the type "
        + "and mode bit-field of the file is "
        + stats.mode);
})().catch(console.error)
```

**输出:**

```js
(node:9448) ExperimentalWarning: The fs.promises API
is experimental 
using stat synchronous: the type and mode bit-field 
of the file is  33206

```

**注意:**以上程序使用`node filename.js`命令编译运行，正确使用 file_path。

**参考:**[https://nodejs . org/API/fs . html # fs _ stats _ mode](https://nodejs.org/api/fs.html#fs_stats_mode)