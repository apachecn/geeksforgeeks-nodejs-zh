# Node.js fs。Dir.closeSync()方法

> 原文:[https://www . geesforgeks . org/node-js-fs-dir-close sync-method/](https://www.geeksforgeeks.org/node-js-fs-dir-closesync-method/)

**fs。Dir.closeSync()** 方法是类 **fs 的内置应用编程接口。**文件系统**模块中的目录**，用于同步关闭目录的底层资源句柄。

**语法:**

```
const dir.closeSync()
```

**参数:**此方法不接受任何参数。
**返回值:**这个方法返回一个未定义的对象

下面的程序说明了 **fs 的使用。Dir.closeSync()** 方法。

**例 1:**

**文件名:index.js**

## java 描述语言

```
// Node.js program to demonstrate the
// dir.closeSync() method
const fs = require('fs');

// Initiating async function
async function stop(path) {

  // Creating and initiating directory's
  // underlying resource handle
  const dir = await fs.promises.opendir(path);

  console.log("All the dirent before operation :- ");
  for (var i = 0; i <= 6; i++) {
     console.log(((dir.readSync())).name);
  }

  // Synchronously closeSyncing the directory's
  // underlying resource handle
  const promise = dir.closeSync();

  // Display the result
  console.log("dir is closed successfully");
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
abcd.cer
books.txt
cert.cer
certfile.cer
certificate1.cer
example.txt
features
dir is closed successfully
```

**例 2:**

**文件名:index.js**

## java 描述语言

```
// Node.js program to demonstrate the
// dir.closeSync() method
const fs = require('fs');
const fsPromises = fs.promises;

// Name of the directory to be created
let directo = './temp';

// Checking if the directory is present or not
if (!fs.existsSync(directo)){
  fs.mkdirSync(directo);
}

// Initiating asynchronous function
async function funct(path) {

  // Initializing dir
  let dir = null;
  let pathval = null;

  try {

   // Creating and initiating directory's
   // underlying resource handle
   dir = await fs.promises.opendir(
      new URL('file:///F:/java/temp'));

   console.log("All the dirent before operation :- "
                 + ((dir.readSync())));

   // Getting the path of the directory
   // by using path() method
   pathval = dir.path;

  } finally {

    if (dir) {

      // Close the file if it is opened.
      console.log("Path :- " + pathval);

      console.log("All the dirent before operation :- "
                          + ((dir.readSync())));

      console.log("dir is closed successfully");

      await dir.closeSync();  
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
Path :- F:
All the dirent before operation :- [object Object]
dir is closed successfully
```

**参考:**T2【https://nodejs . org/dist/latest-v 12 . x/docs/API/fs . html # fs _ dir _ close sync