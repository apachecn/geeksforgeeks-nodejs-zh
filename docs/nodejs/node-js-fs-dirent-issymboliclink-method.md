# Node.js fs。Dirent.isSymbolicLink()方法

> 原文:[https://www . geesforgeks . org/node-js-fs-dirent-issymboliclin-method/](https://www.geeksforgeeks.org/node-js-fs-dirent-issymboliclink-method/)

**fs。方法是类 **fs 的内置应用编程接口。**文件系统**模块中的目录**，用于检查特定目录是否描述了符号链接。** 

**语法:**

```
const dirent.isSymbolicLink()
```

**参数:**此方法不接受任何参数。
**返回值:**如果特定方向描述了一个符号，则该方法返回真，否则返回假。
下面的程序说明了**fs . dirent . issymboliclin()**方法在 Node.js:
**中的使用示例 1:**
**文件名:index.js**

## java 描述语言

```
// Node.js program to demonstrate the
// dirent.isSymbolicLink() method
const fs = require('fs');

// Initiating asyn function
async function stop(path) {

  // Creating and initiating dir's
  // underlying resource handle
  const dir = await fs.promises.opendir(path);

  // Synchronously reading the dir's
  // underlying resource handle
  // using readSync() method
  for(var i = 0; i <= 3; i ++ ) {

    // Checking if the particular dirent
    // is SymbolicLink or not by using
    // isSymbolicLink() method
    const value = (dir.readSync()).isSymbolicLink();

    // Display the result
    console.log(dir.readSync());
    console.log(value);
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
Dirent { name: 'cert.cer', [Symbol(type)]: 1 }
false
Dirent { name: 'certificate1.cer', [Symbol(type)]: 1 }
false
Dirent { name: 'filename.txt', [Symbol(type)]: 1 }
false
Dirent { name: 'GFG.java', [Symbol(type)]: 1 }
false
```

**示例 2:**
**文件名:index.js**

## java 描述语言

```
// Node.js program to demonstrate the
// dirent.isSymbolicLink() method
const fs = require('fs');

// Initiating asyn function
async function stop(path) {

  let dir = null;

  try {

    // Creating and initiating directory's
    // underlying resource handle
    dir = await fs.promises.opendir(
        new URL('file:///F:/java/'));

    // Synchronously reading the dir's
    // underlying resource handle
    // using readSync() method
    for(var i = 0; i <= 3; i ++ ) {

      // Checking if the particular dirent
      // is SymbolicLink or not by using
      // isSymbolicLink() method
      const value = (dir.readSync()).isSymbolicLink();

      // Display the result
      console.log(dir.readSync());
      console.log(value);
    }
  } finally {

    if (dir) {

      // Display the result
      console.log("dir is closed successfully");

      // Synchronously closeSyncing the directory's
      // underlying resource handle
      const promise = dir.closeSync();
    }
  }
}

// Catching error
stop('./').catch(console.error);
```

**输出:**

```
Dirent { name: 'cert.cer', [Symbol(type)]: 1 }
false
Dirent { name: 'certificate1.cer', [Symbol(type)]: 1 }
false
Dirent { name: 'features', [Symbol(type)]: 2 }
false
Dirent { name: 'GFG.class', [Symbol(type)]: 1 }
false
dir is closed successfully
```

**参考:**T2【https://nodejs . org/dist/latest-v 12 . x/docs/API/fs . html # fs _ dirent _ issymboleling