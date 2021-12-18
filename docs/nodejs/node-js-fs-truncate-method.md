# Node.js fs.truncate()方法

> 原文:[https://www.geeksforgeeks.org/node-js-fs-truncate-method/](https://www.geeksforgeeks.org/node-js-fs-truncate-method/)

node.js 中的 **fs.truncate()方法**用于改变文件的大小，即增加或减少文件大小。这个方法通过 len 字节改变文件在路径上的长度。如果 len 表示的长度比文件的当前长度短，文件将被截断到该长度。如果大于文件长度，则通过附加空字节(x00)来填充，直到达到 len。

**语法:**

```js
fs.truncate( path, len, callback )
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **Path:** The path to save the target file. It can be a string, buffer or url.
*   **len:** It saves the length of the file, after which the file will be truncated. It accepts integer input and is not mandatory because it is set to 0 by default.
*   **Callback:** Callback receives a parameter and throws any exception in the call.

**注意:**在 node.js 最新版本中，回调不再是可选参数。如果我们不使用回调参数，那么它将在运行时返回“类型错误”。

**返回值:**将所需文件的长度改为所需长度。

**例 1:**

```js
// Node.js program to demonstrate the
// fs.truncate() method

// Include the fs module
var fs = require('fs');

// Completely delete the content
// of the targeted file
fs.truncate('/path/to/file', 0, function() {
    console.log('File Content Deleted')
});
```

**输出:**

```js
File Content Deleted
```

**例 2:**

```js
// Node.js program to demonstrate the
// fs.truncate() method

// Include the fs module
var fs = require('fs');

console.log("Content of file");

// Opening file
fs.open('input.txt', 'r+', function(err, fd) {
    if (err) {
        return console.error(err);
    }

    // Reading file
    fs.read(fd, buf, 0, buf.length, 0, function(err, bytes){
        if (err){
            console.log(err);
        }

        // Truncating the file
        fs.truncate('/path/to/file', 15, function(err, bytes){
            if (err){
                console.log(err);
            }

            // Content after truncating
            console.log("New content of file");
            fs.read(fd, buf, 0, buf.length, 0, function(err, bytes){
                if (err) {
                    console.log(err);
                }

                // Print only read bytes to avoid junk.
                if(bytes > 0) {
                    console.log(buf.slice(0, bytes).toString());
                }

                // Close the opened file.
                fs.close(fd, function(err) {
                    if (err) {
                        console.log(err);
                    }
                });
            });
        });
    });
});
```

**输出:**

```js
Content of file
GeeksforGeeks example for truncate in node
New content of file
GeeksforGeeks
```

**参考:**[https://nodejs . org/API/fs . html # fs _ fs _ ftuncate _ FD _ len _ callback](https://nodejs.org/api/fs.html#fs_fs_ftruncate_fd_len_callback)