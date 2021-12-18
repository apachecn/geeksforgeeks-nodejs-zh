# Node.js fs.writeSync()方法

> 原文:[https://www.geeksforgeeks.org/node-js-fs-writesync-method/](https://www.geeksforgeeks.org/node-js-fs-writesync-method/)

文件系统模块或 fs 模块是 Node js 中的一个内置模块，用于处理计算机上的文件。模块的功能可以通过导入 fs 模块来使用。文件系统模块的 fs.writeSync()函数是 write()方法的同步版本，可以将 fs 模块包含在程序中。它可以用于将文本和二进制数据写入文件。

**语法:**

```
fs.writeSync( fd, string, position, encoding )
```

或者

```
fs.writeSync( fd, buffer, offset, length, position )
```

**参数:**

*   **fd:** 代表文件描述符，它是一个标识文件的数字。我们可以使用 fs.openSync()方法，并在其中传递一个描述文件位置的字符串，它将返回一个整数，即文件描述符。
*   **字符串:**是将要写入文件的字符串。
*   **位置:**指定文件中要写入文本的位置。如果在方法中没有传递位置或者没有使用整数值来指定位置，那么它将从第 0 <sup>个</sup>位置开始写入。如果已经在该位置写入了字符串，则该方法将覆盖在该位置传递的新字符串。
*   **编码:**是指定字符编码的字符串。默认情况下，它是 utf8。
*   **缓冲区:**包含缓冲区类型值，如缓冲区、类型化数组、数据视图。
*   **偏移量:**是一个整数值，指定缓冲区中要写入文件的部分。
*   **长度:**是一个整数值，指定写入文件的字节数。

**返回值:**返回写入的字节数。

**示例:**

## index.js

```
// Importe fs module
const fs = require("fs");

// Create a file input.txt and open it
// using openSync
// The second parameter is the flag 
// which is r+ used for reading and 
// writing onto the file
// An exception occurs if the file does
// not exist.
// The method returns an integer which
// is the file descriptor fd
const fd = fs.openSync("input.txt", "r+");

// This text will be written on file input.text
const text = "Welcome to GeeksforGeeks";

// Starting position in file
const position = 0;

// writeSync returns number of bytes written
// on file which is stores in this variable
const numberOfBytesWritten = 
    fs.writeSync(fd, text, position, 'utf8');

console.log('File written successfully using writeSync()');

console.log(`Text written on file: ${text},
        starting from position: ${position}`);

console.log(`Number of Bytes written: 
        ${numberOfBytesWritten}`);
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**控制台输出:**

```
File written successfully using writeSync()
Text written on file: Welcome to GeeksforGeeks,starting from position: 0
Number of Bytes written: 24
```

**示例:**

## index.js

```
// Importing fs module
const fs = require("fs");

// open file using openSync in writing mode
// The file is created if it does not exist
// or truncated if it exists
// The method returns an integer which is
// the file descriptor fd
const fd = fs.openSync("binaryFile", "w");

// Create a buffer which will be written
// onto the file
const buffer = new Buffer.from(
    'GeeksforGeeks: A computer science portal for geeks');

// Starting position in file
const position = 0;

// writeSync returns number of bytes written
// on file which is stores in this variable
const numberOfBytesWritten = 
    fs.writeSync(fd, buffer, position, 50);

console.log('File written successfully using writeSync()');

console.log(`Buffer written on file: ${buffer},
            starting from position: ${position}`);

console.log(`Number of Bytes written: 
            ${numberOfBytesWritten}`);
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**控制台输出:**

```
File written successfully using writeSync()
Buffer written on file: GeeksforGeeks: A computer science portal for geeks
starting from position: 0
Number of Bytes written: 50
```

**参考:**

*   [https://nodejs . org/API/fs . html # fs _ fs _ write sync _ FD _ string _ position _ encoding](https://nodejs.org/api/fs.html#fs_fs_writesync_fd_string_position_encoding)
*   [https://nodejs . org/API/fs . html # fs _ fs _ write sync _ FD _ buffer _ offset _ length _ position](https://nodejs.org/api/fs.html#fs_fs_writesync_fd_buffer_offset_length_position)