# Node.js path.resolve()方法

> 原文:[https://www.geeksforgeeks.org/node-js-path-resolve-method/](https://www.geeksforgeeks.org/node-js-path-resolve-method/)

**path.resolve()方法**用于将一系列路径段解析为绝对路径。它的工作原理是从右到左处理路径序列，预先考虑每个路径，直到创建绝对路径。生成的路径被规范化，尾部斜线根据需要被删除。
如果没有给定路径段作为参数，则使用当前工作目录的绝对路径。
**语法:**

```
path.resolve( [...paths] )

```

**参数:**该函数接受一个参数，如上所述，如下所述:

*   **路径:**这是一系列文件路径，它们将被一起解析以形成绝对路径。如果此参数不是字符串值，它将引发类型错误。

**返回值:**返回绝对路径的字符串。

下面的程序说明了 Node.js:
中的 **path.resolve()方法**

**例 1:**

## Node.js

```
// Node.js program to demonstrate the   
// path.resolve() Method  

// Import the path module
const path = require('path');

console.log("Current directory:", __dirname);

// Resolving 2 path-segments
// with the current directory
path1 = path.resolve("users/admin", "readme.md");
console.log(path1)

// Resolving 3 path-segments
// with the current directory
path2 = path.resolve("users", "admin", "readme.md");
console.log(path2)

// Treating of the first segment
// as root, ignoring the current directory
path3 = path.resolve("/users/admin", "readme.md");
console.log(path3)
```

**输出:**

```
Current directory: G:\tutorials\nodejs-path-resolve
G:\tutorials\nodejs-path-resolve\users\admin\readme.md
G:\tutorials\nodejs-path-resolve\users\admin\readme.md
G:\users\admin\readme.md

```

**例 2:**

## Node.js

```
// Node.js program to demonstrate the   
// path.resolve() Method  

// Import the path module
const path = require('path');

console.log("Current directory:", __dirname);

// Normalization of the absolute paths
path1 = path.resolve("users", "..", "readme.md");
console.log(path1)

path2 = path.resolve("users", "admin", 
            "..", "files", "readme.md");
console.log(path2)

path3 = path.resolve("users", "admin",
            "..", "files", "..", "readme.md");
console.log(path3)
```

**输出:**

```
Current directory: G:\tutorials\nodejs-path-resolve
G:\tutorials\nodejs-path-resolve\readme.md
G:\tutorials\nodejs-path-resolve\users\files\readme.md
G:\tutorials\nodejs-path-resolve\users\readme.md

```

**参考:**T2】https://nodejs.org/api/path.html#path_path_resolve_paths