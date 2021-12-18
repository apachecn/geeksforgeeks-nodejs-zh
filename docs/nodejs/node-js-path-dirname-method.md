# Node.js path.dirname()方法

> 原文:[https://www.geeksforgeeks.org/node-js-path-dirname-method/](https://www.geeksforgeeks.org/node-js-path-dirname-method/)

**path.dirname()方法**用于获取给定路径的目录名。它忽略了各自平台的尾部目录分隔符。

**语法:**

```js
path.dirname( path )
```

**参数:**该函数接受一个参数，如上所述，如下所述:

*   **Path:** is the file path used to extract the directory name. If this parameter is not a string value, it will throw a type error.

**返回值:**返回一个包含路径目录的字符串。

下面的程序说明了 Node.js 中的 **path.dirname()方法**:

**例 1:**

```js
// Node.js program to demonstrate the    
// path.dirname() method 

// Import the path module
const path = require('path');

// Complete file path
path1 = path.dirname("/users/admin/website/index.html");
console.log(path1)

// Only file name
// returns a period (.)
path2 = path.dirname("readme.md");
console.log(path2)

// Path with file not specified
path3 = path.dirname("website/post/comments")
console.log(path3);
```

**输出:**

```js
/users/admin/website
.
website/post
```

**例 2:**

```js
// Node.js program to demonstrate the    
// path.dirname() method 

// Import the path module
const path = require('path');

console.log("File name:", __filename);
path1 = path.dirname(__filename);
console.log(path1);

console.log("Directory name:", __dirname);
path2 = path.dirname(__dirname);
console.log(path2);
```

**输出:**

```js
File name:  G:\tutorials\nodejs-path-dirname\index.js
G:\tutorials\nodejs-path-dirname
Directory name:  G:\tutorials\nodejs-path-dirname
G:\tutorials
```

**参考:**T2】https://nodejs.org/api/path.html#path_path_dirname_path