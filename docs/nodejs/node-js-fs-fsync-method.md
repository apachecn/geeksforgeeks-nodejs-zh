# Node.js fs.fsync()方法

> 原文:[https://www.geeksforgeeks.org/node-js-fs-fsync-method/](https://www.geeksforgeeks.org/node-js-fs-fsync-method/)

在节点中，“文件系统”模块提供了一个应用编程接口，用于以一种围绕标准可移植操作系统接口(POSIX)函数紧密建模的方式与文件系统进行交互。

它有同步和异步两种形式。异步表单总是将完成回调作为最后一个参数。传递给完成回调的参数取决于方法，但第一个参数总是为异常保留。如果操作成功完成，则第一个参数将为 null 或未定义。fs.fsync()方法是一种异步形式。将文件与存储在计算机上的文件同步。

**语法:**

```
fs.fsync(fd, callback);
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **FD:** is a file descriptor (integer) obtained synchronously.
*   **Callback:** is a callback function to check whether there is an error.

**返回值:**该函数不返回值。

**示例 1:** **文件名:index.js**

```
// Requiring module
const fs = require('fs');

// Opening a file
const fd = fs.openSync('example.txt', 'r+');

// Function call
fs.fsync(fd, (err) => {
    if(err) {
        console.log(err);
    } else {
        console.log("FD:",fd);
    }
})
```

**输出:**

```
FD: 3

```

**示例 2:** **文件名:**

```
// Requiring modules
const fs = require('fs');
const express = require('express');
const app = express();

const fd = fs.openSync('example.txt', 'r+');

app.get('/', (req, res) =>{
});

// Function call
fs.fsync(fd, (err) => {
    if(err) {
        console.log(err)
    } else { 
        console.log("FD:",fd)
    }
});

// Server setup
app.listen(3000, function(error){
    if (error) console.log("Error")
    console.log("Server listening to port 3000")
})
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
Server listening to port 3000
FD: 3

```

**参考:**[https://nodejs . org/API/fs . html # fs _ fs _ fssync _ FD _ callback](https://nodejs.org/api/fs.html#fs_fs_fsync_fd_callback)