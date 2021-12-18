# Node.js fsPromises.mkdir()方法

> 原文:[https://www . geesforgeks . org/node-js-fspromises-mkdir-method/](https://www.geeksforgeeks.org/node-js-fspromises-mkdir-method/)

**fsPromises.mkdir()** 方法用于异步创建一个目录，然后解析**promises**，如果递归为真，则解析第一个创建的目录路径。

**语法:**

```
fsPromises.mkdir(path, options)
```

**参数:**该方法接受两个参数，如上所述，如下所述:

1.  **Path:** This parameter is a String, Buffer or URL, which holds the path of the directory that must be created.
2.  **option: is** an object or an integer?
    *   **Recursion:** This parameter holds a recursive Boolean value. By default, it is false.
    *   **mode:** mode option is used to set directory permissions, and the default is 0777\. Is it a string or an integer

**返回值:**它返回*承诺*对象，该对象表示异步操作的最终完成(或失败)及其结果值。

下面的例子说明了 Node.js 中 **fsPromises.mkdir()** 方法的使用

**例:**

```
// Node.js program to demonstrate 
// the fsPromises.mkdir() Method 

// Include fs and path module 
const fs = require('fs');
const fsPromises = fs.promises;

fsPromises.mkdir('fs_test2').then(function() {
    console.log('Directory created successfully');
}).catch(function() {
    console.log('failed to create directory');
});
```

**输出:**

```
Directory created successfully!
```