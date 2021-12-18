# Node.js process.chdir()方法

> 原文:[https://www.geeksforgeeks.org/node-js-process-chdir-method/](https://www.geeksforgeeks.org/node-js-process-chdir-method/)

**process.chdir()方法**是流程模块的内置应用编程接口，用于更改当前工作目录。

**语法:**

```
process.chdir( directory )
```

**参数:**该方法接受如上所述的单个参数，如下所述:

*   **Directory:** is a required option to specify the directory path to which the current working directory is to be changed.

**返回值:**该方法成功时不返回值，但如果未能更改指定“没有此类文件或目录”的目录，则抛出异常。

下面的例子说明了 **process.chdir()方法**在 Node.js 中的使用:

**例 1:**

```
// Node.js program to demonstrate the     
// process.chdir() Method

// Include process module
const process = require('process');

try {

  // Change the directory
  process.chdir('../os');
  console.log("directory has successfully been changed");
} catch (err) {

  // Printing error if occurs
  console.error("error while changing directory");
}
```

**输出:**

```
directory has successfully been changed

```

**例 2:**

```
// Node.js program to demonstrate the     
// process.chdir() Method

// Include process module
const process = require('process');

// Printing current directory
console.log("current working directory: "
          + process.cwd());
try {

  // Change the directory
  process.chdir('../os');
  console.log("working directory after "
          + "changing: " + process.cwd());
} catch (err) {

  // Printing error if occurs
  console.error("error occured while "
        + "changing directory: " + err);
}
```

**输出:**

```
current working directory: C:\nodejs\g\process
working directory after changing: C:\nodejs\g\os

```

**注意:**以上程序使用`node filename.js`命令编译运行。

**参考:**[https://nodejs . org/API/process . html # process _ process _ chdir _ directory](https://nodejs.org/api/process.html#process_process_chdir_directory)