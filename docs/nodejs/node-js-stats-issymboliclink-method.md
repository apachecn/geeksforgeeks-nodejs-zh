# node . js stats . issymbolilink()方法

> 原文:[https://www . geesforgeks . org/node-js-stats-issymboliclin-method/](https://www.geeksforgeeks.org/node-js-stats-issymboliclink-method/)

**stats . issymbolilink()**方法是 fs 内置的应用编程接口。用于检查文件系统是否。Stats 对象描述一个符号链接与否。

**语法:**

```js
stats.isSymbolicLink();
```

**参数:**此方法不接受任何参数。

**Return:** 这个方法返回一个布尔值，如果是 fs 则为真。Stats 对象描述符号链接，否则为 false。

下面的例子说明了 stats.isSymbolicLink()方法在 Node.js 中的使用:

**例 1:**

```js
// Node.js program to demonstrate the   
// stats.isSymbolicLink() Method

// Accessing fs module
const fs = require('fs').promises;

// Accessing fs module
const fs = require('fs');

// Calling fs.Stats isSymbolicLink()
fs.lstat('./filename.lnk', (err, stats) => {
    if (err) throw err;
    if (stats.isSymbolicLink()) {
        console.log("fs.Stats describes "
                    + "a symbolic link");
    } else {
        console.log("fs.Stats does not "
            + "describe a symbolic link");
    }
});
```

**输出:**

```js
fs.Stats does not describe a symbolic link

```

**例 2:**

```js
// Node.js program to demonstrate the   
// stats.isSymbolicLink() Method

// Accessing fs module
const fs = require('fs');

// Calling isSymbolicLink() method from
// fs.Stats class
fs.lstat('./filename.lnk', (err, stats) => {
    if (err) throw err;
    console.log(stats.isSymbolicLink());
});
```

**输出:**

```js
false

```

**注意:**以上程序使用`node filename.js`命令编译运行，正确使用 file_path。在基于 UNIX 的系统中使用符号链接。它将返回 true。

**参考:**T2】https://nodejs.org/api/fs.html#fs_stats_issymboliclink