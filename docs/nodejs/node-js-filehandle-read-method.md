# Node.js filehandle.read()方法

> 原文:[https://www . geesforgeks . org/node-js-file handle-read-method/](https://www.geeksforgeeks.org/node-js-filehandle-read-method/)

**filehandle.read()** 方法使用文件描述符读取文件。为了读取没有文件描述符的文件，可以使用 filehandle 包的 readFile()方法。

Node.js 用于服务器端脚本。读取和写入文件是任何应用程序中执行的两个最重要的操作。Node.js 提供了广泛的内置功能来执行读写操作。fs 包包含文件操作所需的功能。

**语法:**

```
filehandle.read( buffer, offset, length, position );

```

**参数:**该函数接受上面提到的和下面描述的四个参数:

*   **Buffer:** Store the data obtained from the file. It is the buffer where data will be written.
*   **Offset:** The offset in the buffer, which indicates the position where writing begins.
*   **Length:** An integer that specifies the number of bytes to be read.
*   **Location:** An integer that specifies where to start reading in the file. Position is a parameter that specifies where in the file to start reading. If the location is empty, read the data from the current file location.

**返回值:**返回*承诺*。

**注意:**“gfg . txt”应出现在目录中，文本如下:

```
GeeksforGeeks - A computer science portal for geeks
```

**例:**

```
// Node.js program to demonstrate the
// Node.js filehandle.read() Method

// Import the filesystem module 
const fs = require('fs');
const fsPromises = fs.promises;

var buffer = new Buffer.alloc(1024);

console.log(fs.readFileSync('GFG.txt', 'utf8'));

// Using the async function to 
// ReadFile using filehandle
async function doRead() {
    let filehandle = null;

    try {
        // Using the filehandle method
        filehandle = await fsPromises
                    .open('GFG.txt', 'r+');

        // Calling the filehandle.read() method
        await filehandle.read(buffer,
                0, buffer.length, 0);
    } finally {
        if (filehandle) {

            // Close the file if it is opened.
            await filehandle.close();
        }
    }
}

doRead().catch(console.error);
```

使用以下命令运行 **app.js** 文件:

```
node app.js
```

**输出:**

```
GeeksforGeeks - A computer science portal for geeks
```