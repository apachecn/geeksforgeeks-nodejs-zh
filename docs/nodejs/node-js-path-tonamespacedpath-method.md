# node . js path . tonamespacedpath()方法

> 原文:[https://www . geesforgeks . org/node-js-path-tonamespacedpath-method/](https://www.geeksforgeeks.org/node-js-path-tonamespacedpath-method/)

**path.toNamespacedPath()方法**用于从给定路径中找到等价的命名空间前缀路径。此方法仅在 Windows 系统上有意义。它将返回相同的路径，而无需在 POSIX 系统上进行修改。如果路径不是字符串，它将在不修改的情况下返回。

**语法:**

```js
path.toNamespacedPath( path )
```

**参数:**该函数接受如上所述的单个参数，描述如下:

*   **Path:** It is a string containing the path that must be converted.

**返回值:**它返回一个字符串，该字符串具有等效的命名空间前缀路径。

下面的程序说明了 **path.toNamespacedPath()** 方法:

**例 1:**

```js
// Import the path module
const path = require('path');

let originalPath = "C:\\Windows\\users";
console.log("Original Path:", originalPath);

let nameSpacedPath = path.toNamespacedPath(originalPath);
console.log("Namespaced Path:", nameSpacedPath);
```

**输出:**

```js
Original Path: C:\Windows\users
Namespaced Path: \\?\C:\Windows\users
```

**例 2:**

```js
// Import the path module
const path = require('path');

let originalPath = "C:\\Windows\\users\\..\\admin";
console.log("Original Path:", originalPath);

let nameSpacedPath = path.toNamespacedPath(originalPath);
console.log("Namespaced Path:", nameSpacedPath);
```

**输出:**

```js
Original Path: C:\Windows\users\..\admin
Namespaced Path: \\?\C:\Windows\admin
```

**参考:**[https://nodejs . org/API/path . html # path _ path _ tonamespacedpath _ path](https://nodejs.org/api/path.html#path_path_tonamespacedpath_path)