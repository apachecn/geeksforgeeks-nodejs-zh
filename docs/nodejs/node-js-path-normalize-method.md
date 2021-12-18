# Node.js path.normalize()方法

> 原文:[https://www . geesforgeks . org/node-js-path-normalize-method/](https://www.geeksforgeeks.org/node-js-path-normalize-method/)

**路径归一化()方法**用于归一化给定的路径。规范化解决了(。)和(..)将路径分段为正确的形式。如果方法遇到多个路径分隔符，它会用一个特定于平台的路径分隔符替换所有路径分隔符。此方法保留所有尾部分隔符。

**语法:**

```js
path.normalize( path )
```

**参数:**该方法接受单参数**路径**，该路径保存将被规范化的文件路径。如果此参数不是字符串，将引发类型错误。

**返回值:**返回路径规范化形式的字符串。

下面的例子说明了 node.js 中的 **path.normalize()方法**:

**例:**

```js
// Node.js program to demonstrate the   
// path.normalize() method

// Import the path module
const path = require('path');

path1 = path.normalize("/users/admin/.");
console.log(path1)

path2 = path.normalize("/users/admin/..");
console.log(path2)

path3 = path.normalize("/users/admin/../comments")
console.log(path3);

path4 = path.normalize("/users///admin///comments")
console.log(path4);
```

**输出:**

```js
\users\admin
\users
\users\comments
\users\admin\comments
```

**参考:**T2】https://nodejs.org/api/path.html#path_path_normalize_path