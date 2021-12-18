# Node.js fsPromises.copyFile()方法

> 原文:[https://www . geesforgeks . org/node-js-fspromiss-copy file-method/](https://www.geeksforgeeks.org/node-js-fspromises-copyfile-method/)

**fsPromises.copyFile()** 方法用于将文件从*源*路径异步复制到*目的地*路径。默认情况下，如果目标路径已经存在，则会被覆盖。*承诺*将在成功后毫无争议地解决。

**语法:**

```js
fsPromises.copyFile( src, dest, flags )
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **src:** 它是一个字符串、缓冲区或网址，表示要复制的源文件名。
*   **dest:** 它是一个字符串、缓冲区或网址，表示复制操作将创建的目标文件名。
*   **标志:**是复制操作的数字修饰符。默认值为 0。*标志*是指定复制操作行为的可选整数。可以创建一个由两个或多个值的按位“或”组成的掩码。
    1.  **fs . constants . copy file _ EXCO:**如果目标已经存在，复制操作将失败。
    2.  **fs . constants . copyfile _ FICLONE:**复制操作将尝试创建写时复制 reflink。如果平台不支持写入时拷贝，则使用回退拷贝机制。
    3.  **fs . constants . copyfile _ FICLONE _ FORCE:**复制操作将尝试创建一个写时复制 reflink。如果平台不支持写入时复制，则操作将失败。

**返回值:** *承诺*。 *Promise* 对象表示异步操作的最终完成(或失败)及其结果值。

在给定目录下创建一个 **original.txt** 文件，执行以下方法。此示例显示了如果没有给出*标志*，则将 **original.txt** 文件复制到**copy . txt**文件的操作。

**文件名:index.js**

```js
// Node.js program to demonstrate the 
// fsPromises.copyFile() method 

// Import the filesystem module 
const fs = require('fs'); 
const fsPromises = require('fs').promises;

fsPromises.copyFile("original.txt", "copied.txt")
.then(function() {
  console.log("File Copied");
})
.catch(function(error) {
  console.log(error);
});
```

**运行该程序的步骤:**
使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
File Copied
```

现在可以看到**复制的. txt** 文件是在你当前的根目录下创建的。

**参考:**[https://nodejs . org/API/fs . html # fs _ fspromises _ copy file _ src _ dest _ mode](https://nodejs.org/api/fs.html#fs_fspromises_copyfile_src_dest_mode)