# Node.js fs.watch()方法

> 原文:[https://www.geeksforgeeks.org/node-js-fs-watch-method/](https://www.geeksforgeeks.org/node-js-fs-watch-method/)

**fs.watch()方法**是 fs 模块的内置应用编程接口，用于持续观察给定文件或目录中的变化。它返回一个 fs。FSWatcher 对象，可用于跟踪文件中的更改。

它有一个可选的侦听器作为第三个参数，可用于获取发生的更改。这个侦听器有两个参数，一个是被修改的文件或目录的名称，另一个是修改的类型。在查看文件时，如果文件消失并重新出现，则会发出“重命名”事件，如果文件内容被修改，则会发出“更改”事件。

**注意:**此方法不可靠，每次修改可能会在监听器中显示多个事件。

**语法:**

```js
fs.watch( filename[, options][, listener] )
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **文件名:**它是一个字符串、缓冲区或网址，表示要监视的文件或目录的名称。
*   **选项:**是可以用来修改方法行为的字符串或对象。这是一个可选参数。它具有以下参数:
    *   **持久:**是一个布尔值，用于指定只要文件被监视，进程是否应该继续。默认值为真。
    *   **递归:**是一个布尔值，用于指定是否应该监视给定目录的所有子目录。默认值为假。
    *   **编码:**它是一个字符串，指定传递给侦听器的文件名所使用的字符编码。
*   **监听器:**是文件被访问或修改时调用的函数。这是一个可选参数。
    *   **事件类型:**它是一个字符串，指定文件经历的修改类型。
    *   **文件名:**它是一个字符串或缓冲区，指定触发事件的文件名。

**返回值:**返回一个 fs。成功调用函数时的 StatWatcher 对象。

下面的例子说明了 Node.js 中的 **fs.watch()方法**:

**示例 1:** 此示例显示了 watch()方法在文件上的用法。

## JavaScript

```js
// Node.js program to demonstrate the
// fs.watch() method

// Import the filesystem module
const fs = require('fs');

fs.watch("example_file.txt", (eventType, filename) => {
  console.log("\nThe file", filename, "was modified!");
  console.log("The type of change was:", eventType);
});

// Renaming the file to a new name
setTimeout(
  () => fs.renameSync("example_file.txt", "new_file.txt"),
  1000
);

// Renaming the file back to its old name
setTimeout(
  () => fs.renameSync("new_file.txt", "example_file.txt"),
  2000
);

// Changing the contents of the file 
setTimeout(
  () => fs.writeFileSync("example_file.txt", 
  "The file is modified"), 3000
);
```

**输出:**注意这个方法不可靠，每次修改可能会显示多个事件。

```js
The file example_file.txt was modified!
The type of change was: rename

The file example_file.txt was modified!
The type of change was: rename

The file example_file.txt was modified!
The type of change was: change

```

**示例 2:** 此示例显示了 watch()方法在目录中的用法。

## JavaScript

```js
// Node.js program to demonstrate the
// fs.watch() method

// Import the filesystem module
const fs = require('fs');

fs.watch("ex_dir", (eventType, filename) => {
  console.log("\nThe file", filename, "was modified!");
  console.log("The type of change was:", eventType);
});

// Changing the contents of a file 
setTimeout(
  () => fs.writeFileSync("ex_dir/ex1.txt", 
  "The file is modified"), 1000
);

// Renaming a file to a new name
setTimeout(
  () => fs.renameSync("ex_dir/ex2.txt", 
  "ex_dir/new_ex2.txt"), 2000
);
```

**输出:**注意这个方法不可靠，每次修改可能会显示多个事件。

```js
The file ex1.txt was modified!
The type of change was: change

The file ex2.txt was modified!
The type of change was: rename

The file new_ex2.txt was modified!
The type of change was: rename

```

**参考:**[**https://nodejs . org/API/fs . html # fs _ fs _ watch _ filename _ options _ listener**](https://nodejs.org/api/fs.html#fs_fs_watch_filename_options_listener)