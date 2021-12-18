# 来自 fs 的 Node.js stats.isBlockDevice()方法。统计等级

> 原文:[https://www . geesforgeks . org/node-js-stats-is blockdevice-method-from-fs-stats-class/](https://www.geeksforgeeks.org/node-js-stats-isblockdevice-method-from-fs-stats-class/)

**stats.isBlockDevice()方法**是 fs 内置的应用编程接口。用于检查文件系统是否。Stats 对象是否属于块设备。

**语法:**

```js
stats.isBlockDevice();
```

**参数:**此方法不接受任何参数。

**返回值:**该方法返回一个布尔值，即 fs 为真。Stats 对象描述块设备，否则为 false。

下面的例子说明了 stats.isBlockDevice()方法在 Node.js 中的使用:

**例 1:**

```js
// Node.js program to demonstrate the 
// stats.isBlockDevice() method

// Accessing fs module
const fs = require('fs');

// Calling fs.Stats isBlockDevice()
fs.stat('./filename.txt', (err, stats) => {
    if (err) throw err;

    // console.log(`stats: ${JSON.stringify(stats)}`);
    console.log(stats.isBlockDevice());
});
```

**输出:**

```js
false

```

**例 2:**

```js
// Node.js program to demonstrate the 
// stats.isBlockDevice() method

// Accessing fs module
const fs = require('fs');

// Calling fs.Stats isBlockDevice() method
fs.stat('./filename.txt', (err, stats) => {
    if (err) throw err;

    // console.log(
    //  `stats: ${JSON.stringify(stats)}`);
    if (stats.isBlockDevice()) {
        console.log("fs.Stats describes a "
            + "block device");
    } else {
        console.log("fs.Stats does not "
            + "describe a block device");
    }
});
```

**输出:**

```js
fs.Stats does not describe a block device

```

**注意:**以上程序使用`node filename.js`命令编译运行，正确使用 file_path。

**参考资料:**[https://nodejs . org/API/fs . html # fs _ stats _ is lockevie](https://nodejs.org/api/fs.html#fs_stats_isblockdevice)