# Node.js stats.atime 属性

> 原文:[https://www.geeksforgeeks.org/node-js-stats-atime-property/](https://www.geeksforgeeks.org/node-js-stats-atime-property/)

**stats.atime** 属性是 fs 的一个内置应用编程接口。Stats 类用于获取文件上次被访问的时间和日期。

**语法:**

```js
stats.atime;
```

**参数:**属性没有任何参数。

**返回值:**返回一个日期，代表文件上次被访问的时间和日期。

以下示例说明了 stats.atime 属性在 Node.js:
**中的使用示例 1:**

```js
// Node.js program to demonstrate the   
// stats.atime Property

// Accessing fs module
const fs = require('fs');

// Calling fs.Stats stats.atime
// using stat
fs.stat('./', (err, stats) => {
    if (err) throw err;

    // The time and date when 
    // the file is last accessed 
    console.log("Using stat: " + stats.atime);
});

// Using lstat
fs.lstat('./filename.txt', (err, stats) => {
    if (err) throw err;

    // The time and date when the
    // file is last accessed 
    console.log("Using lstat: " + stats.atime);
});
```

**输出:**

```js
Using stat: Sun Jun 21 2020 00:54:20 GMT+0530 (India Standard Time)
Using lstat: Sun Jun 21 2020 01:00:52 GMT+0530 (India Standard Time)

```

**例 2:**

```js
// Node.js program to demonstrate the   
// stats.atime Property

// Accessing fs module
const fs = require('fs').promises;

// Calling fs.Stats stats.atime
(async () => {
    const stats = await fs.stat('./filename.txt');

    // The date and time when the 
    // file is last accessed 
    console.log("Using stat synchronous: "
                + stats.atime);
})().catch(console.error)
```

**输出:**

```js
Using stat synchronous: Sun Jun 21 2020 01:00:52 GMT+0530
                                    (India Standard Time)

```

**注意:**以上程序使用`node filename.js`命令编译运行，正确使用 file_path。

**参考资料:**[https://nodejs . org/API/fs . html # fs _ stats _ atime](https://nodejs.org/api/fs.html#fs_stats_atime)