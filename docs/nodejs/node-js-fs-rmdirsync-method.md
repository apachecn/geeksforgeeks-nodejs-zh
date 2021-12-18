# Node.js fs.rmdirSync()方法

> 原文:[https://www.geeksforgeeks.org/node-js-fs-rmdirsync-method/](https://www.geeksforgeeks.org/node-js-fs-rmdirsync-method/)

**fs.rmdirSync()方法**用于同步删除给定路径的目录。它还可以通过配置 options 对象递归地用于移除嵌套目录。它返回未定义。
**语法:**

```
fs.rmdirSync( path, options )
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **路径:**保存需要删除的目录的路径。它可以是字符串、缓冲区或网址。
*   **选项:**是一个可以用来指定影响操作的可选参数的对象。它有三个可选参数:
    *   **递归:**是一个布尔值，指定是否执行递归目录删除。在这种模式下，如果找不到指定的路径，并且在失败时重试该操作，则不会报告错误。默认值为假。
    *   **maxRetries:** 它是一个整数值，指定 Node.js 尝试执行操作的次数，如果由于任何错误而失败的话。操作在给定的重试延迟后执行。如果递归选项未设置为 true，则忽略此选项。默认值为 0。
    *   **retrydley:**是一个整数值，指定重试操作前等待的时间(毫秒)。如果递归选项未设置为 true，则忽略此选项。默认值为 100 毫秒。

以下示例说明了 Node.js:
**中的 **fs.rmdirSync()方法**示例 1:** 本示例使用 fs.rmdirSync()方法删除目录。

## java 描述语言

```
// Node.js program to demonstrate the
// fs.rmdirSync() method

// Import the filesystem module
const fs = require('fs');

// Get the current filenames
// in the directory
getCurrentFilenames();

fs.rmdirSync("directory_one");
console.log("Folder Deleted!");

// Get the current filenames
// in the directory to verify
getCurrentFilenames();

// Function to get current filenames
// in directory
function getCurrentFilenames() {
  console.log("\nCurrent filenames:");
  fs.readdirSync(__dirname).forEach(file => {
    console.log(file);
  });
  // console.log("\n");
}
```

**输出:**

```
Current filenames:
directory_one
index.js
package.json
Folder Deleted!

Current filenames:
index.js
package.json
```

**示例 2:** 本示例使用带有递归参数的 fs.rmdirSync()方法删除嵌套目录。

## java 描述语言

```
// Node.js program to demonstrate the
// fs.rmdirSync() method

// Get the current filenames
// in the directory
getCurrentFilenames();

// Using the recursive option to delete
// multiple directories that are nested
fs.rmdirSync("directory_one", {
  recursive: true,
});
console.log("Directories Deleted!");

// Get the current filenames
// in the directory to verify
getCurrentFilenames();

// Function to get current filenames
// in directory
function getCurrentFilenames() {
  console.log("\nCurrent filenames:");
  fs.readdirSync(__dirname).forEach(file => {
    console.log(file);
  });
  console.log("\n");
}
```

**输出:**

```
Current filenames:
directory_one
index.js
package.json

Directories Deleted!

Current filenames:
index.js
package.json
```

**参考:**T2https://nodejs.org/api/fs.html#fs_fs_rmdirsync_path_options