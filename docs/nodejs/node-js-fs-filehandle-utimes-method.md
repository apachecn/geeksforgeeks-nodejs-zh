# Node.js fs.filehandle.utimes()方法

> 原文:[https://www . geesforgeks . org/node-js-fs-file handle-utimes-method/](https://www.geeksforgeeks.org/node-js-fs-filehandle-utimes-method/)

**fs.filehandle.utimes()** 方法是**文件系统**模块内 **fs.filehandle** 类的内置应用编程接口，用于更改该文件系统的时间戳。

**语法:**

```js
const filehandle.utimes(atime, mtime)
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **atime:** 访问时间戳是上次读取文件的时间。
*   **时间点:**修改时间戳表示文件内容最后一次被修改的时间。

**返回值:**此方法返回一个未决的承诺，其中不包含任何值。

下面的程序说明了 **fs.filehandle.utimes()** 方法在 Node.js 中的使用:

**示例 1:** **文件名:index.js**

## java 描述语言

```js
// Node.js program to demonstrate the
// filehandle.utimes() method
const fs = require('fs');
const fsPromises = fs.promises;

console.log("content of the file before operation :- "
        + fs.readFileSync('example.txt', 'utf8'));

// File cTime before operation
fs.stat('example.txt', (err, stats) => {
    if (err) throw err;

    console.log("CTime of the file before operation: "
                    + stats.ctime);
});

// Initiating asyncrionise function
async function funct() {

    // Initializing following variables
    let filehandle = null;
    let prom = null;

    try {

        // Creating and initiating  filehandle
        filehandle = await
            fsPromises.open('example.txt', 'r+');

        // Changing the timestamp of the file
        // by using utimes() method
        prom = filehandle.utimes(0, 10);

    } finally {

        if (filehandle) {

            // File cTime after operation
            (filehandle.stat(true))
                        .then(function (result) {
                console.log("CTime of the file "
                        + "after operation :- "
                        + result.ctime);
            })

            console.log("content of the file "
                    + "after operation : " +
                fs.readFileSync('example.txt', 'utf8'));

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

> 操作前文件内容:example.txt 文件内容
> 操作前文件 CTime:2020 年 07 月 07 日星期二 09:21:11 GMT+0530(印度标准时间)
> 操作后文件内容:example.txt 文件内容
> 操作后文件 CTime:-2020 年 07 月 07 日星期二 09:53:15 GMT+0530(印度标准时间)

**示例 2:** **文件名:index.js**

## java 描述语言

```js
// Node.js program to demonstrate the
// filehandle.utimes() method
const fs = require('fs');
const fsPromises = fs.promises;

// Data for the new file
let data = "This is a file containing"
        + " a collection of books.";

// Name of the file to be created
let file = "books.txt";

// Creating the new file 'books.txt'
fs.writeFile(file, data, (err) => {

    // Catching error
    if (err) {
        console.log(err);
    }
});

// Using fs.exists() method
fs.exists(file, (exists) => {
    if (exists) {
        console.log(
            "content of file before operation: "
            + (fs.readFileSync(file)));
    }
});

// File cTime before operation
fs.stat(file, (err, stats) => {
    if (err) throw err;

    console.log(
        "CTime of the file before operation: "
        + stats.ctime);
});

// Initiating asyncrionise function
async function funct() {

    // Initializing filehandle
    let filehandle = null;

    try {

        // Creating and initiating  filehandle
        filehandle = await
            fsPromises.open(file, 'r+');

        // Changing the timestamp of the file
        // by using utimes() method
        prom = filehandle.utimes(0, 20);

    } finally {

        if (filehandle) {

            // Close the file if it is opened.
            // file cTime after operation
            (filehandle.stat(true))
                    .then(function (result) {
                console.log("CTime of the file "
                        + "after operation :- "
                        + result.ctime);
            })

            console.log("content of file after"
                + " operation: " +
                (fs.readFileSync(file)));

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

> 操作前文件的内容:这是一个包含书籍集合的文件。
> 操作前文件 CTime:2020 年 07 月 07 日星期二 09:56:52 GMT+0530(印度标准时间)
> 操作后文件内容:这是一个包含藏书的文件。
> 运行后文件时间:2020 年 07 月 07 日星期二 09:57:09 格林尼治标准时间+0530(印度标准时间)

**参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/fs . html # fs _ file handle _ utimes _ atime _ mtime](https://nodejs.org/dist/latest-v12.x/docs/api/fs.html#fs_filehandle_utimes_atime_mtime)