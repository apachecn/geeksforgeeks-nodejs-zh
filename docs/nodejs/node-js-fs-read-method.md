# Node.js fs.read()方法

> 原文:[https://www.geeksforgeeks.org/node-js-fs-read-method/](https://www.geeksforgeeks.org/node-js-fs-read-method/)

Node.js 用于服务器端脚本。读取和写入文件是任何应用程序中执行的两个最重要的操作。Node.js 提供了广泛的内置功能来执行读写操作。fs 包包含文件操作所需的功能。fs 包的 read()方法使用文件描述符读取文件。为了读取没有文件描述符的文件，可以使用 fs 包的 readFile()方法。

**语法**

```
fs.read(fd, buffer, offset, length, position, callback)
```

**参数:**

*   **FD:**fs . open()方法返回的文件描述符。
*   **缓冲区:**存储从文件中提取的数据。
*   **偏移量:**缓冲区中的偏移量，指示从何处开始写入。
*   **长度:**指定要读取的字节数的整数。
*   **位置:**一个整数，指定从文件中的哪个位置开始读取。如果位置为空，则从当前文件位置读取数据。
*   **回调:**回调函数接受三个参数即。(错误，字节前导，缓冲区)。

**解释:**fs . open()方法打开文件并返回文件描述符。文件描述符是由内核存储在文件描述符表中的数字或索引，用于唯一标识计算机操作系统中打开的文件。fs.read()方法使用文件描述符读取文件并存储在缓冲区中。缓冲区的内容作为输出打印出来。fs.close()方法用于关闭文件。

**例 1:**

```
var fs = require("fs");
var buffer = new Buffer.alloc(1024);

console.log("Open existing file");
fs.open('gfg.txt', 'r+', function (err, fd) {
    if (err) {
        return console.error(err);
    }

    console.log("Reading the file");

    fs.read(fd, buffer, 0, buffer.length,
        0, function (err, bytes) {
            if (err) {
                console.log(err);
            }

            if (bytes > 0) {
                console.log(buffer.
                    slice(0, bytes).toString());
            }
            console.log(bytes + " bytes read");

            // Close the opened file.
            fs.close(fd, function (err) {
                if (err) {
                    console.log(err);
                }

                console.log("File closed successfully");
            });
        });
});
```

**输出:**

```
Open existing file
Reading the file
0 bytes read
File closed successfully

```

**例 2:** 对文件名/路径进行动态输入。

```
// Module required to accept user
// input from console
var readline = require('readline-sync');
var fs = require("fs");

var path = readline.question("Enter file path: ");
console.log("Entered path : " + path);

console.log("File Content ");

fs.stat(path, function (error, stats) {

    // 'r' specifies read mode
    fs.open(path, "r", function (error, fd) {
        var buffer = new Buffer.alloc(stats.size);
        fs.read(fd, buffer, 0, buffer.length,
            null, function (error, bytesRead, buffer) {
                var data = buffer.toString("utf8");
                console.log(data);
            });
    });
});
```

**输出:**

```
C:\Users\User\Desktop>node read3.js
Enter file path: new.txt
Entered path : new.txt
File Content
Hello World..
Welcome to GeeksForGeeks..
This is a Node.js program

```