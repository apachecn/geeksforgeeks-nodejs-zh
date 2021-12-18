# Node.js fsPromises.symlink()方法

> 原文:[https://www . geesforgeks . org/node-js-fspromiss-symlink-method/](https://www.geeksforgeeks.org/node-js-fspromises-symlink-method/)

**fsPromises.symlink()** 方法用于创建到指定路径的 symlink，然后在成功时解析*promises*而没有参数。这会创建一个链接，使路径指向目标。相对目标是相对于链接的父目录。

语法:

```
fsPromises.symlink( target, path, type )
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **Target:** It is a string, buffer or web address, which represents the path where *symbolic link* must be created.
*   **Path:** is a string, buffer or web address that represents the path of creating *symbolic link* .
*   **Type:** is a string representing the *symbolic link* type to be created. It can be specified with "file", "dir" or "junction". If the target does not exist, the *<u>file</u>* will be used.

*类型*参数仅在 Windows 平台上使用，可以是*【目录】【文件】*或*【交汇点】*之一。Windows 交叉点要求目标路径是绝对的。当使用*‘连接’*时，目标参数将自动规范化为绝对路径。

**示例:**这个示例说明了 Node.js 中的**方法:**

**文件名:**

```
// Node.js program to demonstrate the 
// fsPromises.symlink method 

// Import the filesystem module 
const fs = require('fs'); 
const fsPromises = fs.promises;

console.log("Contents of the text file:"); 
console.log(fs.readFileSync(
        'example_file.txt', 'utf8')); 

fsPromises.symlink(__dirname + 
    "\\example_file.txt", "symlinkToFile", 'file') 
.then(function() {
  console.log("\nSymlink created\n"); 
  console.log("Contents of the symlink created:"); 
  console.log(fs.readFileSync('symlinkToFile', 'utf8')); 
})
.catch(function(error) {
  console.log(error);
});
```

**运行该程序的步骤:**使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
Contents of the text file:
Hello Geeks

Symlink created

Contents of the symlink created:
Hello Geeks

```

**参考:**[https://nodejs . org/API/fs . html # fs _ fspromises _ symlink _ target _ path _ type](https://nodejs.org/api/fs.html#fs_fspromises_symlink_target_path_type)