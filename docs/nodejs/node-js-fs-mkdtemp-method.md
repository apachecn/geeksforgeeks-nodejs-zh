# Node.js fs.mkdtemp()方法

> 原文:[https://www.geeksforgeeks.org/node-js-fs-mkdtemp-method/](https://www.geeksforgeeks.org/node-js-fs-mkdtemp-method/)

**fs.mkdtemp()方法**用于创建唯一的临时目录。文件夹名称是通过在前缀字符串后面附加 6 个随机生成的字符来创建的。也可以通过在文件夹路径后使用分隔符在文件夹内创建临时目录。

**语法:**

```
fs.mkdtemp( prefix, options, callback )
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **Prefix:** It is a string that will always be used before six randomly generated numbers of the directory are created.
*   **Option:** is a character string or object with encoding attribute, which can be used to specify the character encoding to be used.
*   **Callback:** is a function that will be called when the method is executed.
    *   **err:** If the operation fails, this error will be thrown.
    *   **Folder:** is the path of the temporary folder created by the function.

下面的例子说明了 Node.js 中的 **fs.mkdtemp()方法**:

**示例 1:** 本示例在当前目录中创建一个前缀为“temp-”的临时目录。

```
// Node.js program to demonstrate the
// fs.mkdtemp() method

// Import the filesystem module
const fs = require('fs');

fs.mkdtemp("temp-", (err, folder) => {
  if (err)
    console.log(err);
  else {
    console.log("The temporary folder path is:", folder);
  }
});
```

**输出:**

```
The temporary folder path is: temp-2jEcWI
```

**示例 2:** 本示例在操作系统的临时目录中创建一个临时文件夹。

```
// Node.js program to demonstrate the
// fs.mkdtemp() method

// Import the filesystem module
const fs = require('fs');

// Import the os module
const os = require('os'); 

// Get the separator from the path module
const { sep } = require('path');

// Get the temporary directory of the system
const tmpDir = os.tmpdir(); 

fs.mkdtemp(`${tmpDir}${sep}`, (err, folder) => {
  if (err)
    console.log(err);
  else {
    console.log("The temporary folder path is:", folder);
  }
});
```

**输出:**

```
The temporary folder path is: C:\Users\userone\AppData\Local\Temp\2avQ7n
```

**参考:**[https://nodejs . org/API/fs . html # fs _ fs _ mkdtemp _ prefix _ options _ callback](https://nodejs.org/api/fs.html#fs_fs_mkdtemp_prefix_options_callback)