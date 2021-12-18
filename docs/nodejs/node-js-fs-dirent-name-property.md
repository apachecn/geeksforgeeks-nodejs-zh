# Node.js fs.dirent.name 属性

> 原文:[https://www . geesforgeks . org/node-js-fs-dirent-name-property/](https://www.geeksforgeeks.org/node-js-fs-dirent-name-property/)

**fs。属性是类 **fs 的内置应用编程接口。**文件系统**模块中的目录**，用于提供特定目录的名称。**

**语法:**

```js
const dirent.name
```

**参数:**该属性不接受任何参数。
**返回值:**该属性返回特定目录的名称。

下面的程序说明了**属性在 Node.js 中的使用:**

**示例 1:** **文件名:index.js**

## java 描述语言

```js
// Node.js program to demonstrate the
// dirent.name property
const fs = require('fs');

// Initiating asyn function
async function stop(path) {

    // Creating and initiating dir's
    // underlying resource handle
    const dir = await
        fs.promises.opendir(path);

    // Synchronously reading the dir's
    // underlying resource handle
    // using readSync() method
    for (var i = 0; i <= 6; i++) {

        // Checking if the particular
        // dirent is SymbolicLink or
        // not by using name() method
        const value = (dir.readSync()).name;

        // Display the result
        console.log(value);
    }
}

// Catching error
stop('./').catch(console.error);
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
abcd.cer
cert.cer
certfile.cer
certificate1.cer
example.txt
features
filename.txt
```

**示例 2:** **文件名:index.js**

## java 描述语言

```js
// Node.js program to demonstrate the
// dirent.name property
const fs = require('fs');

// Initiating asyn function
async function stop(path) {

    let dir = null;

    try {

        // Creating and initiating directory's
        // underlying resource handle
        dir = await fs.promises.opendir(
            new URL('file:///F:/java/'));

        // Synchronously reading the File's
        // underlying resource handle
        // using readSync() method
        for (var i = 0; i <= 3; i++) {

            // Checking if the particular dirent
            // is File or not by using isFile() method
            const value = (dir.readSync()).name;

            // Display the result
            console.log(dir.readSync());
            console.log(value);
        }
    } finally {

        if (dir) {

            // Display the result
            console.log("dir is closed successfully");

            // Synchronously closeSyncing the
            // directory's underlying resource handle
            const promise = dir.closeSync();
        }
    }
}

// Catching error
stop('./').catch(console.error);
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
Dirent { name: 'books.txt', [Symbol(type)]: 1 }
abcd.cer
Dirent { name: 'certfile.cer', [Symbol(type)]: 1 }
cert.cer
Dirent { name: 'example.com_index.html', [Symbol(type)]: 1 }
certificate1.cer
Dirent { name: 'features', [Symbol(type)]: 2 }
example.txt
```

**参考:**T2【https://nodejs . org/dist/latest-v 12 . x/docs/API/fs . html # fs _ dirent _ nameT4】