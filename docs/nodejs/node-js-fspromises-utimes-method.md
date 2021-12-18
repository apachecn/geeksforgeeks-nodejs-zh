# Node.js fsPromises.utimes()方法

> 原文:[https://www . geesforgeks . org/node-js-fs promises-utimes-method/](https://www.geeksforgeeks.org/node-js-fspromises-utimes-method/)

**fsPromises.utimes()** 方法用于异步更改文件的修改和访问时间戳。可以使用数字、字符串或日期对象来指定时间戳。如果时间戳无法转换为正确的数字，或者是 NaN、Infinity 或-Infinity，则会引发错误。

它会更改路径引用的对象的文件系统时间戳，然后在成功时解析无参数的承诺。

**语法:**

```js
fsPromises.utimes( path, atime, mtime )
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **Path:** It is a string indicating the path of the file whose timestamp must be changed.
*   **atime:** It means that the new access timestamp to be set is a number, string or Date object.
*   **Time:** It means that the new modification timestamp to be set is a number, string or Date object.

第一次和第二次*争论遵循以下规则:*

1.  值可以是代表 Unix 纪元时间、日期的数字，也可以是类似“123456789.0”的数字字符串。
2.  如果该值无法转换为数字，或者是 NaN、Infinity 或-Infinity，将引发错误。

**示例:**此示例说明 Node.js 中的 **fsPromises.utimes()** 方法，创建一个**示例 _gfg.txt** 文件进行输入。

**文件名:**

```js
// Node.js program to demonstrate the 
// fsPromises.utimes() method 

// Import the filesystem module 
const fs = require('fs');
const fsPromises = require('fs').promises;

console.log("Details before changing time:");

// Get the stats object of the file 
prevStats = fs.statSync("example_gfg.txt");

// Access the modified and access time of the file 
console.log("Modification Time:", prevStats.mtime);
console.log("Access Time:", prevStats.atime);

// Get the current time to change the timestamps 
let newModifiedTime = new Date();
let newAccessTime = new Date();

// Use the utimes() function to assign 
// the new timestamps 
fsPromises.utimes("example_file.txt", 
        newAccessTime, newModifiedTime);

// Get the stats object of the file 
console.log("\nDetails after changing time:");

// Get the stats object of the file 
changedStats = fs.statSync("example_gfg.txt");

// Access the changed modified and 
// access time of the file 
console.log("Changed Modification Time:", 
                changedStats.mtime);

console.log("Changed Access Time:", 
                changedStats.atime);
```

**运行该程序的步骤:**使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
Details before changing time:
Modification Time: 2020-06-11T17:25:51.136Z
Access Time: 2020-06-11T16:50:51.223Z

Details after changing time:
Changed Modification Time: 2020-06-11T17:25:51.136Z
Changed Access Time: 2020-06-11T16:50:51.223Z

```

**参考:**[https://nodejs . org/API/fs . html # fs _ fspromises _ utimes _ path _ atime _ mtime](https://nodejs.org/api/fs.html#fs_fspromises_utimes_path_atime_mtime)