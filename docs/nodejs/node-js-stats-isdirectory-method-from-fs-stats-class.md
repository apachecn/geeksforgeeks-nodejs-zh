# 来自 fs 的 Node.js stats.isDirectory()方法。统计等级

> 原文:[https://www . geesforgeks . org/node-js-stats-is directory-method-from-fs-stats-class/](https://www.geeksforgeeks.org/node-js-stats-isdirectory-method-from-fs-stats-class/)

**stats.isDirectory()方法**是 fs 的内置应用编程接口。用于检查文件系统是否。Stats 对象是否描述文件系统目录。

**语法:**

```js
stats.isDirectory();
```

**参数:**此方法不接受任何参数。

**Return:** 这个方法返回一个布尔值，如果是 fs 则为真。Stats 对象描述一个目录，否则为 false。

下面的例子说明了 stats.isDirectory()方法在 Node.js 中的使用:

**例 1:**

```js
// Node.js program to demonstrate the   
// stats.isDirectory() Method

// Accessing fs module
const fs = require('fs');

// Calling fs.Stats isDirectory()
fs.stat('./filename.txt', (err, stats) => {
    if (err) throw err;
    // console.log(`stats: ${JSON.stringify(stats)}`);
    console.log(stats.isDirectory());
});

fs.stat('./filename.txt', (err, stats) => {
    if (err) throw err;
    // console.log(`stats: ${JSON.stringify(stats)}`);

    if (stats.isDirectory()) {
        console.log("fs.Stats describes a "
            + "file system directory");
    } else {
        console.log("fs.Stats does not "
        + "describe a file system directory");
    }
});
```

**输出:**

```js
false
fs.Stats does not describe a file system directory

```

**例 2:**

```js
// Node.js program to demonstrate the   
// stats.isDirectory() Method

// Accessing fs module
const fs = require('fs');

// calling fs.Stats isDirectory()
fs.stat('./', (err, stats) => {
    if (err) throw err;
    // console.log(`stats: ${JSON.stringify(stats)}`);
    console.log(stats.isDirectory());
});

fs.stat('./', (err, stats) => {
    if (err) throw err;
    // console.log(`stats: ${JSON.stringify(stats)}`);
    if (stats.isDirectory()) {
        console.log("fs.Stats describes a "
            + "file system directory");
    } else {
        console.log("fs.Stats does not "
        + "describe a file system directory");
    }
});
```

**输出:**

```js
true
fs.Stats describes a file system directory

```

**注意:**以上程序使用`node filename.js`命令编译运行，正确使用 file_path。

**参考:**T2】https://nodejs.org/api/fs.html#fs_stats_isdirectory