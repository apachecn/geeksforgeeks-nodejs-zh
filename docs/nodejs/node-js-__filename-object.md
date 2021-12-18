# Node.js __filename 对象

> 原文:[https://www.geeksforgeeks.org/node-js-__filename-object/](https://www.geeksforgeeks.org/node-js-__filename-object/)

Node.js 中的**_ _ 文件名**返回被执行代码的文件名。它给出了代码文件的绝对路径。以下方法介绍了如何在 NodeJS 项目中实现 **__filename** 。

**语法:**

```
console.log(__filename)
```

**先决条件:**

*   Basic knowledge of node. js
*   Node.js is already installed (version 12+)
*   NPM installed (version 6+)

**返回值:**返回当前模块的绝对文件名。

**示例 1:** 创建一个 JavaScript 文件 *index.js* 并写下以下代码:

## index . js

```
// Node.js code to demonstrate the absolute
// file name of the current Module.
console.log("Filename of the current file is: ",
    __filename);
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
Filename of the current file is:  
  C:\Users\Pallavi\Desktop\node_func\app.js
```

**例 2:**

## index . js

```
// Node.js code to demonstrate the absolute
// file name of the current Module

console.log(__filename);

// To show to parts of file using filename.
const parts = __filename.split(/[\\/]/);
console.log( "This the all the parts "
    + "present in file :",parts);
```

**输出:**

```
C:\Users\Pallavi\Desktop\node_func\app.js
This the all the parts present in file : 
  [ 'C:', 'Users', 'Pallavi', 'Desktop', 
  'node_func', 'app.js' ]
```

**参考:**T2】https://nodejs.org/api/globals.html#globals_filename