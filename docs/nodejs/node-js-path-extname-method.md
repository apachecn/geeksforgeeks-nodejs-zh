# Node.js path.extname()方法

> 原文:[https://www.geeksforgeeks.org/node-js-path-extname-method/](https://www.geeksforgeeks.org/node-js-path-extname-method/)

**path.extname()方法**用于获取文件路径的扩展名部分。从句点(.)的最后一次出现返回的扩展字符串。)放在路径字符串的末尾。如果文件路径中没有句点，则返回一个空字符串。

**语法:**

```
path.extname( path )
```

**参数:**该方法接受单参数**路径**，该路径保存用于提取扩展名的文件路径。

**返回值:**返回一个带有路径扩展部分的字符串。如果此参数不是字符串值，它将引发类型错误。

下面的例子说明了 node.js 中的 **path.extname()方法**:

**例 1:**

```
// Node.js program to demonstrate the   
// path.extname() method

// Import the path module
const path = require('path');

path1 = path.extname("hello.txt");
console.log(path1)

path2 = path.extname("readme.md");
console.log(path2)

// File with no extension
// Returns empty string
path3 = path.extname("fileDump")
console.log(path3)

// File with blank extension
// Return only the period
path4 = path.extname("example.")
console.log(path4)

path5 = path.extname("readme.md.txt")
console.log(path5)

// Extension name of the current script
path6 = path.extname(__filename)
console.log(path6)
```

**输出:**

```
.txt
.md

.
.txt
.js
```

**例 2:**

```
// Node.js program to demonstrate the   
// path.extname() method

// Import the path module
const path = require('path');

// Comparing extensions from a
// list of file paths
paths_array = [
    "/home/user/website/index.html",
    "/home/user/website/style.css",
    "/home/user/website/bootstrap.css",
    "/home/user/website/main.js",
    "/home/user/website/contact_us.html",
    "/home/user/website/services.html",
]

paths_array.forEach(filePath => {
    if (path.extname(filePath) == ".html")
        console.log(filePath);
});
```

**输出:**

```
/home/user/website/index.html
/home/user/website/contact_us.html
/home/user/website/services.html
```

**参考:**T2】https://nodejs.org/api/path.html#path_path_extname_path