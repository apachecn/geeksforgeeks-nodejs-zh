# Node.js fs.realpathSync()方法

> 原文:[https://www . geesforgeks . org/node-js-fs-realpath sync-method/](https://www.geeksforgeeks.org/node-js-fs-realpathsync-method/)

**fs.realpathSync()方法**用于同步计算给定路径的规范路径名。它是通过解决。,..以及路径中的符号链接，并返回解析后的路径。
**语法:**

```js
fs.realpathSync( path, options )
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **路径:**保存需要解析的目录路径。它可以是字符串、缓冲区或网址。
*   **选项:**它是一个字符串或对象，可用于指定将影响操作的可选参数。它有一个可选参数:
    *   **编码:**是定义解析路径编码的字符串。

**返回:**返回代表解析路径的字符串或缓冲区。
以下示例说明了 Node.js:
**中的 **fs.realpathSync()方法**示例 1:**

## java 描述语言

```js
// Node.js program to demonstrate the
// fs.realpathSync() method

// Import the filesystem module
const fs = require('fs');

console.log("Current Directory Path:", __dirname);

// Finding the canonical path
// one directory up
path1 = __dirname + "\\..";

resolvedPath = fs.realpathSync(path1);
console.log("One directory up resolved path is: ",
             resolvedPath);

// Finding the canonical path
// two directories up
path2 = __dirname + "\\..\\..";

resolvedPath = fs.realpathSync(path2);
console.log("Two directories up resolved path is: ",
             resolvedPath);
```

**输出:**

```js
Current Directory Path: G:\tutorials\nodejs-fs-realPathSync
One directory up resolved path is:  G:\tutorials
Two directories up resolved path is:  G:\
```

**例 2:**

## java 描述语言

```js
// Node.js program to demonstrate the
// fs.realpathSync() method

// Import the filesystem module
const fs = require('fs');

path = __dirname + "\\..";

// Getting the canonical path is utf8 encoding
resolvedPath = fs.realpathSync(path, { encoding: "utf8" });
console.log("The resolved path is: ", resolvedPath);

// Getting the canonical path is hex encoding
resolvedPath = fs.realpathSync(path, { encoding: "hex" });
console.log("The resolved path is: ", resolvedPath);

// Getting the canonical path is base64 encoding
resolvedPath = fs.realpathSync(path, { encoding: "base64" });
console.log("The resolved path is: ", resolvedPath);
```

**输出:**

```js
The resolved path is:  G:\tutorials
The resolved path is:  473a5c7475746f7269616c73
The resolved path is:  RzpcdHV0b3JpYWxz
```

**参考:**[https://nodejs . org/API/fs . html # fs _ fs _ realathsync _ path _ options](https://nodejs.org/api/fs.html#fs_fs_realpathsync_path_options)