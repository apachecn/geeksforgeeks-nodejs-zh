# Node.js fs.readdir()方法

> 原文:[https://www.geeksforgeeks.org/node-js-fs-readdir-method/](https://www.geeksforgeeks.org/node-js-fs-readdir-method/)

**fs.readdir()方法**用于异步读取给定目录的内容。此方法的回调返回目录中所有文件名的数组。options 参数可用于更改从方法返回文件的格式。

**语法:**

```js
fs.readdir( path, options, callback )
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **Path:** The directory path where the content to be read is saved. It can be a string, a buffer or a web address.
*   **Option:** is an object that can be used to specify optional parameters that affect the method. It has two optional parameters:
    *   **Encoding:** It is a string value that specifies which encoding is used for the file name of the callback parameter. The default value is utf8.
    *   **with file type:** is a Boolean value that specifies whether the file is returned as a file system. Direct object. The default value is false.
*   **Callback:** is a function that will be called when the method is executed.
    *   **err:** If the operation fails, this error will be thrown.
    *   **File:** is an array of String, Buffer or fs. A directory object that contains files in the directory.

下面的例子说明了 Node.js 中的 **fs.readdir()方法**:

**示例 1:** 本示例使用 fs.readdir()方法返回目录中的文件名或文件对象。

```js
// Node.js program to demonstrate the
// fs.readdir() method

// Import the filesystem module
const fs = require('fs');

// Function to get current filenames
// in directory
fs.readdir(__dirname, (err, files) => {
  if (err)
    console.log(err);
  else {
    console.log("\nCurrent directory filenames:");
    files.forEach(file => {
      console.log(file);
    })
  }
})

// Function to get current filenames
// in directory with "withFileTypes"
// set to "true" 

fs.readdir(__dirname, 
  { withFileTypes: true },
  (err, files) => {
  console.log("\nCurrent directory files:");
  if (err)
    console.log(err);
  else {
    files.forEach(file => {
      console.log(file);
    })
  }
})
```

**输出:**

```js
Current directory filenames:
index.js
package.json
text_file_a.txt
text_file_b.txt

Current directory files:
Dirent { name: 'index.js', [Symbol(type)]: 1 }
Dirent { name: 'package.json', [Symbol(type)]: 1 }
Dirent { name: 'text_file_a.txt', [Symbol(type)]: 1 }
Dirent { name: 'text_file_b.txt', [Symbol(type)]: 1 }
```

**示例 2:** 本示例使用 fs.readdir()方法仅返回带有“.”的文件名。txt "扩展名。

```js
// Node.js program to demonstrate the
// fs.readdir() method

// Import the filesystem module
const fs = require('fs');
const path = require('path');

// Function to get current filenames
// in directory with specific extension
fs.readdir(__dirname, (err, files) => {
  if (err)
    console.log(err);
  else {
    console.log("\Filenames with the .txt extension:");
    files.forEach(file => {
      if (path.extname(file) == ".txt")
        console.log(file);
    })
  }
})
```

**输出:**

```js
Filenames with the .txt extension:
text_file_a.txt
text_file_b.txt
```

**参考:**[https://nodejs . org/API/fs . html # fs _ fs _ readdir _ path _ options _ callback](https://nodejs.org/api/fs.html#fs_fs_readdir_path_options_callback)