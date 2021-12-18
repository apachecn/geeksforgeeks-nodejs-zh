# Node.js fs.fchown()函数

> 原文:[https://www.geeksforgeeks.org/node-js-fs-fchown-function/](https://www.geeksforgeeks.org/node-js-fs-fchown-function/)

**fs.fchown()方法**用于更改给定文件描述符的所有者和组。该功能接受用户 id 和组 id，可用于设置各自的所有者和组。它有一个回调函数，如果函数失败，它会返回任何可能出现的错误。

**语法:**

```
fs.fchown( fd, uid, gid, callback )
```

**参数:**该方法接受上述四个参数，如下所述:

*   **FD:** is an integer, which indicates that the file descriptors of the owner and group files need to be changed.
*   **uid:** is a number representing the user id corresponding to the owner to be set.
*   **Gid:** is a number representing the group ID corresponding to the group to be set.
*   **Callback:** is a function that will be called when the method is executed.
    *   **err:** If the method fails, this error will be thrown.

下面的例子说明了 Node.js 中的 **fs.fchown()方法**:

**示例 1:** 本示例显示了所有者的设置。

```
// Node.js program to demonstrate the
// fs.fchown() method

// Import the filesystem module
const fs = require('fs');

let fd = fs.openSync("example_file.txt", "r");

// Set the owner to a new one keeping the group same
// New owner is "geek" with user id 1027
// The old group is "xubuntu" with group id 999
fs.fchown(fd, 1027, 999, (error) => {
  if (error)
    console.log("Error Code:", error);
  else
    console.log("uid and gid set successfully");
});
```

**运行代码前:**

```
xubuntu@xubuntu: ~/Desktop/fs-fchown$ ls -l
total 8
-rw-rw--w- 1 xubuntu xubuntu 4 Apr 26 02:08 example_file.txt
-rw-rw-r-- 1 xubuntu xubuntu 290 Apr 26 02:08 index.js

```

**代码输出:**

```
Given uid and gid set successfully

```

**运行代码后:**

```
xubuntu@xubuntu: ~/Desktop/fs-fchown$ ls -l
total 8
-rw-rw--w- 1 geek xubuntu 4 Apr 26 02:08 example_file.txt
-rw-rw-r-- 1 xubuntu xubuntu 290 Apr 26 02:08 index.js

```

**示例 2:** 此示例显示了组的设置。

```
// Node.js program to demonstrate the
// fs.fchown() method

// Import the filesystem module
const fs = require('fs');

let fd = fs.openSync("example_file.txt", "r");

// Set the owner to a new one keeping the group same
// New owner is "raj" with user id 1025
// New group is "author" with group id 1031
fs.fchown(fd, 1025, 1031, (error) => {
  if (error)
    console.log("Error Code:", error);
  else
    console.log("uid and gid set successfully");
});
```

**运行代码前:**

```
xubuntu@xubuntu: ~/Desktop/fs-fchown$ ls -l
total 8
-rw-rw--w- 1 xubuntu xubuntu 4 Apr 26 02:08 example_file.txt
-rw-rw-r-- 1 xubuntu xubuntu 290 Apr 26 02:08 index.js

```

**代码输出:**

```
Given uid and gid set successfully

```

**运行代码后:**

```
xubuntu@xubuntu: ~/Desktop/fs-fchown$ ls -l
total 8
-rw-rw--w- 1 raj author 4 Apr 26 02:08 example_file.txt
-rw-rw-r-- 1 xubuntu xubuntu 290 Apr 26 02:08 index.js

```

**参考:**[https://nodejs . org/API/fs . html # fs _ fs _ fchown _ FD _ uid _ GID _ callback](https://nodejs.org/api/fs.html#fs_fs_fchown_fd_uid_gid_callback)