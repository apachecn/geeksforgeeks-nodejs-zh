# Node.js fs.readlink()方法

> 原文:[https://www.geeksforgeeks.org/node-js-fs-readlink-method/](https://www.geeksforgeeks.org/node-js-fs-readlink-method/)

**fs.readlink()方法**是 fs 模块的内置应用编程接口，用于异步返回符号链接的值，即链接到的路径。可选参数可用于指定链接路径的字符编码。

**语法:**

```js
fs.readlink( path[, options], callback )
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **路径:**它是一个字符串、缓冲区或网址，代表符号链接的路径。
*   **选项:**它是一个对象或字符串，可用于指定将影响输出的可选参数。它有一个可选参数:
    *   **编码:**是一个字符串值，指定返回链接路径的字符编码。默认值为“utf8”。
*   **回调:**是执行方法时会调用的函数。
    *   **err:** 这是一个如果方法失败会抛出的错误。
    *   **链接字符串:**它是包含符号链接字符串值的字符串或缓冲区对象。

下面的例子说明了 Node.js 中的 **fs.readlink()方法**:

**示例 1:** 本示例读取文件的符号链接值，并更改该值的编码。

## java 描述语言

```js
// Node.js program to demonstrate the
// fs.readlink() method

// Import the filesystem module
const fs = require('fs');

// Create a symbolic link
fs.symlinkSync(__dirname + "\\example_file.txt", 
                       "symlinkToFile", 'file');

console.log("\nSymlink created\n");

// Using the default utf-8 encoding for the link value
fs.readlink("symlinkToFile", (err, linkString) => {
  if (err)
    console.log(err);
  else
    console.log("Path of the symlink:", linkString);
});

// Using the base64 encoding for the link value
fs.readlink("symlinkToFile", 

  // Specify the options object
  {encoding: "base64"},
  (err, linkString) => {
    if (err)
      console.log(err);
    else
      console.log("Path in base64:", linkString);
});
```

**输出:**

> 符号链接已创建
> 
> 符号链接的路径:G:\ tutorials \ nodejs-fs-read link \ example _ file . txt
> base 64 中的路径:rzpcdhv0b3jpywxxxg5 vzgvqcy1mcy 1 yzwfkbgluna1xlegftcgxlx 2 zpbguudhh 0

**示例 2:** 本示例读取目录的符号链接的值。

## java 描述语言

```js
// Node.js program to demonstrate the
// fs.readlink() method

// Import the filesystem module
const fs = require('fs');

// Create a symbolic link
fs.symlinkSync(__dirname + "\\example_directory", 
            "symlinkToDir", 'dir');

console.log("\nSymlink created\n");

fs.readlink("symlinkToDir", (err, linkString) => {
  if (err)
    console.log(err);
  else
    console.log("Path of the symlink:", linkString);
});
```

**输出:**

> 符号链接已创建
> 
> 符号链接的路径:G:\教程\ nodejs-fs-read link \ example _ directory

**参考:**T2【https://nodejs . org/API/fs . html # fs _ fs _ readlink _ path _ options _ callback