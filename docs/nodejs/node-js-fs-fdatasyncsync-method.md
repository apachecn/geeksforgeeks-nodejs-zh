# node . js fs . fdatasync()方法

> 原文:[https://www . geesforgeks . org/node-js-fs-fdatasync-method/](https://www.geeksforgeeks.org/node-js-fs-fdatasyncsync-method/)

fs(文件系统)模块支持以标准 POSIX 函数为模型的方式与文件系统进行交互，这意味着我们可以使用计算机的文件系统执行输入/输出操作。比如从文件中读取数据，向文件中写入数据等。所有文件系统操作都有同步和异步形式，异步形式大多以完成回调作为最后一个参数。

fs.fdatasync()(在 v0.1.96 中添加)方法是 [fs.fdatasync()](https://www.geeksforgeeks.org/node-js-fs-fdatasync-method/) 的同步版本。

fs.fdatasync()方法是 fs(文件系统)模块的一个内置 API(应用程序编程接口)，它类似于 fs.fsync()方法，fs.fsync()将文件的所有修改数据传输(或刷新)到磁盘内存，以便即使系统崩溃或重新启动，也可以检索所有更改的信息，但是 fdatasync()方法不会传输或刷新修改的元数据，除非需要该元数据才能正确处理后续的数据写入/读取。

fdatasync()和 [fdatasync()](https://www.geeksforgeeks.org/node-js-fs-fdatasync-method/) 方法都可以减少不必要的磁盘活动。

**语法:**

```js
// Require fs module at the top of this .js file
const fs = require('fs');

fs.fdatasyncSync(fd);
```

**参数:**fs . fdatasync()方法只取一个参数。

*   **FD < Integer >** : This is an integer value.

**示例:**在 main.js 文件中，编写以下代码。

## Javascript

```js
// Node.js program to demonstrate the 
// fs.fdatasyncSync() method 

// Using require to access fs module 
const fs = require('fs'); 

// Data function which we'll write to data.js 
function data() { 
    console.log("Hi this is data function"); 
} 

// Open the file 
fs.open('data.js', "a+", (err, fd) => { 
    if (err) 
        throw err; 

    // Write our data 
    fs.writeFile(fd, data, (err) => { 

        // Checking error 
        if (err) 
            throw err; 

        // Force the file to be flushed 
        fs.fdatasyncSync(fd); //return undefined

        // Print after dataSync 
        console.log("Writing 'data' in 'data.js'... ") 
    }); 
});
```

使用**节点 main.js** 运行文件

**输出:**

```js
Writing 'data' in 'data.js'
```

**参考:**[https://nodejs . org/API/fs . html # fs _ fs _ fdatasyncsync _ FD](https://nodejs.org/api/fs.html#fs_fs_fdatasyncsync_fd)