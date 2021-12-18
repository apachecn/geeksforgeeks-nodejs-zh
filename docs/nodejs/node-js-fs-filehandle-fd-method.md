# Node.js fs.filehandle.fd()方法

> 原文:[https://www . geesforgeks . org/node-js-fs-file handle-FD-method/](https://www.geeksforgeeks.org/node-js-fs-filehandle-fd-method/)

**fs.filehandle.fd()** 方法是**文件系统**模块中类 **fs.filehandle** 的内置应用编程接口，用于提供该文件句柄对象的数字文件描述符。
**语法:**

```
const filehandle.fd()
```

**参数:**此方法不接受任何参数。
**返回值:**这个方法返回这个文件句柄对象的数字文件描述符。
下面的程序说明了 **fs.filehandle.fd()** 方法在 Node.js:
**中的使用示例 1:** **文件名:index.js**

## java 描述语言

```
// Node.js program to demonstrate the
// filehandle.fd() method
const fs = require('fs');
const fsPromises = fs.promises;

console.log("content of file before operation :- "
            + (fs.readFileSync('example.txt')));

// Initiating asyncrionise function
async function funct() {

    // Initializing filehandle
    let filehandle = null;
    let value = null;

    try {

        // Creating and initiating  filehandle
        filehandle = await
            fsPromises.open('example.txt', 'r+');

        // Getting the Numeric file descriptor
        // by using fd api
        value = filehandle.fd;

    } finally {

        if (filehandle) {

            // Close the file if it is opened.
            console.log(
                "Numeric file descriptor :- " + value);
            console.log(
                "content of file after operation :- " +
                (fs.readFileSync('example.txt')));

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

```
node index.js
```

**输出:**

```
content of file before operation :- ABCD
Numeric file descriptor :- 3
content of file after operation :- ABCD
```

**示例 2:**
**文件名:index.js**

## java 描述语言

```
// Node.js program to demonstrate the
// filehandle.fd() method
const fs = require('fs');
const fsPromises = fs.promises;

// Data for the new file
let data = "This is a file containing "
            + "a collection of books.";

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
        console.log("content of file "
            + "before operation :- "
            + (fs.readFileSync(file)));
    }
});

// Initiating asyncrionise function
async function funct() {

    // Initializing filehandle
    let filehandle = null;

    try {

        // Creating and initiating  filehandle
        filehandle = await
                fsPromises.open(file, 'r+');

        // Getting the Numeric file descriptor
        // by using fd api
        value = filehandle.fd;

    } finally {

        if (filehandle) {

            // Close the file if it is opened.
            console.log(
                "Numeric file descriptor :- "
                + value);

            console.log("content of file "
                + "after operation :- "
                + (fs.readFileSync(file)));

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

```
node index.js
```

**输出:**

```
content of file before operation :- This is a file containing a collection of books.
Numeric file descriptor :- 4
content of file after operation :- This is a file containing a collection of books.
```

**参考:**T2【https://nodejs . org/dist/latest-v 12 . x/docs/API/fs . html # fs _ file handle _ FDT4】