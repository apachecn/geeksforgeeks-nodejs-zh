# Node.js | fs。fchownSync()方法

> 原文:[https://www.geeksforgeeks.org/node-js-fs-fchownsync-method/](https://www.geeksforgeeks.org/node-js-fs-fchownsync-method/)

**fs.fchownSync()方法**用于同步更改给定文件描述符的所有者和组。该功能接受用户 id 和组 id，可用于设置各自的所有者和组。它不返回任何东西。

**语法:**

```
fs.fchownSync( fd, uid, gid )
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **[FD:** is an integer, which indicates that the file descriptors of the owner and group files need to be changed.
*   **uid:** is a number representing the user id corresponding to the owner to be set.
*   **Gid:** is a number representing the group ID corresponding to the group to be set.

下面的例子说明了 Node.js 中的 **fs.fchownSync()方法**:

**示例 1:** 本示例显示了所有者的设置。

```
// Node.js program to demonstrate the
// fs.fchownSync() method

// Import the filesystem module
const fs = require('fs');

// Get the file descriptor for the file
let fd = fs.openSync("example_file.txt", "r");

// Set the owner to a new one keeping the group same
// New owner is "geeksforgeeks" with user id 1010
// The old group is "xubuntu" with group id 999
fs.fchownSync(fd, 1010, 999);
console.log("uid and gid set successfully");
```

**运行代码前:**

```
xubuntu@xubuntu: ~/Desktop/fs-fchownSync$ ls -l
total 8
-rw-rw--w- 1 xubuntu xubuntu 4 Apr 22 09:10 example_file.txt
-rw-rw-r-- 1 xubuntu xubuntu 290 Apr 22 09:15 index.js

```

**代码输出:**

```
Given uid and gid set successfully

```

**运行代码后:**

```
xubuntu@xubuntu: ~/Desktop/fs-fchownSync$ ls -l
total 8
-rw-rw--w- 1 geeksforgeeks xubuntu 4 Apr 22 09:10 example_file.txt
-rw-rw-r-- 1 xubuntu xubuntu 290 Apr 22 09:15 index.js

```

**示例 2:** 此示例显示了组的设置。

```
// Node.js program to demonstrate the
// fs.fchownSync() method

// Import the filesystem module
const fs = require('fs');

// Get the file descriptor for the file
let fd = fs.openSync("example_file.txt", "r");

// Set the group to a new one keeping the owner same
// The old owner is "xubuntu" with user id 999
// New group is "author" with group id 1015
fs.fchownSync(fd, 999, 1015);
console.log("uid and gid set successfully");
```

**运行代码前:**

```
xubuntu@xubuntu: ~/Desktop/fs-fchownSync$ ls -l
total 8
-rw-rw--w- 1 xubuntu xubuntu 4 Apr 22 09:10 example_file.txt
-rw-rw-r-- 1 xubuntu xubuntu 290 Apr 22 09:15 index.js

```

**代码输出:**

```
Given uid and gid set successfully

```

**运行代码后:**

```
xubuntu@xubuntu: ~/Desktop/fs-fchownSync$ ls -l
total 8
-rw-rw--w- 1 xubuntu author 4 Apr 22 09:10 example_file.txt
-rw-rw-r-- 1 xubuntu xubuntu 290 Apr 22 09:15 index.js

```

**参考:**[https://nodejs . org/API/fs . html # fs _ fs _ fchowsynnc _ FD _ uid _ GID](https://nodejs.org/api/fs.html#fs_fs_fchownsync_fd_uid_gid)