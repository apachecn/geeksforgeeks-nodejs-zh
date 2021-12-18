# Node.js fsPromises.rename()方法

> 原文:[https://www . geesforgeks . org/node-js-fs promises-rename-method/](https://www.geeksforgeeks.org/node-js-fspromises-rename-method/)

**fsPromises.rename()** 方法用于将给定旧路径的文件异步重命名为给定新路径。如果目标文件已经存在，它将覆盖该文件。它解决了承诺，成功后没有争论。

**语法:**

```
fsPromises.rename( oldPath, newPath )
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **[Old path]:** Save the file path to be renamed. It can be a string, a buffer or a web address.
*   **New Path:** A new path that needs to be renamed to save the file. It can be a string, a buffer or a web address.

下面的例子说明了 Node.js 中的 **fsPromises.rename()** 方法:

**示例 1:** 本示例使用 **fsPromises.rename()** 方法重命名文件:

## Node.js

```
// Node.js program to demonstrate the     
// fsPromises.rename() method  

// Import filesystem module 
const fs = require('fs');
const fsPromises = require('fs').promises;

// List all the filenames before renaming 
getCurrentFilenames();

(async function main() {
    try {

        // Rename the file 
        fsPromises.rename('GFG.txt', 'GeeksforGeeks.txt')
        console.log("\nFile Renamed!\n");

        // List all the filenames after renaming 
        getCurrentFilenames();

    } catch (err) {
        console.error(err);
    }
})();

// Function to get current filenames 
// in directory 
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
GFG.txt
GeeksforGeeks.js

File Renamed!

Current filenames:
GeeksforGeeks.js
GFG.txt
```

**示例 2:** 本示例使用 **fsPromises.rename()** 方法演示文件重命名过程中出现的错误:

## node . js

```
// Node.js program to demonstrate the     
// fsPromises.rename() method  

// Import filesystem module 
const fs = require('fs');
const fsPromises = require('fs').promises;

(async function main() {
    try {

        // List all the filenames before renaming 
        getCurrentFilenames();

        // Rename the file 
        fsPromises.rename('GeeksforGeeks.txt', 'geeks.txt')

        // List all the filenames after renaming 
        console.log("\nFile Renamed\n");

        // List all the filenames after renaming 
        getCurrentFilenames();
    }
    catch (err) {
        console.error(err);
    }
})();

// Function to get current filenames 
// in directory 
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
[Error: ENOENT: no such file or directory, rename  
'G:\tutorials\nodejs-fs-rename\GeeksforGeeks.txt' ->
'G:\tutorials\nodejs-fs-rename\geeks.txt'] {
 errno: -4058,
 code: 'ENOENT',
 syscall: 'rename',
 path: 'G:\\tutorials\\nodejs-fs-rename\\GeeksforGeeks.txt',
 dest: 'G:\\tutorials\\nodejs-fs-rename\\geeks.txt'
}
```

**参考:**[https://nodejs . org/API/fs . html # fs _ fspromises _ rename _ old path _ new path](https://nodejs.org/api/fs.html#fs_fspromises_rename_oldpath_newpath)