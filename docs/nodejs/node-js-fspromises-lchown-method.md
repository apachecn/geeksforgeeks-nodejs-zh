# Node.js fsPromises.lchown()方法

> 原文:[https://www . geesforgeks . org/node-js-fspromiss-lch own-method/](https://www.geeksforgeeks.org/node-js-fspromises-lchown-method/)

**fsPromises.lchown()** 方法用于更改文件的所有权，然后在成功时无参数地解析 Promise。该功能接受用户 id 和组 id，可用于设置各自的所有者和组。

**语法:**

```js
fsPromises.lchown( path, uid, gid )
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **Path:** It is a string, buffer or web address that indicates the path of the file that the owner and group must change.
*   **uid:** is an integer representing the user id corresponding to the owner to be set.
*   **Gid:** is an integer representing the group ID corresponding to the group to be set.

**注意:**这个方法只在 macOS 上实现。

**示例:** Node.js 程序演示 fsPromises.lchown()方法。

**文件名:**

```js
// Node.js program to demonstrate the 
// fsPromises.lchown() method 

// Import the filesystem module 
const fs = require('fs'); 
const fsPromises = fs.promises;

let filepath = "example_file.txt"; 
let symlinkpath = "symlinkFile"; 

// Create a symlink to the file 
fs.symlinkSync(filepath, symlinkpath); 

// Set the owner and group of the
// symbolic link to a new one 
// New owner is "geeksforgeeks" with
// user id 1200 New group is "editor"
// with group id 1201 
fs.lchown(symlinkpath, 1200, 1201)
.then(function() {
  console.log("Given uid and gid set successfully"); 
})
.catch(function(error) {
  console.log(error);
});
```

**运行该程序的步骤:**使用以下命令运行 **index.js** 文件:

```js
node index.js
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
lrwxrwxrwx 1 geeksforgeeks editor 16 Apr 26 09:15 
        symlinkFile -> example_file.txt

```