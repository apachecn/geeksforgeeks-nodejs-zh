# Node.js fs.utimes()方法

> 原文:[https://www.geeksforgeeks.org/node-js-fs-utimes-method/](https://www.geeksforgeeks.org/node-js-fs-utimes-method/)

**fs.utimes()方法**用于异步更改文件的修改和访问时间戳。可以使用数字、字符串或日期对象来指定时间戳。如果时间戳无法转换为正确的数字，或者是 NaN、Infinity 或-Infinity，则会引发错误。

**语法:**

```js
fs.utimes( path, atime, mtime, callback )
```

**参数:**这个方法接受上面提到的和下面描述的四个参数:

*   **Path:** It is a string indicating the path of the file whose timestamp must be changed.
*   **atime:** It means that the new access timestamp to be set is a number, string or Date object.
*   **Time:** It means that the new modification timestamp to be set is a number, string or Date object.
*   **Callback:** is a function that will be called when the method is executed.
    *   **err:** If the method fails, this error will be thrown.

下面的例子说明了 Node.js 中的 **fs.utimes()方法**:

**例 1:**

```js
// Node.js program to demonstrate the
// fs.utimes() method

// Import the filesystem module
const fs = require('fs');

console.log("Details before changing time:");

// Get the stats object of the file
prevStats = fs.statSync("example_file.txt");

// Access the modified and access time of the file
console.log("Modification Time:", prevStats.mtime);
console.log("Access Time:", prevStats.atime);

// Get the current time to change the timestamps
let newModifiedTime = new Date();
let newAccessTime = new Date();

// Use the utimes() function to assign
// the new timestamps
fs.utimes(
  "example_file.txt",
  newAccessTime,
  newModifiedTime,
  () => {
    // Get the stats object of the file
    console.log("\nDetails after changing time:");

    // Get the stats object of the file
    changedStats = fs.statSync("example_file.txt");

    // Access the changed modified and
    // access time of the file
    console.log("Changed Modification Time:",
                         changedStats.mtime);

    console.log("Changed Access Time:", 
                        changedStats.atime);
  }
);
```

**输出:**

```js
Details before changing time:
Modification Time: 2017-01-24T23:41:00.000Z
Access Time: 2018-02-26T00:05:00.000Z

Details after changing time:
Changed Modification Time: 2020-05-25T15:31:08.257Z
Changed Access Time: 2020-05-25T15:31:08.257Z

```

**例 2:**

```js
// Node.js program to demonstrate the
// fs.utimes() method

// Import the filesystem module
const fs = require('fs');

console.log("Details before changing time:");

// Get the stats object of the file
prevStats = fs.statSync("example_file.txt");

// Access the modified and access time of the file
console.log("Modification Time:", prevStats.mtime);
console.log("Access Time:", prevStats.atime);

// Get the current time to change the timestamps
let newModifiedTime = new Date("January 25, 2017 05:11:00");
let newAccessTime = new Date("February 26, 2018 05:35:00");

// Use the utimes() function to assign
// the new timestamps
fs.utimes("example_file.txt", newAccessTime,
                       newModifiedTime, () => {

  // Get the stats object of the file
  console.log("\nDetails after changing time:");

  // Get the stats object of the file
  changedStats = fs.statSync("example_file.txt");

  // Access the changed modified and
  // access time of the file
  console.log("Changed Modification Time:",
                        changedStats.mtime);
  console.log("Changed Access Time:",
                        changedStats.atime);
});
```

**输出:**

```js
Details before changing time:
Modification Time: 2015-12-20T19:42:00.000Z
Access Time: 2020-05-25T15:19:24.250Z

Details after changing time:
Changed Modification Time: 2017-01-24T23:41:00.000Z
Changed Access Time: 2018-02-26T00:05:00.000Z

```

**参考:**[https://nodejs . org/API/fs . html # fs _ fs _ utimes _ path _ atime _ mtime _ callback](https://nodejs.org/api/fs.html#fs_fs_utimes_path_atime_mtime_callback)