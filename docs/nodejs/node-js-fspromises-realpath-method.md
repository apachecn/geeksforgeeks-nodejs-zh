# Node.js fsPromises.realpath()方法

> 原文:[https://www . geesforgeks . org/node-js-fspromiss-real path-method/](https://www.geeksforgeeks.org/node-js-fspromises-realpath-method/)

**fsPromises.realPath()** 方法使用与 *fs.realpath.native()* 函数相同的语义来确定路径的实际位置，然后用解析后的路径解析 Promise。仅支持可转换为 *UTF8* 字符串的路径。

**语法:**

```js
fsPromises.realpath( path, options )

```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **Path:** Save the directory path to be resolved. It can be a string, a buffer or a web address.
*   **Option:** is a string or object that can be used to specify optional parameters that affect the operation. It has an optional parameter:
    *   **Code:** It is a string that defines the parsing path code.

下面的例子说明了 **fs。Node.js 中的 promisresealpath()**方法:

**示例 1:** 本示例使用 **fsPromises.realPath()** 方法获取给定路径的规范路径。

## Node.js

```js
// Node.js program to demonstrate the 
// fsPromises.realPath() method 

// Import the filesystem module 
const fs = require('fs'); 

console.log("Current Directory Path: ", __dirname); 

// Finding the canonical path 
// one directory up 
path1 = __dirname + "\\.."; 

fsPromises.realpath(path1, (error, resolvedPath)) 
    console.log("One directory up resolved"
      + " path is: ", resolvedPath); 

// Finding the canonical path 
// two directories up 
path2 = __dirname + "\\..\\.."; 

fsPromises.realpath(path2, (resolvedPath)) 

    console.log("Two directories up resolved"
          + " path is:", resolvedPath); 

```

**输出:**

```js
Current Directory Path: G:\tutorials\nodejs-fs-realPath
Two directories up resolved path is: G:\
One directory up resolved path is: G:\tutorials
```

**示例 2:** 本示例使用 **fsPromises.realPath()** 方法演示不同的编码类型。

## node . js

```js
// Node.js program to demonstrate the 
// fsPromises.realPath() method 

// Import the filesystem module 
const fs = require('fs'); 

path = __dirname + "\\.."; 

// Getting the canonical path in utf8 encoding 
fsPromises.realpath(path, {encoding: "utf8"})
console.log("The resolved path is:", resolvedPath); 

// Getting the canonical path in hex encoding 
fsPromises.realpath(path, {encoding: "hex"}) 
console.log("The resolved path is:", resolvedPath); 

// Getting the canonical path in base64 encoding 
fsPromises.realpath(path, {encoding: "base64"})
console.log("The resolved path is:", resolvedPath); 
```

**输出:**

```js
The resolved path is: G:\tutorials
The resolved path is: 473a5c7475746f7269616c73
The resolved path is: RzpcdHV0b3JpYWxz
```

**参考资料:**[https://nodejs . org/API/fs . html # fs _ fspromises _ realpath _ options](https://nodejs.org/api/fs.html#fs_fspromises_realpath_path_options)