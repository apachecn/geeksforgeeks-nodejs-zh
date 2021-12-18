# node . js fs . file handle . truncate()方法

> 原文:[https://www . geesforgeks . org/node-js-fs-file handle-truncate-method/](https://www.geeksforgeeks.org/node-js-fs-filehandle-truncate-method/)

**fs.filehandle.truncate()** 方法是**文件系统**模块中类 **fs.filehandle** 的内置应用程序编程接口，用于截断特定的文件对象，并且只保留在 truncate()方法中作为整数传递的那部分字节。

**语法:**

```js
const filehandle.truncate(len)
```

**参数:**该方法取该文件必须被截断的字节长度。
**返回值:**此方法返回一个不包含任何价值的待定承诺。

下面的程序说明了在 Node.js 中 **fs.filehandle.truncate()** 方法的使用:

**示例 1:** **文件名:index.js**

## java 描述语言

```js
// Node.js program to demonstrate the
// filehandle.truncate() method
const fs = require('fs');
const fsPromises = fs.promises;

// Initiating asyncrionise function
async function funct() {

    // Initializing following variables
    let filehandle = null;
    let prom = null;

    try {

        // Data before operation
        console.log("data before operation: " +
            fs.readFileSync('example.txt', 'utf8'));

        // Creating and initiating  filehandle
        filehandle = await
            fsPromises.open('example.txt', 'r+');

        // Truncating the file
        // by using truncate() method
        prom = filehandle.truncate(5);

    } finally {

        if (filehandle) {

            // Data after operation
            console.log("data after operation: " +
                fs.readFileSync('example.txt', 'utf8'));

            // Close the file if it is opened.
            await filehandle.close();
        }
    }
}

funct().catch(console.error);
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
data before operation: ABCDEFGHIJK
data after operation: ABCDE
```

**示例 2:** **文件名:index.js**

## java 描述语言

```js
// Node.js program to demonstrate the
// filehandle.truncate() method
const fs = require('fs');
const fsPromises = fs.promises;

// Data for the new file
let data = "This is a file containing "
            + "a collection of books.";

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

// Initiating asyncrionise function
async function funct() {

    // Initializing filehandle
    let filehandle = null;

    try {

        // Creating and initiating filehandle
        filehandle = await fsPromises.open(file, 'r+');

        // Truncating the file
        // by using truncate() method
        prom = filehandle.truncate(4);

    } finally {

        if (filehandle) {

            // Close the file if it is opened.
            console.log(
                "content of file after operation: "
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

```js
node index.js
```

**输出:**

```js
content of file before operation: 
  This is a file containing a collection of books.
content of file after operation: This
```

**注意**:以上程序不会在在线 JavaScript 和脚本编辑器上运行。
**参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/fs . html # fs _ file handle _ truncate _ len](https://nodejs.org/dist/latest-v12.x/docs/api/fs.html#fs_filehandle_truncate_len)