# node . js path . isabsolut()方法

> 原文:[https://www . geesforgeks . org/node-js-path-isabsolut-method/](https://www.geeksforgeeks.org/node-js-path-isabsolute-method/)

**path . isabsolut()方法**用于检查给定路径是否为绝对路径。绝对路径被定义为包含定位文件所需的完整细节的路径。

**语法:**

```
path.isAbsolute( path )
```

**参数:**该方法接受单参数**路径**，该路径保存用于检查其是否为绝对路径的文件路径。如果此参数不是字符串，将引发类型错误。

**返回值:**返回一个布尔值，表示路径是否为绝对路径。如果路径长度为零，则返回“false”。

下面的程序说明了 node.js 中的**path . isabsolut()方法**:

**例 1:**

```
// Node.js program to demonstrate the   
// path.isAbsolute() method

// Import the path module
const path = require('path');

path1 = path.isAbsolute("/user/bash/");
console.log(path1);

path2 = path.isAbsolute("user/bash/readme.md");
console.log(path2);

path3 = path.isAbsolute("/user/bash/readme.md");
console.log(path3);

path4 = path.isAbsolute("..");
console.log(path4);
```

**输出:**

```
true
false
true
false
```

**例 2:**

```
// Node.js program to demonstrate the   
// path.isAbsolute() method

// Import the path module
const path = require('path');

path1 = path.isAbsolute("\\user\\bash\\");
console.log(path1);

path2 = path.isAbsolute("user\\bash\\readme.md");
console.log(path2);

path3 = path.isAbsolute("\\user\\bash\\readme.md");
console.log(path3);

path4 = path.isAbsolute("..");
console.log(path4);
```

**输出:**

```
true
false
true
false
```

**参考:**T2】https://nodejs.org/api/path.html#path_path_isabsolute_path