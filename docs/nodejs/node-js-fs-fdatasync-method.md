# Node.js fs.fdatasync()方法

> 原文:[https://www.geeksforgeeks.org/node-js-fs-fdatasync-method/](https://www.geeksforgeeks.org/node-js-fs-fdatasync-method/)

*fs* 模块提供了一个应用编程接口，用于以一种围绕标准 POSIX 函数紧密建模的方式与文件系统交互。所有文件系统操作都有同步和异步形式，异步形式大多以完成回调作为最后一个参数。

**fs.fdatasync()** (在 v0.1.96 中添加)方法是 *fs* 模块的内置应用程序编程接口，类似于 *fs.fsync()，*它减少了不需要所有元数据与磁盘同步的应用程序的磁盘活动。需要元数据来允许正确处理后续数据检索，因为它不会刷新已修改的元数据。

**语法:**

```
fs.fdatasync(fd, callback);
```

可以使用

```
const fs = require('fs');
```

访问“ *fs* 模块

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **fd** < *整数* > **:** 此参数接受< *整数* >类型值。
*   **回调** < *函数* > **:此参数需要一个回调函数，谨防嵌套回调或回调地狱。**
    *   **错误** < *错误* > **:如果回调函数处理不当，**抛出错误。

**示例 1:** **文件名:index . js**

## Javascript

```
// Node.js program to demonstrate the 
// fs.fdatasync() method 

// Using require to access fs module 
const fs = require('fs');

// Basic demo of fs.fdatasync
fs.fdatasync(1, err => {
    if (err) {
        console.log('error', err);
    }
    else {
        console.log('no-error');
    }
    console.log("Data Sync...");
})

// alfa function
function alfa() {
    console.log("Printing callback in "
        + "console from callback alfa... ");
    return "hiii";
}
function data() {
    console.log("Printing callback in "
        + "console from data... ");
}

// Open the file
fs.open('filename.txt', "a+", (err, fd) => {
    if (err)
        throw err;

    // Write our data
    fs.writeFile(fd, data, (err) => {

        // checking error
        if (err)
            throw err;

        // Force the file to be flushed
        fs.fdatasync(fd, function alfa(err) {
            if (err)
                throw err
        });
        fs.fdatasync(5, data);

        // print after dataSync
        console.log("Writing 'data' in 'filename.txt'... ")
    });
});
```

运行 **index.js** 文件使用以下命令:

```
node index.js
```

**输出:**

```
error [Error: EBADF: bad file descriptor, fdatasync] {
  errno: -4083,
  code: 'EBADF',
  syscall: 'fdatasync'
}
Data Sync...
Writing 'data' in 'filename.txt'...       
Printing callback in console from data... 
```

**参考:**[https://nodejs.org/api/fs.html#fs_fs_fdatasync_fd_callback](https://nodejs.org/api/fs.html#fs_fs_fdatasync_fd_callback)

T30】