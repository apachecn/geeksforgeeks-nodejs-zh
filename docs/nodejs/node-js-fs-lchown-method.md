# Node.js fs。lchown()方法

> 原文:[https://www.geeksforgeeks.org/node-js-fs-lchown-method/](https://www.geeksforgeeks.org/node-js-fs-lchown-method/)

**fs.lchown()方法**用于异步更改给定路径的所有者和组，但是，如果路径是一个，它不尊重符号链接，这与 fs.chown()方法不同，后者不将链接引用到它们的路径。该功能接受用户 id 和组 id，可用于设置各自的所有者和组。它不返回任何东西。

**语法:**

```js
fs.lchown( fd, uid, gid, callback )
```

**参数:**该方法接受上述四个参数，描述如下:

*   **FD:** is an integer, which indicates that the file descriptors of the owner and group files need to be changed.
*   **uid:** is a number representing the user id corresponding to the owner to be set.
*   **Gid:** is a number representing the group ID corresponding to the group to be set.
*   **Callback:** is a function that will be called when the method is executed.
    *   **err:** If the method fails, this error will be thrown.

下面的例子说明了 Node.js 中的 **fs.lchown()方法**:

**示例 1:** 此示例显示了使用 lchown()方法设置所有者和组。

```js
// Node.js program to demonstrate the
// fs.lchown() method

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
fs.lchown(symlinkpath, 1200, 1201, (err) => {
  if (err)
    console.log(err);
  else {
    console.log("Given uid and gid set successfully");
  }
});
```

**运行代码前:**

```js
xubuntu@xubuntu: ~/Desktop/fs-lchown$ ls -l
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
xubuntu@xubuntu: ~/Desktop/fs-lchown$ ls -l
total 4
-rw-rw--w- 1 xubuntu xubuntu 4 Apr 26 05:10 example_file.txt
-rw-rw-r-- 1 xubuntu xubuntu 290 Apr 26 05:15 index.js
lrwxrwxrwx 1 geeksforgeeks editor 16 Apr 26 09:15 symlinkFile -> example_file.txt

```

**示例 2:** 此示例显示了 chown()和 lchown()在取消符号链接引用方面的比较。

```js
// Node.js program to demonstrate the
// fs.lchown() method

// Import the filesystem module
const fs = require('fs');

let filepath = "example_file.txt";
let symlinkpath1 = "symlinkFile1";
let symlinkpath2 = "symlinkFile2";

// Create two symlinks to the file
fs.symlinkSync(filepath, symlinkpath1);
fs.symlinkSync(filepath, symlinkpath2);

// Use lchown() on the first symlink
// New owner is "geeksforgeeks" with user id 1200
// New group is "owner" with group id 1300
fs.lchown(symlinkpath1, 1200, 1300, (err) => {
  if (err)
    console.log(err);
  else {
    console.log("lchownSync: uid and gid set successfully");
  }
});

// Use chown() on the second symlink
// New owner is "max" with user id 1100
// New group is "author" with group id 1202
fs.chown(symlinkpath1, 1100, 1202, (err) => {
  if (err)
    console.log(err);
  else {
    console.log("chownSync: uid and gid set successfully");
  }
});
```

**运行代码前:**

```js
xubuntu@xubuntu: ~/Desktop/fs-lchown$ ls -l
total 4
-rw-rw--w- 1 xubuntu xubuntu 6 Apr 26 09:15 example_file.txt
-rw-rw-r-- 1 xubuntu xubuntu 777 Apr 26 09:16 index.js

```

**代码输出:**

```js
lchown: uid and gid set successfully
chown: uid and gid set successfully

```

**运行代码后:**

```js
xubuntu@xubuntu: ~/Desktop/fs-lchown$ ls -l
total 4
-rw-rw--w- 1 max author 6 Apr 26 09:15 example_file.txt
-rw-rw-r-- 1 xubuntu xubuntu 777 Apr 26 09:16 index.js
lrwxrwxrwx 1 geeksforgeeks owner 16 Apr 26 09:15 symlinkFile1 -> example_file.txt
lrwxrwxrwx 1 root root 16 Apr 26 09:15 symlinkFile2 -> example_file.txt

```

**参考:**T2】https://nodejs . org/API/fs . html # fs _ fs _ lctown _ path _ uid _ GID _ callback