# Node.js fs。lchownSync()方法

> 原文:[https://www.geeksforgeeks.org/node-js-fs-lchownsync-method/](https://www.geeksforgeeks.org/node-js-fs-lchownsync-method/)

**fs.lchownSync()方法**用于同步更改给定路径的所有者和组，但是，如果路径是一个，它不尊重符号链接，这与 fs.chownSync()方法不同，后者不将链接引用到它们的路径。

该功能接受用户 id 和组 id，可用于设置各自的所有者和组。它不返回任何东西。

**语法:**

```js
fs.lchownSync( fd, uid, gid )
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **[FD:** is an integer, which indicates that the file descriptors of the owner and group files need to be changed.
*   **uid:** is a number representing the user id corresponding to the owner to be set.
*   **Gid:** is a number representing the group ID corresponding to the group to be set.

下面的例子说明了 Node.js 中的 **fs.lchownSync()方法**:

**示例 1:** 此示例显示了使用 lchownSync()方法设置所有者和组。

```js
// Node.js program to demonstrate the
// fs.lchownSync() method

// Import the filesystem module
const fs = require('fs');

let filepath = "example_file.txt";
let symlinkpath = "symlinkFile";

// Create a symlink to the file
fs.symlinkSync(filepath, symlinkpath);

// Set the owner and group of the symbolic
// link to a new one
// New owner is "geeksforgeeks" with user id 1200
// New group is "editor" with group id 1201
fs.lchownSync(symlinkpath, 1200, 1201);
console.log("Given uid and gid set successfully");
```

**运行代码前:**

```js
xubuntu@xubuntu: ~/Desktop/fs-lchownSync$ ls -l
total 4
-rw-rw--w- 1 xubuntu xubuntu 4 Apr 26 05:10 example_file.txt
-rw-rw-r-- 1 xubuntu xubuntu 290 Apr 26 05:15 index.js

```

**代码输出:**

```js
Given uid and gid set successfully

```

**运行代码后:**

```js
xubuntu@xubuntu: ~/Desktop/fs-lchownSync$ ls -l
total 4
-rw-rw--w- 1 xubuntu xubuntu 4 Apr 26 05:10 example_file.txt
-rw-rw-r-- 1 xubuntu xubuntu 290 Apr 26 05:15 index.js
lrwxrwxrwx 1 geeksforgeeks editor 16 Apr 26 09:15 symlinkFile -> example_file.txt

```

**示例 2:** 此示例显示了 chownSync()和 lchownSync()在取消符号链接引用方面的比较。

```js
// Node.js program to demonstrate the
// fs.lchownSync() method

// Import the filesystem module
const fs = require('fs');

let filepath = "example_file.txt";
let symlinkpath1 = "symlinkFile1";
let symlinkpath2 = "symlinkFile2";

// Create two symlinks to the file
fs.symlinkSync(filepath, symlinkpath1);
fs.symlinkSync(filepath, symlinkpath2);

// Use lchownSync() on the first symlink
// New owner is "geeksforgeeks" with user id 1200
// New group is "owner" with group id 998
fs.lchownSync(symlinkpath1, 1200, 998);
console.log("lchownSync: uid and gid set successfully");

// Use chownSync() on the second symLink
// New owner is "sam" with user id 1100
// New group is "editor" with group id 1201
fs.chownSync(symlinkpath2, 1100, 1201);
console.log("chownSync: uid and gid set successfully");
```

**运行代码前:**

```js
xubuntu@xubuntu: ~/Desktop/fs-lchownSync$ ls -l
total 4
-rw-rw--w- 1 xubuntu xubuntu 6 Apr 26 09:15 example_file.txt
-rw-rw-r-- 1 xubuntu xubuntu 777 Apr 26 09:16 index.js

```

**代码输出:**

```js
lchownSync: uid and gid set successfully
chownSync: uid and gid set successfully

```

**运行代码后:**

```js
xubuntu@xubuntu: ~/Desktop/fs-lchownSync$ ls -l
total 4
-rw-rw--w- 1 sam editor 6 Apr 26 09:15 example_file.txt
-rw-rw-r-- 1 xubuntu xubuntu 777 Apr 26 09:16 index.js
lrwxrwxrwx 1 geeksforgeeks owner 16 Apr 26 09:15 symlinkFile1 -> example_file.txt
lrwxrwxrwx 1 root root 16 Apr 26 09:15 symlinkFile2 -> example_file.txt

```

**参考:**[https://nodejs . org/API/fs . html # fs _ fs _ lcownssync _ path _ uid _ GID](https://nodejs.org/api/fs.html#fs_fs_lchownsync_path_uid_gid)