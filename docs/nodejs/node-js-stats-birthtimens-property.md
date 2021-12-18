# Node.js stats.birthtimeNs 属性

> 原文:[https://www . geesforgeks . org/node-js-stats-birthtimens-property/](https://www.geeksforgeeks.org/node-js-stats-birthtimens-property/)

属性是 fs 的一个内置应用程序编程接口。Stats 类用于获取文件创建时的时间戳，因为 POSIX 纪元以毫秒表示。

**语法:**

```js
stats.birthtimeNs;
```

**参数:**该属性没有任何参数，但是在创建 stats 对象期间{bigint:true}必须作为选项传递。

**返回值:**它返回一个数字或 BigInt 值，表示自 POSIX 纪元以来创建文件时的时间戳，以毫秒表示。

下面的例子说明了 stats.birthtimeNs 属性在 Node.js 中的使用:

**例 1:**

```js
// Node.js program to demonstrate the   
// stats.birthtimeNs property

// Accessing fs module
const fs = require('fs');

// Calling fs.Stats stats.birthtimeNs
// using stat
fs.stat('./', { bigint: true }, (err, stats) => {
    if (err) throw err;

    // The timestamp when the file is created (in NS)    
    console.log("Using stat: " + stats.birthtimeNs);
});

// Using lstat
fs.lstat('./filename.txt',
    { bigint: true }, (err, stats) => {
        if (err) throw err;

        // The timestamp when the file
        // is created (in NS) 
        console.log("Using lstat: " 
              + stats.birthtimeNs);
    });
```

**输出:**

```js
Using stat: 1589375311991945.3
Using lstat: 1592667100334387

```

**例 2:**

```js
// Node.js program to demonstrate the   
// stats.birthtimeNs property

//accessing fs module
const fs = require('fs').promises;

// Calling stats.birthtimeNs property
// from fs.Stats class
(async () => {
    const stats = await fs.stat(
        './filename.txt', { bigint: true });

    // The timestamp when the file
    // is created (in NS) 
    console.log("Using stat synchronous: "
            + stats.birthtimeNs);
})().catch(console.error)
```

**输出:**

```js
Using stat synchronous: 1592667100334387

```

**注意:**以上程序使用`node filename.js`命令编译运行，正确使用 file_path。

**参考:**T2】https://nodejs.org/api/fs.html#fs_stats_birthtimens