# 如何从 node.js 中的一个文件返回一个行数组？

> 原文:[https://www . geeksforgeeks . org/如何从节点中的文件返回行数组-js/](https://www.geeksforgeeks.org/how-to-return-an-array-of-lines-from-a-file-in-node-js/)

在本文中，我们将使用 node.js 从指定的文件中返回一个行数组。fs 模块用于处理 node.js 中的文件系统，并读取文件数据，我们使用 **fs.readFileSync( )** 或 **fs.readFile( )** 方法。这里我们将使用 readFileSync 方法读取文件，我们使用下面的步骤以数组的形式返回文件的行:

*   Use the **fs. Readfilesync** method to read the data of the file, and you will get a buffer.
*   Use **tostring ()** method.
*   Convert the buffer into a string. Now use the **string.split ()** method to disconnect the data, and the separator should be "\"

下面是我们实现上述步骤的示例:

## index . js

```
// Requiring the fs module
let fs = require("fs")

// Creating a function which takes a file as input
const readFileLines = filename =>
  fs
    .readFileSync(filename)
    .toString('UTF8')
    .split('\n');

// Driver code
let arr = readFileLines('gfg.txt');

// Print the array
console.log(arr);
```

**文本文件:**gfg . txt 文件。

```
Geeksforgeeks
A computer Science Portal for Geeks
```

使用以下命令运行代码:

```
node index.js
```

**输出:**

```
[
  'Geeksforgeeks',
  'A computer Science Portal for Geeks'
]
```