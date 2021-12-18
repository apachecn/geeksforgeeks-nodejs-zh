# Node.js fs.watchFile()方法

> 原文:[https://www.geeksforgeeks.org/node-js-fs-watchfile-method/](https://www.geeksforgeeks.org/node-js-fs-watchfile-method/)

**fs.watchFile()方法**用于持续观察给定文件的变化。它有一个回调侦听器，每次访问文件时都会调用它。它有一个可选的选项参数，可用于指定属性，如轮询文件的频率间隔，以及只要文件被监视，该过程是否会继续。

侦听器有两个参数，即当前 stat 对象和前一个 stat 对象。这可用于比较文件的更改。修改后的文件访问时间可以从文件系统中找到。Stat 对象的 mtime 属性。

在观看文件时，如果它消失了又重新出现，消失回调的 previousStat 将与外观回调的 previousStat 相同。当文件被重命名，然后第二次重命名回其原始名称时，就会出现这种情况。当文件被删除然后恢复时，也会发生这种情况。

**语法:**

```
fs.watchFile(filename[, options], listener)
```

**参数:**该方法接受三个参数，如上所述，如下所述:

1.  **文件名:**它是一个字符串、缓冲区或网址，表示要观看的文件的文件名。
2.  **选项:**是一个可以用来修改方法行为的对象。这是一个可选参数。它具有以下参数:
    *   **bigint:** 是一个布尔值，用于指定 fs 的数值。将对象作为 BigInt 值进行统计。默认值为假。
    *   **persistent:** 是一个布尔值，用于指定只要文件被监视，进程是否应该继续。默认值为真。
    *   **间隔:**是一个整数，指定每次轮询目标的时间间隔。它以毫秒为单位指定。默认值为 5007。
3.  **监听器:**是文件被访问或修改时调用的函数。
    *   **电流:**是 fs。Stats 对象，表示文件被访问或修改后的当前状态。
    *   **以前:**是 fs。Stats 对象，表示文件在被访问或修改之前的先前状态。

**返回值:**返回一个 fs。成功调用函数时的 StatWatcher 对象。

以下示例说明了 Node.js:
**示例 1:** 中的 **fs.watchFile()方法**本示例显示了 watchFile()方法及其参数的用法。

```
// Node.js program to demonstrate
// the fs.watchFile() method

// Import the filesystem module
const fs = require('fs');

fs.watchFile(

  // The name of the file to watch
  "example_file.txt",

  // The options parameter is used to 
  //modify the behaviour of the method
  {
    // Specify the use of big integers
    // in the Stats object 
    bigint: false,

    // Specify if the process should 
    // continue as long as file is
    // watched
    persistent: true,

    // Specify the interval between
    // each poll the file
    interval: 4000,
  },
  (curr, prev) => {
    console.log("\nThe file was edited");

    // Show the time when the file was modified
    console.log("Previous Modified Time", prev.mtime);
    console.log("Current Modified Time", curr.mtime);

    console.log(
      "The contents of the current file are:",
      fs.readFileSync("example_file.txt", "utf8")
    );
  }
);

// Make Changes to the file for the first time
fs.writeFileSync("example_file.txt",
   "File Contents are Edited");

// Make Changes to the file for the second time
setTimeout(
  () => fs.writeFileSync("example_file.txt",
          "File Contents are Edited Again"),
  5000
);
```

**输出:**

```
The file was edited
Previous Modified Time 2020-05-30T07:52:14.587Z
Current Modified Time 2020-05-30T08:01:40.948Z
The contents of the current file are: File Contents are Edited

The file was edited
Previous Modified Time 2020-05-30T08:01:40.948Z
Current Modified Time 2020-05-30T08:01:45.950Z
The contents of the current file are: File Contents are Edited Again

```

**示例 2:** 本示例显示了文件被重命名，然后又被重命名回其原始名称，导致文件消失和重新出现时的文件修改时间。

```
// Node.js program to demonstrate 
// the fs.watchFile() method

// Import the filesystem module
const fs = require('fs');

fs.watchFile("example_file.txt", (curr, prev) => {
  console.log("\nThe File was modified");
  console.log("Previous Modification Time", prev.mtime);
  console.log("Current Modification Time", curr.mtime);
});

// Renaming the file to a new name
setTimeout(
  () => fs.renameSync("example_file.txt",
           "new_file.txt"),
  1000
);

// Renaming the file back to its old name
setTimeout(
  () => fs.renameSync("new_file.txt", 
          "example_file.txt"),
  6000
);
```

**输出:**

```
Previous Modification Time 2020-05-30T08:01:45.950Z
Current Modification Time 1970-01-01T00:00:00.000Z

The File was modified
Previous Modification Time 2020-05-30T08:01:45.950Z
Current Modification Time 2020-05-30T08:01:45.950Z

```

**参考:**[https://nodejs . org/API/fs . html # fs _ fs _ watch file _ filename _ options _ listener](https://nodejs.org/api/fs.html#fs_fs_watchfile_filename_options_listener)