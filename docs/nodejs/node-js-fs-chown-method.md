# Node.js fs.chown()方法

> 原文:[https://www.geeksforgeeks.org/node-js-fs-chown-method/](https://www.geeksforgeeks.org/node-js-fs-chown-method/)

**fs.chown()方法**用于异步更改给定路径的所有者和组。该功能接受用户 id 和组 id，可用于设置各自的所有者和组。它有一个回调函数，如果函数失败，它会返回任何可能出现的错误。

**语法:**

```
fs.chown( path, uid, gid, callback )
```

**参数:**这个方法接受上面提到的和下面描述的四个参数:

*   **Path:** It is a string, Buffer or URL that indicates the path of the file that the owner and group must change.
*   **uid:** is a number representing the user id corresponding to the owner to be set.
*   **Gid:** is a number representing the group ID corresponding to the group to be set.
*   **Callback:** is a function that will be called when the method is executed.
    *   **err:** If the method fails, this error will be thrown.

下面的例子说明了 Node.js 中的 **fs.chown()方法**:

**示例 1:** 本示例显示了所有者的设置。

```
// Node.js program to demonstrate the
// fs.chown() method

// Import the filesystem module
const fs = require('fs');

let filepath = "example_file.txt";

// Set the owner to a new one keeping the group same
// New owner is "geeksforgeeks" with user id 1541
fs.chown(filepath, 1541, 999, (error) => {
  if (error)
    console.log("Error Code:", error);
  else
    console.log("uid and gid set successfully");
});
```

**运行代码前:**

```
xubuntu@xubuntu: ~/Desktop/fs-chown$ ls -l
total 8
-rw-rw--w- 1 xubuntu xubuntu 4 Apr 25 04:08 example_file.txt
-rw-rw-r-- 1 xubuntu xubuntu 290 Apr 25 04:08 index.js

```

**代码输出:**

```
Given uid and gid set successfully

```

**运行代码后:**

```
xubuntu@xubuntu: ~/Desktop/fs-chown$ ls -l
total 8
-rw-rw--w- 1 geeksforgeeks xubuntu 4 Apr 25 04:08 example_file.txt
-rw-rw-r-- 1 xubuntu xubuntu 290 Apr 25 04:08 index.js

```

**示例 2:** 此示例显示了组的设置。

```
// Node.js program to demonstrate the
// fs.chown() method

// Import the filesystem module
const fs = require('fs');

let filepath = "example_file.txt";

// Set the owner and group both to a new one
// New owner is "sam" with owner id 1500
// New group is "author" with group id 1021
fs.chown(filepath, 1500, 1021, (error) => {
  if (error)
    console.log("Error Code:", error);
  else
    console.log("uid and gid set successfully");
});
```

**运行代码前:**

```
xubuntu@xubuntu: ~/Desktop/fs-chown$ ls -l
total 8
-rw-rw--w- 1 xubuntu xubuntu 4 Apr 25 04:09 example_file.txt
-rw-rw-r-- 1 xubuntu xubuntu 290 Apr 25 04:09 index.js

```

**代码输出:**

```
Given uid and gid set successfully

```

**运行代码后:**

```
xubuntu@xubuntu: ~/Desktop/fs-chown$ ls -l
total 8
-rw-rw--w- 1 sam author 4 Apr 25 04:09 example_file.txt
-rw-rw-r-- 1 xubuntu xubuntu 290 Apr 25 04:09 index.js

```

**参考:**T2【https://nodejs . org/API/fs . html # fs _ fs _ chown _ path _ uid _ GID _ callback