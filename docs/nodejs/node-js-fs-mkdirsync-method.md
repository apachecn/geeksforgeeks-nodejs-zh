# Node.js fs.mkdirSync()方法

> 原文:[https://www.geeksforgeeks.org/node-js-fs-mkdirsync-method/](https://www.geeksforgeeks.org/node-js-fs-mkdirsync-method/)

**fs.mkdirSync()方法**是 **fs** 模块的内置应用编程接口，它提供了一个应用编程接口，用于以一种紧密围绕标准 **POSIX** 函数建模的方式与文件系统交互。
使用 **fs.mkdirSync()方法**同步创建目录。

**语法:**

```
fs.mkdirSync( path, options )
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **路径:**要创建目录的路径。可以是字符串、缓冲区等。
*   **选项:**是一个可选参数，决定如何递归等创建目录。

**返回值:**返回**未定义**。

下面的例子说明了 **fs.mkdirSync()方法**在 Node.js 中的使用:

**例 1:**

```
// Node.js program to demonstrate the
// fs.mkdirSync() method

const fs = require("fs");

const path = require("path");

// Using fs.exists() method to 
// check that the directory exists or not
console.log("Checking for directory " 
        + path.join(__dirname, "Geeks"));
fs.exists(path.join(__dirname, "Geeks"), exists => {
  console.log(exists ? "The directory already exists" 
                    : "Not found!");
});

// Using fs.mkdirSync() method
// to create the directory
fs.mkdirSync(path.join(__dirname, "Geeks"));

// Using fs.exists() method to
// check that the directory exists or not
fs.exists(path.join(__dirname, "Geeks"), exists => {
  console.log(exists ? "The directory already exists" 
                    : "Not found!");
});
```

**输出:**

```
Checking for directory c:\Users\Suraj\node\Geeks
Not found!
The directory already exists

```

**例 2:**

```
// Node.js program to demonstrate the
// fs.mkdirSync() method

const fs = require("fs");

const path = require("path");

// Using fs.exists() method to
// check that the directory exists or not
console.log("Checking for directory" 
        + path.join(__dirname, "Tisu"));
fs.exists(path.join(__dirname, "Tisu"), exists => {
  console.log(exists ? "The directory already exists"
                         : "Not found!");
});

// Using fs.mkdirSync() method
// to create the directory recursively
fs.mkdirSync(path.join(__dirname, "Tisu"), true);

// Using fs.exists() method to
// check that the directory exists or not
fs.exists(path.join(__dirname, "Tisu"), exists => {
  console.log(exists ? "The directory already exists" 
                    : "Not found!");
});
```

**输出:**

```
Checking for directory c:\Users\Suraj\node\Tisu
Not found!
The directory already exists

```

**注意:**以上程序使用`node index.js`命令编译运行。

参考:https://nodejs . org/API/fs . html # fs _ fs _ mkdirsync _ path _ options