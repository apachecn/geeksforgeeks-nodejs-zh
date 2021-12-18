# Node.js | fs.chownSync()方法

> 原文:[https://www.geeksforgeeks.org/node-js-fs-chownsync-method/](https://www.geeksforgeeks.org/node-js-fs-chownsync-method/)

**fs.chownSync()方法**用于同步更改给定路径的所有者和组。该功能接受用户 id 和组 id，可用于设置各自的所有者和组。它不返回任何东西。

**语法:**

```js
fs.chownSync( path, uid, gid )
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **Path:** It is a string, buffer or web address that indicates the path of the file that the owner and group must change.
*   **uid:** is a number representing the user id corresponding to the owner to be set.
*   **Gid:** is a number representing the group ID corresponding to the group to be set.

下面的例子说明了 Node.js 中的 **fs.chownSync()方法**:

**示例 1:** 本示例显示了所有者的设置。

```js
// Node.js program to demonstrate the
// fs.chownSync() method

// Import the filesystem module
const fs = require('fs');

let filepath = "example_file.txt";

// Set the owner to a new one keeping the group same
// New owner is "geeksforgeeks" with user id 1100
// The old group is "xubuntu" with group id 999
fs.chownSync(filepath, 1100, 999);
console.log("Given uid and gid set successfully");
```

**运行代码前:**

```js
xubuntu@xubuntu: ~/Desktop/fs-chownSync$ ls -l
total 8
-rw-rw--w- 1 xubuntu xubuntu 4 Apr 23 09:08 example_file.txt
-rw-rw-r-- 1 xubuntu xubuntu 290 Apr 23 09:08 index.js

```

**代码输出:**

```js
Given uid and gid set successfully

```

**运行代码后:**

```js
xubuntu@xubuntu: ~/Desktop/fs-chownSync$ ls -l
total 8
-rw-rw--w- 1 geeksforgeeks xubuntu 4 Apr 23 09:08 example_file.txt
-rw-rw-r-- 1 xubuntu xubuntu 290 Apr 23 09:08 index.js

```

**示例 2:** 此示例显示了组的设置。

```js
// Node.js program to demonstrate the
// fs.chownSync() method

// Import the filesystem module
const fs = require('fs');

let filepath = "example_file.txt";

// Set the group to a new one keeping the owner same
// New group is "editor" with group id 1201
fs.chownSync(filepath, 999, 1201);
console.log("Given uid and gid set successfully");
```

**运行代码前:**

```js
xubuntu@xubuntu: ~/Desktop/fs-chownSync$ ls -l
total 8
-rw-rw--w- 1 xubuntu xubuntu 4 Apr 23 09:08 example_file.txt
-rw-rw-r-- 1 xubuntu xubuntu 290 Apr 23 09:08 index.js

```

**代码输出:**

```js
Given uid and gid set successfully

```

**运行代码后:**

```js
xubuntu@xubuntu: ~/Desktop/fs-chownSync$ ls -l
total 8
-rw-rw--w- 1 xubuntu editor 4 Apr 23 09:08 example_file.txt
-rw-rw-r-- 1 xubuntu xubuntu 290 Apr 23 09:08 index.js

```

**参考:**T2】https://nodejs.org/api/fs.html#fs_fs_chownsync_path_uid_gid