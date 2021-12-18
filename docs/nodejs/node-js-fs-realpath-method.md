# Node.js fs.realpath()方法

> 原文:[https://www.geeksforgeeks.org/node-js-fs-realpath-method/](https://www.geeksforgeeks.org/node-js-fs-realpath-method/)

**fs.realPath()方法**用于计算给定路径的规范路径名。它通过解析路径中的`.`、`..`和符号链接来实现。

**语法:**

```js
fs.realpath( path, options, callback )
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **Path:** Save the directory path to be resolved. It can be a string, a buffer or a web address.
*   **Option:** is a string or object that can be used to specify optional parameters that affect the operation. It has an optional parameter:
    *   **Code:** It is a string that defines the parsing path code.
*   **Callback:** is a function that will be called when the method is executed.
    *   **err:** If the operation fails, this error will be thrown.
    *   [T0】 resolved path: 【T1] It is a string or buffer that represents the resolution path.

下面的例子说明了 Node.js 中的 **fs.realPath()方法**:

**示例 1:** 本示例使用 fs.realPath()方法获取给定路径的规范路径。

```js
// Node.js program to demonstrate the
// fs.realPath() method

// Import the filesystem module
const fs = require('fs');

console.log("Current Directory Path:", __dirname);

// Finding the canonical path
// one directory up
path1 = __dirname + "\\..";

fs.realpath(path1, (error, resolvedPath) => {
  if (error) {
    console.log(error);
  }
  else {
    console.log("One directory up resolved"
      + " path is: ", resolvedPath);
  }
});

// Finding the canonical path
// two directories up
path2 = __dirname + "\\..\\..";

fs.realpath(path2, (error, resolvedPath) => {
  if (error) {
    console.log(error);
  }
  else {
    console.log("Two directories up resolved"
          + " path is:", resolvedPath);
  }
});
```

**输出:**

```js
Current Directory Path: G:\tutorials\nodejs-fs-realPath
Two directories up resolved path is: G:\
One directory up resolved path is: G:\tutorials
```

**示例 2:** 本示例使用 fs.realPath()方法演示不同的编码类型。

```js
// Node.js program to demonstrate the
// fs.realPath() method

// Import the filesystem module
const fs = require('fs');

path = __dirname + "\\..";

// Getting the canonical path in utf8 encoding
fs.realpath(path, {encoding: "utf8"}, (error, resolvedPath) => {
  if (error) {
    console.log(error);
  }
  else {
    console.log("The resolved path is:", resolvedPath);
  }
});

// Getting the canonical path in hex encoding
fs.realpath(path, {encoding: "hex"}, (error, resolvedPath) => {
  if (error) {
    console.log(error);
  }
  else {
    console.log("The resolved path is:", resolvedPath);
  }
});

// Getting the canonical path in base64 encoding
fs.realpath(path, {encoding: "base64"}, (error, resolvedPath) => {
  if (error) {
    console.log(error);
  }
  else {
    console.log("The resolved path is:", resolvedPath);
  }
});
```

**输出:**

```js
The resolved path is: G:\tutorials
The resolved path is: 473a5c7475746f7269616c73
The resolved path is: RzpcdHV0b3JpYWxz
```

**参考:**[https://nodejs . org/API/fs . html # fs _ fs _ realath _ path _ options _ callback](https://nodejs.org/api/fs.html#fs_fs_realpath_path_options_callback)