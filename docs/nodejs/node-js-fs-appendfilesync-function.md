# Node.js | fs.appendFileSync()函数

> 原文:[https://www . geesforgeks . org/node-js-fs-appendfilesync-function/](https://www.geeksforgeeks.org/node-js-fs-appendfilesync-function/)

**fs.appendFileSync()方法**用于将给定数据同步追加到文件中。如果新文件不存在，则会创建一个新文件。可选选项参数可用于修改操作的行为。

**语法:**

```js
fs.appendFileSync( path, data, options])
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **Path:** It is a string, buffer, web address or number, which indicates the name of the source file or the file descriptor to be attached.
*   **Data:** is a character string or buffer that indicates the data that must be appended.
*   **Option:** is a string or object that can be used to specify optional parameters that affect output. There are three optional parameters:
    *   **Code:** is a string that specifies the file code. The default value is utf8.
    *   **Mode:** An integer that specifies the file mode. The default value is "0o666".
    *   **Flag:** It is a string that specifies the flag to be used when attaching to a file. The default value is "A".

下面的例子说明了 Node.js 中的 **fs.appendFileSync()方法**:

**示例 1:** 该示例显示了给定文本到文件的追加。

```js
// Node.js program to demonstrate the
// fs.appendFileSync() method

// Import the filesystem module
const fs = require('fs');

// Get the file contents before the append operation
console.log("\nFile Contents of file before append:",
  fs.readFileSync("example_file.txt", "utf8"));

fs.appendFileSync("example_file.txt", " - Geeks For Geeks");

// Get the file contents after the append operation
console.log("\nFile Contents of file after append:",
       fs.readFileSync("example_file.txt", "utf8"));
```

**输出:**

```js
File Contents of file before append: Hello

File Contents of file after append: Hello - Geeks For Geeks

```

**示例 2:** 该示例显示了可选参数的用法，用于更改操作的文件编码和标志。“w”标志代替文件的内容，而不是附加到它上面。

```js
// Node.js program to demonstrate the
// fs.appendFileSync() method

// Import the filesystem module
const fs = require('fs');

// Get the file contents before the append operation
console.log("\nFile Contents of file before append:",
  fs.readFileSync("example_file.txt", "utf8"));

// Append to the file using optional parameters
fs.appendFileSync("example_file.txt",
  "This is the appended text",
  { encoding: "utf8", flag: "w" }
);

// Get the file contents after the append operation
console.log("\nFile Contents of file after append:",
       fs.readFileSync("example_file.txt", "utf8"));
```

**输出:**

```js
File Contents of file before append: This is a test file

File Contents of file after append: This is the appended text

```

**参考:**T2【https://nodejs . org/API/fs . html # fs _ fs _ appendfilesync _ path _ data _ options