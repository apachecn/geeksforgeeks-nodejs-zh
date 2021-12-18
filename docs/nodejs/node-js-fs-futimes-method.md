# node . js fs . fut times()方法

> 原文:[https://www.geeksforgeeks.org/node-js-fs-futimes-method/](https://www.geeksforgeeks.org/node-js-fs-futimes-method/)

**fs.futimes()方法**用于异步更改给定文件描述符的修改和访问时间戳。可以使用数字、字符串或日期对象来指定时间戳。如果时间戳无法转换为正确的数字，或者是 NaN、Infinity 或-Infinity，则会引发错误。

**语法:**

```js
fs.futimes( fd, atime, mtime, callback )
```

**参数:**该方法接受上述四个参数，描述如下:

*   **FD:** It is an integer that represents the file descriptor of the file whose timestamp must be changed.
*   **atime:** It means that the new access timestamp to be set is a number, string or Date object.
*   **Time:** It means that the new modification timestamp to be set is a number, string or Date object.
*   **Callback:** is a function that will be called when the method is executed.
    *   **err:** If the method fails, this error will be thrown.

下面的例子说明了 Node.js 中的 **fs.futimes()方法**:

**例 1:**

```js
// Node.js program to demonstrate the
// fs.futimes() method

// Import the filesystem module
const fs = require('fs');

// Get the file descriptor of the file
const fd = fs.openSync("example_file.txt", "r+");

console.log("Details before changing time:");

// Get the stats object of the file
prevStats = fs.statSync("example_file.txt");

// Access the modified and access time of the file
console.log("Modification Time:", prevStats.mtime);
console.log("Access Time:", prevStats.atime);

// Get the current time to change the timestamps
let changedModifiedTime = new Date();
let changedAccessTime = new Date();

// Use the futimes() function to assign
// the new timestamps to the file descriptor
fs.futimes(fd, changedAccessTime, changedModifiedTime, () => {
  // Get the stats object of the file
  console.log("\nDetails after changing time:");

  // Get the stats object of the file
  changedStats = fs.statSync("example_file.txt");

  // Access the changed modified and access time of the file
  console.log("Changed Modification Time:", changedStats.mtime);
  console.log("Changed Access Time:", changedStats.atime);
});
```

**输出:**

```js
Details before changing time:
Modification Time: 2020-05-25T15:59:10.807Z
Access Time: 2020-05-25T15:59:10.807Z

Details after changing time:
Changed Modification Time: 2020-05-25T16:01:34.915Z
Changed Access Time: 2020-05-25T16:01:34.915Z

```

**例 2:**

```js
// Node.js program to demonstrate the
// fs.futimes() method

// Import the filesystem module
const fs = require('fs');

// Get the file descriptor of the file
const fd = fs.openSync("example_file.txt", "r+");

console.log("Details before changing time:");

// Get the stats object of the file
prevStats = fs.statSync("example_file.txt");

// Access the modified and access time of the file
console.log("Modification Time:", prevStats.mtime);
console.log("Access Time:", prevStats.atime);

// Get the current time to change the timestamps
let changedModifiedTime = new Date("April 01, 2019 04:13:20");
let changedAccessTime = new Date("April 12, 2019 08:12:40");

// Use the futimes() function to assign
// the new timestamps to the file descriptor
fs.futimes(fd, changedAccessTime, changedModifiedTime, () => {
  // Get the stats object of the file
  console.log("\nDetails after changing time:");

  // Get the stats object of the file
  changedStats = fs.statSync("example_file.txt");

  // Access the changed modified and access time of the file
  console.log("Changed Modification Time:", changedStats.mtime);
  console.log("Changed Access Time:", changedStats.atime);
});
```

**输出:**

```js
Details before changing time:
Modification Time: 2020-05-25T16:06:28.977Z
Access Time: 2020-05-25T16:06:28.977Z

Details after changing time:
Changed Modification Time: 2019-03-31T22:43:20.000Z
Changed Access Time: 2019-04-12T02:42:40.000Z

```

**参考:**[https://nodejs . org/API/fs . html # fs _ fs _ futimes _ FD _ atime _ mtime _ callback](https://nodejs.org/api/fs.html#fs_fs_futimes_fd_atime_mtime_callback)