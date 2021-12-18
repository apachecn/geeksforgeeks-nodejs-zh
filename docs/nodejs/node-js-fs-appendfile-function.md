# Node.js fs.appendFile()函数

> 原文:[https://www . geesforgeks . org/node-js-fs-append file-function/](https://www.geeksforgeeks.org/node-js-fs-appendfile-function/)

**fs.appendFile()方法**用于将给定数据异步追加到文件中。如果新文件不存在，则会创建一个新文件。options 参数可用于修改操作的行为。

**语法:**

```
fs.appendFile( path, data[, options], callback )
```

**参数:**该方法接受上面提到的四个参数，如下所述:

*   **Path:** It is a string, buffer, web address or number, which indicates the name of the source file or the file descriptor to be attached.
*   **Data:** is a character string or buffer that indicates the data that must be appended.
*   **Option:** is a string or object that can be used to specify optional parameters that affect output. There are three optional parameters:
    *   **Code:** is a string that specifies the file code. The default value is utf8.
    *   **Mode:** An integer that specifies the file mode. The default value is "0o666".
    *   **Flag:** It is a string that specifies the flag to be used when attaching to a file. The default value is "A".
*   **Callback:** is a function that will be called when the method is executed.
    *   **err:** If the method fails, this error will be thrown.

下面的例子说明了 Node.js 中的 **fs.appendFile()方法**:

**示例 1:** 该示例显示了给定文本到文件的追加。

```
// Node.js program to demonstrate the
// fs.appendFile() method

// Import the filesystem module
const fs = require('fs');

// Get the file contents before the append operation
console.log("\nFile Contents of file before append:",
  fs.readFileSync("example_file.txt", "utf8"));

fs.appendFile("example_file.txt", "World", (err) => {
  if (err) {
    console.log(err);
  }
  else {
    // Get the file contents after the append operation
    console.log("\nFile Contents of file after append:",
      fs.readFileSync("example_file.txt", "utf8"));
  }
});
```

**输出:**

```
File Contents of file before append: Hello

File Contents of file after append: HelloWorld

```

**示例 2:** 该示例显示了可选参数的用法，用于更改操作的文件编码、模式和标志。

```
// Node.js program to demonstrate the
// fs.appendFile() method

// Import the filesystem module
const fs = require('fs');

// Get the file contents before the append operation
console.log("\nFile Contents of file before append:",
  fs.readFileSync("example_file.txt", "utf8"));

fs.appendFile("example_file.txt", " - GeeksForGeeks",
  { encoding: "latin1", mode: 0o666, flag: "a" },
  (err) => {
    if (err) {
      console.log(err);
    }
    else {
      // Get the file contents after the append operation
      console.log("\nFile Contents of file after append:",
        fs.readFileSync("example_file.txt", "utf8"));
    }
  });
```

**输出:**

```
File Contents of file before append: This is a test file

File Contents of file after append: This is a test file - GeeksForGeeks

```

**参考:**T2【https://nodejs . org/API/fs . html # fs _ fs _ append file _ path _ data _ options _ callback