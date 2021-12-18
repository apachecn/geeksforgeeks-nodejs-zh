# Node.js fs.filehandle.sync()方法

> 原文:[https://www . geesforgeks . org/node-js-fs-file handle-sync-method/](https://www.geeksforgeeks.org/node-js-fs-filehandle-sync-method/)

**fs.filehandle.sync()** 方法是**文件系统**模块中类 **fs.filehandle** 的内置应用编程接口，用于将该文件的内核状态与存储设备同步。
**语法:**

```js
const filehandle.sync()
```

**参数:**此方法不接受任何参数作为参数。
**返回值:**该方法返回一个不包含任何价值的待定承诺。
下面的程序说明了 **fs.filehandle.sync()** 方法的使用。
**示例 1:** **文件名:index.js**

## java 描述语言

```js
// Node.js program to demonstrate the
// filehandle.sync() method
const fs = require('fs');
const fsPromises = fs.promises;

console.log("content of file before operation :- "
        + (fs.readFileSync('example.txt')));

// Initiating asyncrionise function
async function funct() {

    // Initializing following variables
    let filehandle = null;
    let prom = null;

    try {

        // Creating and initiating filehandle
        filehandle = await
            fsPromises.open('example.txt', 'r+');

        // Synchronizing the file's in-core state
        // by using sync() method
        prom = filehandle.sync();

    } finally {

        if (filehandle) {

            // Display the result
            console.log("data is synchronized successfully");
            console.log("content of file after operation :- "
                    + (fs.readFileSync('example.txt')));

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
content of file before operation :- Content of file: example.txt
data is synchronized successfully
content of file after operation :- Content of file: example.txt
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
        console.log("content of file before"
            + " operation :- " +
            (fs.readFileSync(file)));
    }
});

// Initiating asyncrionise function
async function funct() {

    // Initializing filehandle
    let filehandle = null;

    try {

        // Creating and initiating filehandle
        filehandle = await
            fsPromises.open(file, 'r+');

        // Synchronizing the file's in-core
        // state by using sync() method
        prom = filehandle.sync();

    } finally {

        if (filehandle) {

            // Close the file if it is opened.
            console.log("data is synchronized"
                    + " successfully");

            console.log("content of file after"
                + " operation :- " +
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

> 操作前文件的内容:-这是一个包含书籍集合的文件。
> 数据同步成功
> 操作后文件内容:-这是一个包含藏书的文件。

**参考:**T2【https://nodejs . org/dist/latest-v 12 . x/docs/API/fs . html # fs _ file handle _ syncT4】