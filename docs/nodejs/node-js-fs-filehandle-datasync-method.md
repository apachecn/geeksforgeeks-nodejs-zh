# node . js fs . file handle . datasync()方法

> 原文:[https://www . geesforgeks . org/node-js-fs-file handle-datasync-method/](https://www.geeksforgeeks.org/node-js-fs-filehandle-datasync-method/)

**fs.filehandle.datasync()** 方法是**文件系统**模块内 **fs.filehandle** 类的内置应用编程接口，用于同步文件的数据。

**语法:**

```
const filehandle.datasync()
```

**参数:**此方法不接受任何参数。
**返回值:**该方法返回一个不包含任何价值的待定承诺。

下面的程序说明了 **fs.filehandle.datasync()** 方法的使用。

**示例 1:** **文件名:index.js**

## java 描述语言

```
// Node program to demonstrate the
// filehandle.datasync() method
const fs = require('fs');
const fsPromises = fs.promises;

console.log("File content before operation: "
        + (fs.readFileSync('example.txt')));

// Initiating asyncrionise function
async function funct() {

    // Initializing filehandle
    let filehandle = null;

    try {

        // Creating and initiating  filehandle
        filehandle = await
            fsPromises.open('example.txt', 'r+');

        // Syncing the data by using
        // datasync() method
        await filehandle.datasync();

    } finally {

        if (filehandle) {

            // Close the file if it is opened.
            console.log("data synced successfully");
            console.log("Content after operation: "
                + (fs.readFileSync('example.txt')));

            await filehandle.close();
        }
    }
}

funct().catch(console.error);
```

程序目录结构:

![](img/01f73ba41511f0178722008f0b80ab52.png)

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
File content before operation: Content of the example.txt file
data synced successfully
Content after operation: Content of the example.txt file
```

**示例 2:** **文件名:index.js**

## java 描述语言

```
// Node.js program to demonstrate the
// filehandle.datasync() method
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
        console.log("content of file before"
                + " operation: " +
                (fs.readFileSync(file)));
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

        // Syncing the data by using
        // datasync() method
        await filehandle.datasync();

    } finally {

        if (filehandle) {

            // Close the file if it is opened.
            console.log("data synced successfully");
            console.log("content of file after"
                + " operation: " +
                (fs.readFileSync(file)));

            await filehandle.close();
        }
    }
}

funct().catch(console.error);
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
content of file before operation: This is a file containing a collection of books.
data synced successfully
content of file after operation: This is a file containing a collection of books.
```

运行程序前的目录结构:

![](img/01f73ba41511f0178722008f0b80ab52.png)

运行程序后的目录结构:

![](img/0ecf2ff4cf6c5de99b63f81df99f18a4.png)

**参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/fs . html # fs _ file handle _ datasync](https://nodejs.org/dist/latest-v12.x/docs/api/fs.html#fs_filehandle_datasync)