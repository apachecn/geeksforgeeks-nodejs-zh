# Node.js fsPromises.opendir()方法

> 原文:[https://www . geesforgeks . org/node-js-fspromises-opendir-method/](https://www.geeksforgeeks.org/node-js-fspromises-opendir-method/)

**fsPromises.opendir()** 方法用于*异步*打开文件系统中的一个目录。它创造了一个 *fs。目录*，包含所有读取和清理目录的功能。该对象包含可用于访问目录的各种方法。

**语法:**

```js
fsPromises.opendir( path[, options])
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **路径:**它是一个字符串、缓冲区或网址，表示必须打开的目录的路径。
*   **选项:**它是一个字符串或一个对象，可用于指定将影响输出的可选参数。它有两个可选参数:
    *   **编码:**是一个字符串，指定打开目录时路径的编码以及后续读取操作的编码。*默认值为‘utf8’。*
    *   **bufferSize:** 它是一个数字，指定读取目录时内部缓冲的目录条目数。更高的值意味着更高的性能，但会导致更高的内存使用率。*默认值为‘32’。*

**示例:**这个示例说明了 Node.js 中的**方法**

**文件名:index.js**

```js
// Node.js program to demonstrate the 
// fsPromises.opendir() method 

// Import the filesystem module 
const fs = require('fs'); 
const fsPromises = fs.promises;

fsPromises.opendir(__dirname)
.then(function(result) {
  console.log(result);
})
.catch(function(error) {
  console.log(error);
});
```

**运行该程序的步骤:**
使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
Dir {
  [Symbol(kDirHandle)]: DirHandle {},
  [Symbol(kDirBufferedEntries)]: [],
  [Symbol(kDirPath)]: 'C:\\Users\\Lenovo\\Downloads\\Internship\\Program',
  [Symbol(kDirClosed)]: false,
  [Symbol(kDirOptions)]: { bufferSize: 32, encoding: 'utf8' },
  [Symbol(kDirReadPromisified)]: [Function: bound [kDirReadImpl]],
  [Symbol(kDirClosePromisified)]: [Function: bound close]
}

```

**参考:**[https://nodejs . org/API/fs . html # fs _ fspromises _ opendir _ path _ options](https://nodejs.org/api/fs.html#fs_fspromises_opendir_path_options)