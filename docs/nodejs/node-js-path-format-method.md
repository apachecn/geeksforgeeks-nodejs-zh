# Node.js path.format()方法

> 原文:[https://www.geeksforgeeks.org/node-js-path-format-method/](https://www.geeksforgeeks.org/node-js-path-format-method/)

**path.format()方法**用于从给定的路径对象返回路径字符串。该方法有一些规则，其中一个路径属性比另一个获得更高的优先级:

*   If the "dir" parameter is provided, the "root" parameter of the path object is ignored.
*   If the Basic parameter is provided, the "ext" and "name" parameters of the path object are ignored.

**语法:**

```js
path.format( pathObject )
```

**参数:**该函数接受包含路径细节的单个参数**病理对象**。它有以下参数:

*   **dir:** It specifies the directory name of the path object.
*   **Root:** Specifies the root of the path object.
*   **Basis:** Specify the basis of the path object.
*   **Name:** Specifies the file name of the path object.
*   **ext:** Specify the file extension of the path object.

**返回值:**从提供的路径对象返回路径字符串。

下面的程序说明了 Node.js 中的 path.format()方法:

**例 1:** 在 POSIX

```js
// Import the path module
const path = require('path');

// CASE 1
// If "dir", "root" and "base" are all given,
// "root" is ignored.
let path1 = path.format({
    root: "/ignored/root/",
    dir: "/home/user/personal",
    base: "details.txt",
});
console.log("Path 1:", path1);

// CASE 2
// If "dir" is not specified then "root" will be used 
// If only "root" is provided
// platform separator will not be included.
// "ext" will be ignored.
let path2 = path.format({
    root: "/",
    base: "game.dat",
    ext: ".noextension",
});
console.log("Path 2:", path2);

// CASE 3
// If "base" is not specified
// "name" and "ext" will be used 
let path3 = path.format({
    root: "/images/",
    name: "image",
    ext: ".jpg",
});
console.log("Path 3:", path3);
```

上

**输出:**

```js
Path 1: /home/user/personal/details.txt
Path 2: /game.dat
Path 3: /images/image.jpg
```

**示例 2:** 在 Windows 上

```js
// Import the path module
const path = require('path');

// CASE 1
// If "dir", "root" and "base" are all given,
// "root" is ignored.
let path1 = path.format({
    root: "C:\\ignored\\root",
    dir: "website\\dist",
    base: "index.html",
});
console.log("Path 1:", path1);

// CASE 2
// If "dir" is not specified then "root"
// will be used 
// If only "root" is provided platform
// separator will not be included.
// "ext" will be ignored.
let path2 = path.format({
    root: "C:\\",
    base: "style.css",
    ext: ".ignored",
});
console.log("Path 2:", path2);

// CASE 3
// If "base" is not specified
// "name" and "ext" will be used 
let path3 = path.format({
    root: "website\\",
    name: "main",
    ext: ".js",
});
console.log("Path 3:", path3);
```

**输出:**

```js
Path 1: website\dist\index.html
Path 2: C:\style.css
Path 3: website\main.js
```

**参考:**[https://nodejs . org/API/path . html # path _ path _ format _ pathobject](https://nodejs.org/api/path.html#path_path_format_pathobject)