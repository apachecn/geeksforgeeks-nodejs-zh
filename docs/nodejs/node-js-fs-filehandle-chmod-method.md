# Node.js fs.filehandle.chmod()方法

> 原文:[https://www . geesforgeks . org/node-js-fs-file handle-chmod-method/](https://www.geeksforgeeks.org/node-js-fs-filehandle-chmod-method/)

**fs.filehandle.chmod()** 方法是**文件系统**模块中类 **fs.filehandle** 的内置应用编程接口，用于更改特定文件的权限。

**语法:**

```js
const filehandle.chmod( mode )
```

**参数:**该方法接受保存整数值的单参数**模式**。
**返回值:**该方法返回一个不包含任何价值的待定承诺。

下面的程序说明了 **fs.filehandle.chmod()** 方法的使用。

**示例 1:** **文件名:index.js**

## java 描述语言

```js
// Node.js program to demonstrate the
// fs.filehandle.chmod() method
const fs = require('fs');
const fsPromises = fs.promises;

console.log("content of file before "
        + "operation :- " +
        (fs.readFileSync('example.txt')));

// Initiating asyncrionise function
async function funct() {

    // Initializing filehandle
    let filehandle = null;

    try {

        // Creating and initiating filehandle
        filehandle = await fsPromises
                .open('example.txt', 'r+');

        // Modifying the file permission
        // by using chmod() method
        const prom = filehandle.chmod(1);

    } finally {

        if (filehandle) {

            // Close the file if it is opened.
            console.log("permission is changed"
                        + " to read only");

            console.log("content of file before"
                    + " operation :- " +
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

```js
node index.js
```

**输出:**

> 操作前文件内容:-example . txt 文件内容
> 权限更改为只读
> 操作后文件内容:-example . txt 文件内容

**示例 2:** **文件名:index.js**

## java 描述语言

```js
// Node.js program to demonstrate the
// fs.filehandle.chmod() method
const fs = require('fs');
const fsPromises = fs.promises;

// data for the new file
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
        console.log("content of file "
            + "before operation :- " +
            (fs.readFileSync(file)));
    }
});

// Initiating asyncrionise function
async function funct() {

    // Initializing filehandle
    let filehandle = null;

    try {

        // Creating and initiating  filehandle
        filehandle = await fsPromises.open(file, 'r+');

        // Modifying the file permission
        // by using chmod() method
        const prom = filehandle.chmod(1);

    } finally {

        if (filehandle) {

            // Close the file if it is opened.
            console.log("permission is "
                + "changed to read only");

            console.log("content of file"
                + "after operation :- " +
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
> 操作后权限变为只读
> 文件内容:-这是一个包含藏书的文件。

**参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/fs . html # fs _ file handle _ chmod _ mode](https://nodejs.org/dist/latest-v12.x/docs/api/fs.html#fs_filehandle_chmod_mode)