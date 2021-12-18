# Node.js fs.exists()方法

> 原文:[https://www.geeksforgeeks.org/node-js-fs-exists-method/](https://www.geeksforgeeks.org/node-js-fs-exists-method/)

**fs.exists()方法**是 **fs** 模块的一个内置应用编程接口，它提供了一个应用编程接口，用于以一种围绕标准 **POSIX** 函数紧密建模的方式与文件系统交互。 **fs.exists()方法**用于测试给定路径在文件系统中是否存在。

**语法:**

```
fs.exists( path, callback )
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **Path:** The path to test whether the directory exists. It can be a string, a buffer, etc.
*   **Callback:** is a callback function passed to the exists () method.

**返回值:**返回表示路径存在与否的**布尔值**。

**注:**现已弃用。

下面的例子说明了 **fs.exists()方法**在 Node.js 中的使用:

**例 1:**

```
// Node.js program to demonstrate the 
// fs.exists() method

var fs = require('fs');

// Using fs.exists() method
fs.exists('/etc/passwd', (exists) => {
  console.log(exists ? 'Found' : 'Not Found!');
});
```

**输出:**

```
Found

```

**例 2:**

```
// Node.js program to demonstrate the 
// fs.exists() method

var fs = require('fs');

// Using fs.exists() method
fs.exists('/etc/geeks', (exists) => {
    console.log(exists ? 'Found' : 'Not found!');
});
```

**输出:**

```
Not found!

```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/dist/latest-v 13 . x/docs/API/fs . html # fs _ fs _ exists _ path _ callback](https://nodejs.org/dist/latest-v13.x/docs/api/fs.html#fs_fs_exists_path_callback)