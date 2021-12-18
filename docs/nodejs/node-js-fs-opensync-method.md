# Node.js fs.openSync()方法

> 原文:[https://www.geeksforgeeks.org/node-js-fs-opensync-method/](https://www.geeksforgeeks.org/node-js-fs-opensync-method/)

**fs.openSync()方法**是 fs 模块的内置应用编程接口，用于返回代表文件描述符的整数值。

**语法:**

```js
fs.openSync( path, flags, mode )
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **Path:** The path to save the file. Its type is string, buffer or web address.
*   **Flag:** It holds strings or numerical values. Its default value is "r".
*   **mode:** Save the string or integer value, with the default value of 0o666.

**返回值:**返回一个代表文件描述符的数字。

下面的例子说明了 **fs.openSync()方法**在 Node.js 中的使用:

**例 1:**

```js
// Node.js program to demonstrate the     
// fs.openSync() method  

// Including fs module
var fs = require('fs');

// Defining filename
var filename = './myfile';

// Calling openSync method
// with its parameters
var res = fs.openSync(filename, 'r');

// Prints output
console.log(res);
```

**输出:**

```js
23

```

这里，标志“r”表示文件已经被创建，它读取创建的文件。

**例 2:**

```js
// Node.js program to demonstrate the     
// fs.openSync() method  

// Including fs module
var fs = require('fs');

// Defining path
var path = require('path');

// Calling openSync method with
// all its parameters
var fd = fs.openSync(path.join(
    process.cwd(), 'input.txt'), 'w', 0o666);

// This will append the content
// of file created above
fs.writeSync(fd, 'GeeksforGeeks');

// Setting timeout
setTimeout(function () {

  // Its printed after the file is closed
  console.log('closing file now');

  // closing file descriptor
  fs.closeSync(fd);
}, 10000);
console.log("Program done!");
```

**输出:**

```js
Program done!
closing file now

```

这里，标记“w”表示文件被创建或覆盖。

**参考:**[https://nodejs . org/API/fs . html # fs _ fs _ opensync _ path _ flags _ mode](https://nodejs.org/api/fs.html#fs_fs_opensync_path_flags_mode)