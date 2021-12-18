# Node.js fs。目录路径()方法

> 原文:[https://www.geeksforgeeks.org/node-js-fs-dir-path-method/](https://www.geeksforgeeks.org/node-js-fs-dir-path-method/)

**fs。Dir.path()** 方法是类 **fs 的内置应用编程接口。**文件系统**模块中的**目录，用于获取目录的路径。
**语法:**

```
const dir.path
```

**参数:**此方法不接受任何参数。
**返回值:**此方法返回目录的路径。
以下程序说明了 **fs 的使用。Dir.path()** 方法。
**示例 1:** **文件名:index.js**

## java 描述语言

```
// Node.js program to demonstrate the
// dir.path() method
const fs = require('fs');

// Initiating async function
async function stop(path) {

    // Creating and initiating directory's
    // underlying resource handle
    const dir = await fs.promises.opendir(path);

    console.log("All the dirent before operation :- ");

    for (var i = 0; i <= 2; i++) {
        console.log(((dir.readSync())).name);
    }

    // Getting the path of the directory
    // by using path() method
    const pathval = dir.path;

    console.log("All the dirent after operation :- ");

    for (var i = 0; i <= 2; i++) {
        console.log(((dir.readSync())).name);
    }

    // Display the result
    console.log("\nPath :- " + pathval);
}

// Catching error
stop('./').catch(console.error);
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
All the dirent before operation :- 
books.txt
datastore.json
example.txt
All the dirent after operation :-
index.js
node_modules
package-lock.json

Path :- ./
```

**示例 2:** **文件名:index.js**

## java 描述语言

```
// Node.js program to demonstrate the
// dir.path() method
const fs = require('fs');
const fsPromises = fs.promises;

// Name of the directory to be created
let directo = './temp';

// Checking if the directory is
// present or not
if (!fs.existsSync(directo)) {
    fs.mkdirSync(directo);
}

// Initiating asyncrionise function
async function funct(path) {

    // Initializng dir
    let dir = null;
    let pathval = null;

    try {

        // Creating and initiating directory's
        // underlying resource handle
        dir = await fs.promises.opendir('./');

        console.log("All the dirent before operation :- " +
            ((dir.readSync())));

        // Getting the path of the directory
        // by using path() method
        pathval = dir.path;

    } finally {

        if (dir) {

            // Close the file if it is opened.
            console.log("Path :- " + pathval);

            console.log("All the dirent after operation :- " +
                ((dir.readSync())));
            await dir.close();
        }
    }
}

funct('./').catch(console.error);
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
All the dirent before operation :- [object Object]
Path :- ./
All the dirent after operation :- [object Object]
```

**参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/fs . html # fs _ dir _ path](https://nodejs.org/dist/latest-v12.x/docs/api/fs.html#fs_dir_path)