# Node.js fs.renameSync()方法

> 原文:[https://www.geeksforgeeks.org/node-js-fs-renamesync-method/](https://www.geeksforgeeks.org/node-js-fs-renamesync-method/)

**fs.renameSync()方法**用于将给定旧路径的文件同步重命名为给定新路径。如果目标文件已经存在，它将覆盖该文件。

**语法:**

```
fs.renameSync( oldPath, newPath )
```

**属性值:**

*   **Old path:** Save the path of the file to be renamed. It can be a string, a buffer or a web address.
*   **New Path:** The new path to rename the saved file. It can be a string, a buffer or a web address.

下面的例子说明了 Node.js 中的 **fs.renameSync()方法**:

**示例 1:** 本示例使用 fs.renameSync()方法重命名文件。

```
// Node.js program to demonstrate the
// fs.renameSync() method

// Import the filesystem module
const fs = require('fs');

// List all the filenames before renaming
getCurrentFilenames();

// Rename the file
fs.renameSync('hello.txt', 'world.txt');

// List all the filenames after renaming
getCurrentFilenames();

// function to get current filenames in directory
function getCurrentFilenames() {
  console.log("Current filenames:");
  fs.readdirSync(__dirname).forEach(file => {
    console.log(file);
  });
}
```

**输出:**

```
Current filenames:
hello.txt
index.js
package.json
Current filenames:
index.js
package.json
world.txt
```

**示例 2:** 本示例使用 fs.renameSync()方法演示文件重命名过程中的错误。

```
// Node.js program to demonstrate the
// fs.renameSync() method

// Import the filesystem module
const fs = require('fs');

// List all the filenames before renaming
getCurrentFilenames();

// Rename a non-existent file
fs.renameSync('nonexist.txt', 'world.txt');

// List all the filenames after renaming
getCurrentFilenames();

// Function to get current filenames in directory
function getCurrentFilenames() {
  console.log("Current filenames:");
  fs.readdirSync(__dirname).forEach(file => {
    console.log(file);
  });
}
```

**输出:**

```
Current filenames:
index.js
package.json
world.txt
internal/fs/utils.js:220
    throw err;
    ^

Error: ENOENT: no such file or directory, rename 'nonexist.txt' -> 'world.txt'
    at Object.renameSync (fs.js:643:3)
    at Object. (G:\tutorials\nodejs-fs-renameSync\index.js:29:4)
    at Module._compile (internal/modules/cjs/loader.js:956:30)
    at Object.Module._extensions..js (internal/modules/cjs/loader.js:973:10)
    at Module.load (internal/modules/cjs/loader.js:812:32)
    at Function.Module._load (internal/modules/cjs/loader.js:724:14)
    at Function.Module.runMain (internal/modules/cjs/loader.js:1025:10)
    at internal/main/run_main_module.js:17:11 {
  errno: -4058,
  syscall: 'rename',
  code: 'ENOENT',
  path: 'nonexist.txt',
  dest: 'world.txt'
}
```

**参考:**[https://nodejs . org/API/fs . html # fs _ fs _ renamesync _ old path _ new path](https://nodejs.org/api/fs.html#fs_fs_renamesync_oldpath_newpath)