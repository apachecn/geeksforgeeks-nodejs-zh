# Node.js fs。Dir.readSync()方法

> 原文:[https://www . geesforgeks . org/node-js-fs-dir-readsync-method/](https://www.geeksforgeeks.org/node-js-fs-dir-readsync-method/)

**fs。Dir.readSync()** 方法是类 **fs 的内置应用编程接口。**文件系统**模块中的目录**，用于读取目录的下一个目录。
**语法:**

```
const dir.readSync()
```

**参数:**此方法不接受任何参数。
**返回值:**此方法返回目录的方向。
以下程序说明了 **fs 的使用。Node.js 中的 Dir.readSync()** 方法:
**示例 1:**
**文件名:index.js**

## java 描述语言

```
// Node.js program to demonstrate the
// dir.readSync() method
const fs = require('fs');

// Initiating async function
async function stop(path) {

  // Creating and initiating directory's
  // underlying resource handle
  const dir = await fs.promises.opendir(path);

  // Synchronously reading the directory's
  // underlying resource handle
  const dirent = dir.readSync();

  // Display the result
  console.log(dirent.name);
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
abcd.cer
```

**示例 2:**
**文件名:index.js**

## java 描述语言

```
// Node.js program to demonstrate the
// dir.readSync() method
const fs = require('fs');

// Initiating asyn function
async function stop(path) {

  let dir = null;

  try {

  // Creating and initiating directory's
  // underlying resource handle
  dir = await fs.promises.opendir(
      new URL('file:///F:/java/'));

  // Synchronously reading the directory's
  // underlying resource handle
  // using readSync() method
  for(var i = 0 ; i <= 3 ; i ++ ) {
    var dirent = dir.readSync();

    // Display the result
    console.log(dirent.name);
  }

  } finally {

    if (dir) {

      // Display the result
      console.log("dir is closed successfully");

      // Synchronously closeSyncing the
      // directory's underlying resource
      // handle
      const promise = dir.closeSync()
    }
  }
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
abcd.cer
cert.cer
certfile.cer
certificate1.cer
dir is closed successfully
```

**参考:**T2【https://nodejs . org/dist/latest-v 12 . x/docs/API/fs . html # fs _ dir _ readsyncT4】