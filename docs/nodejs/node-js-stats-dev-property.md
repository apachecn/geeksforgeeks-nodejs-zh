# Node.js stats.dev 属性

> 原文:[https://www.geeksforgeeks.org/node-js-stats-dev-property/](https://www.geeksforgeeks.org/node-js-stats-dev-property/)

**stats.dev** 属性是 fs 的一个内置应用编程接口。Stats 类用于获取文件所在设备的数字(number / bigint)标识。

**语法:**

```js
stats.dev;
```

**参数:**该属性不接受任何参数。

**返回值:**返回一个数字或 BigInt 值，代表文件所在设备的标识。

下面的例子说明了 stats.dev 属性在 Node.js 中的使用:

**例 1:**

```js
// Node.js program to demonstrate the   
// stats.dev Property

// Accessing fs module
const fs = require('fs');

// Calling fs.Stats stats.dev
// using stat for file
fs.stat('./filename.txt', (err, stats) => {
    if (err) throw err;
    console.log("using stat: the numeric "
        + "identity of the device is  "
        + stats.dev);
});

//using lstat for file
fs.lstat('./filename.txt', (err, stats) => {
    if (err) throw err;
    console.log("using lstat: the numeric "
        + "identity of the device is  "
        + stats.dev);
});
//using stat for directory
fs.stat('./', (err, stats) => {
    if (err) throw err;
    console.log("using stat: the numeric "
        + "identity of the device is  " 
        + stats.dev);
});

//using lstat for directory
fs.lstat('./', (err, stats) => {
    if (err) throw err;
    console.log("using lstat: the numeric "
        + "identity of the device is  " 
        + stats.dev);
});
```

**输出:**

```js
using stat: the numeric identity of the device is  891323748
using lstat: the numeric identity of the device is  891323748
using stat: the numeric identity of the device is  891323748
using lstat: the numeric identity of the device is  891323748

```

**例 2:**

```js
// Node.js program to demonstrate the   
// stats.dev Property

// Accessing fs module
const fs = require('fs').promises;

// Calling stats.dev property from
// fs.Stats class
(async () => {
    const stats = await fs.stat(
            './fs_stat_dev.txt');

    //using stat synchronous
    console.log("The numeric identity "
        + "of the device is  " + stats.dev);
})().catch(console.error)
```

**输出:**

```js
The numeric identity of the device is  891323748

```

**注意:**以上程序使用`node filename.js`命令编译运行，正确使用 file_path。

**参考资料:**[https://nodejs . org/API/fs . html # fs _ stats _ dev](https://nodejs.org/api/fs.html#fs_stats_dev)