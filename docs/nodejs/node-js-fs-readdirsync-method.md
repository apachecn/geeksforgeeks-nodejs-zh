# Node.js fs.readdirSync()方法

> 原文:[https://www . geesforgeks . org/node-js-fs-readdirsync-method/](https://www.geeksforgeeks.org/node-js-fs-readdirsync-method/)

**fs.readdirSync()方法**用于同步读取给定目录的内容。方法返回一个包含目录中所有文件名或对象的数组。options 参数可用于更改从方法返回文件的格式。

**语法:**

```
fs.readdirSync( path, options )
```

**参数:**这个方法接受两个参数，如上所述，如下所述:

*   **Path:** It stores the path of the directory from which the content must be read. It can be a string, a buffer or a web address.
*   **Option:** is an object that can be used to specify optional parameters that affect the method. It has two optional parameters:
    *   **Encoding:** It is a string value that specifies which encoding is used for the file name of the callback parameter. The default value is utf8.
    *   **with file type:** is a Boolean value that specifies whether the file is returned as a file system. Direct object. The default value is false.

**返回:**返回字符串、缓冲区或 fs 的数组。包含目录中文件的目录对象。

下面的例子说明了 Node.js 中的 **fs.readdirSync()方法**:

**示例 1:** 本示例使用 fs.readdirSync()方法返回目录中的文件名或文件对象。

```
// Node.js program to demonstrate the
// fs.readdirSync() method

// Import the filesystem module
const fs = require('fs');

// Function to get current filenames
// in directory
filenames = fs.readdirSync(__dirname);

console.log("\nCurrent directory filenames:");
filenames.forEach(file => {
  console.log(file);
});

// Function to get current filenames
// in directory with "withFileTypes"
// set to "true" 

fileObjs = fs.readdirSync(__dirname, { withFileTypes: true });

console.log("\nCurrent directory files:");
fileObjs.forEach(file => {
  console.log(file);
});
```

**输出:**

```
Current directory filenames:
CONTRUBUTIONS.txt
index.html
index.js
package.json
README.md

Current directory files:
Dirent { name: 'CONTRUBUTIONS.txt', [Symbol(type)]: 1 }
Dirent { name: 'index.html', [Symbol(type)]: 1 }
Dirent { name: 'index.js', [Symbol(type)]: 1 }
Dirent { name: 'package.json', [Symbol(type)]: 1 }
Dirent { name: 'README.md', [Symbol(type)]: 1 }
```

**示例 2:** 本示例使用 fs.readdirSync()方法只返回带有“.”的文件名。md "分机。

```
// Node.js program to demonstrate the
// fs.readdirSync() method

// Import the filesystem module
const fs = require('fs');
const path = require('path');

// Function to get current filenames
// in directory with specific extension
files = fs.readdirSync(__dirname);

console.log("\Filenames with the .md extension:");
files.forEach(file => {
  if (path.extname(file) == ".md")
    console.log(file);
})
```

**输出:**

```
Filenames with the .md extension:
README.md
```

**参考:**[https://nodejs . org/API/fs . html # fs _ fs _ readdirsync _ path _ options](https://nodejs.org/api/fs.html#fs_fs_readdirsync_path_options)