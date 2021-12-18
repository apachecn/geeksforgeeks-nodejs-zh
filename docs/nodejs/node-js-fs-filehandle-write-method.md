# Node.js fs.filehandle.write()方法

> 原文:[https://www . geesforgeks . org/node-js-fs-file handle-write-method/](https://www.geeksforgeeks.org/node-js-fs-filehandle-write-method/)

**fs.filehandle.write()** 方法是**文件系统**模块中类 **fs.filehandle** 的内置应用程序编程接口，用于将缓冲区中的数据写入该特定文件。
**语法:**

```js
const filehandle.write(buffer[, offset[, length[, position]]])
```

**参数:**该方法取以下参数:

*   **缓冲器:**提供需要存储的数据的缓冲器。
*   **偏移量:**缓冲区中的起点。
*   **长度:**要写入的字节数。
*   **位置:**文件的开始点。

**返回值:**该方法返回一个待定承诺，该承诺包含缓冲区和描述写入字节数的 bytesWritten 属性。
下面的程序说明了 **fs.filehandle.write()** 方法在 Node.js:
**中的使用示例 1:** **文件名:index.js**

## java 描述语言

```js
// Node.js program to demonstrate the
// filehandle.write() method
const fs = require('fs');
const fsPromises = fs.promises;

console.log("file before write operation :- "
    + fs.readFileSync('example.txt', 'utf8'));

// Initiating asyncrionise function
async function funct() {

    // Initializing following variables
    let filehandle = null;
    let prom = null;
    let buffer = Buffer.from('Geeks');

    try {

        // Creating and initiating filehandle
        filehandle = await
            fsPromises.open('example.txt', 'r+');

        // Writting the file by using
        // write() method
        prom = filehandle.write(
                buffer, 0, buffer.length, 0);

    } finally {

        if (filehandle) {

            // Display the result
            prom.then(function (result) {
                console.log(
                    "file after write operation :- "
                    + (result.buffer).toString());
            })

            // Close the file if it is opened.
            await filehandle.close();
        }
    }
}

funct().catch(console.error);
```

运行程序前的目录结构:

![](img/01f73ba41511f0178722008f0b80ab52.png)

运行程序后的目录结构:

![](img/01f73ba41511f0178722008f0b80ab52.png)

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
file before write operation :- Geeks for Geeks
file after write operation :- Geeks
```

**示例 2:** **文件名:index.js**

## java 描述语言

```js
// Node.js program to demonstrate the
// filehandle.sync() method
const fs = require('fs');
const fsPromises = fs.promises;

// Data for the new file
let data = "This is a file containing"
        + " a collection of books.";

// Name of the file to be created
let file = "books.txt";

// Creating the new file 'books.txt'
fs.writeFile(file, data, (err) => {

    // Cathing error
    if (err) {
        console.log(err);
    }
});

// Using fs.exists() method
fs.exists(file, (exists) => {
    if (exists) {
        console.log(
            "content of file before operation :- "
            + (fs.readFileSync(file)));
    }
});

// Initiating asyncrionise function
async function funct() {

    // Initializing filehandle
    let filehandle = null;

    // Initializing following variables
    let buffer = Buffer.from('ABCD');

    try {

        // Creating and initiating  filehandle
        filehandle = await
            fsPromises.open(file, 'r+');

        // Writting the file
        // by using write() method
        prom = filehandle.write(
            buffer, 0, buffer.length, 0);

    } finally {

        if (filehandle) {

            // Display the result
            prom.then(function (result) {
                console.log(
                    "file after write operation :- "
                    + (result.buffer).toString());
            })

            await filehandle.close();
        }
    }
}

funct().catch(console.error);
```

运行程序前的目录结构:

![](img/01f73ba41511f0178722008f0b80ab52.png)

运行程序后的目录结构:

![](img/0ecf2ff4cf6c5de99b63f81df99f18a4.png)

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
content of file before operation :- 
  This is a file containing a collection of books.
file after write operation :- ABCD
```

**参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/fs . html # fs _ file handle _ write _ buffer _ offset _ length _ position](https://nodejs.org/dist/latest-v12.x/docs/api/fs.html#fs_filehandle_write_buffer_offset_length_position)