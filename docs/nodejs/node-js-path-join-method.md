# Node.js | path.join()方法

> 原文:[https://www.geeksforgeeks.org/node-js-path-join-method/](https://www.geeksforgeeks.org/node-js-path-join-method/)

**path.join()方法**用于使用特定于平台的分隔符连接多个路径段，以形成单个路径。在连接发生后，最终路径被规范化。路径段是使用逗号分隔值指定的。

**语法:**

```
path.join( [...paths] )

```

**参数:**该函数接受一个参数，如上所述，如下所述:

*   **Path:** This is a comma-separated path sequence that will be connected together to form the final path.

**返回值:**返回包含所有段的完整规范化路径的字符串。

下面的例子说明了 Node.js 中的 **path.join()方法**:

**例 1:**

## node . js

```
// Node.js program to demonstrate the   
// path.join() Method  

// Import the path module
const path = require('path');

// Joining 2 path-segments
path1 = path.join("users/admin/files", "index.html");
console.log(path1)

// Joining 3 path-segments
path2 = path.join("users", "geeks/website", "index.html");
console.log(path2)

// Joining with zero-length paths
path3 = path.join("users", "", "", "index.html");
console.log(path3)
```

**输出:**

```
users\admin\files\index.html
users\geeks\website\index.html
users\index.html

```

**例 2:**

## node . js

```
// Node.js program to demonstrate the   
// path.join() Method  

// Import the path module
const path = require('path');

// Normalizing of the final path
path1 = path.join("users", "..", "files", "readme.md");
console.log(path1)

// Zero length final path
// returns a period (.)
path2 = path.join("users", "..");
console.log(path2)

// Getting the directory path one folder above
console.log("Current Directory: ", __dirname);
path3 = path.join(__dirname, "..");
console.log("Directory above:", path3)
```

**输出:**

```
files\readme.md
.
Dirname:  G:\tutorials\nodejs-path-join
Directory above: G:\tutorials

```

**参考:**T2】https://nodejs.org/api/path.html#path_path_join_paths