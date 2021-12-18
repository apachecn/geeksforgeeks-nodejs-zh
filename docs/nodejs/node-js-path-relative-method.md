# Node.js path.relative()方法

> 原文:[https://www.geeksforgeeks.org/node-js-path-relative-method/](https://www.geeksforgeeks.org/node-js-path-relative-method/)

**path.relative()方法**用于根据当前工作目录找到从一个给定路径到另一个路径的相对路径。如果两个给定路径相同，它将解析为零长度字符串。

**语法:**

```
path.relative( from, to )
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **From:** This file path will be used as the basic path.
*   **to:** is the file path used to find the relative path.

**返回值:**返回路径规范化形式的字符串。

下面的程序说明了 Node.js 中的 **path.relative()方法**:

**例:**

```
// Node.js program to demonstrate the    
// path.relative() method 

// Import the path module
const path = require('path');

path1 = path.relative("geeks/website", "geeks/index.html");
console.log(path1)

path2 = path.relative("users/admin", "admin/files/website");
console.log(path2)

// When both the paths are same
// It returns blank string
path3 = path.relative("users/admin", "users/admin");
console.log(path3)
```

**输出:**

```
..\index.html
..\..\admin\files\website

```

**参考:**T2】https://nodejs.org/api/path.html#path_path_relative_from_to