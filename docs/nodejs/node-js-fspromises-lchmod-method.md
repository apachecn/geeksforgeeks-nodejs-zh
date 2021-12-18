# Node.js fsPromises.lchmod()方法

> 原文:[https://www . geesforgeks . org/node-js-fspromiss-lch mod-method/](https://www.geeksforgeeks.org/node-js-fspromises-lchmod-method/)

**fsPromises.lchmod()** 方法用于更改给定路径的权限。这些权限可以使用对应于各自文件模式的字符串常量或八进制数来指定。

**注意:**这个方法只在 macOS 上实现。它更改文件的权限，然后在成功时无参数地解析承诺。

**语法:**

```
fsPromises.lchmod( path, mode)
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **路径:**它是一个字符串、缓冲区或网址，表示权限必须更改的文件的路径。
*   **模式:**是一个八进制**整数**常量，表示要授予的权限。逻辑或运算符可用于分隔多个权限。

**示例:**此示例说明了 Node.js:
中的 **fsPromises.lchmod()** 方法创建一个“example.txt”文件，用于向用户授予读取权限。

**文件名:index.js**

```
// Node.js program to demonstrate the 
// fsPromises.lchmod method 

// Import the filesystem module 
const fs = require('fs'); 
const fsPromises = fs.promises;

// Changing file permission to read only
fsPromises.lchmod('example.txt', 0o400)
.then(function() {
  console.log("File permission changed to read only!");

  try {
      fs.writeFileSync('x.txt','Hello World');
  }
  catch (e) {
    console.log(e.code);
  }
})
.catch(function(error) {
  console.log(error);
});
```

**运行该程序的步骤:**使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
File permission changed to read only!
EPERM

```

**参考:**[https://nodejs . org/API/fs . html # fs _ fspromises _ lcmod _ path _ mode](https://nodejs.org/api/fs.html#fs_fspromises_lchmod_path_mode)