# Node.js fs.writeFile()方法

> 原文:[https://www.geeksforgeeks.org/node-js-fs-writefile-method/](https://www.geeksforgeeks.org/node-js-fs-writefile-method/)

**fs.writeFile()方法**用于将指定的数据异步写入文件。默认情况下，如果文件存在，它将被替换。“选项”参数可用于修改方法的功能。

**语法:**

```
fs.writeFile( file, data, options, callback )
```

**参数:**这个方法接受上面提到的和下面描述的四个参数:

*   **File:** It is a string, Buffer, URL or file description integer, indicating the path of the file to which it must be written. Using the file descriptor will make it behave like the fs.write () method.
*   **Data:** is the string, Buffer, TypedArray or DataView to be written into the file.
*   **Option:** is a string or object that can be used to specify optional parameters that affect output. It has three optional parameters:
    *   **Code:** is a string value that specifies the file code. The default value is utf8.
    *   **Mode:** An integer value that specifies the file mode. The default value is 0o666.
    *   **Flag:** It is a string value that specifies the flag used when writing to the file. The default value is "w".
*   **Callback:** is a function that will be called when the method is executed.
    *   **err:** The error that will be thrown if the operation fails.

下面的例子说明了 Node.js 中的 **fs.writeFile()方法**:

**例 1:**

```
// Node.js program to demonstrate the
// fs.writeFile() method

// Import the filesystem module
const fs = require('fs');

let data = "This is a file containing a collection of books.";

fs.writeFile("books.txt", data, (err) => {
  if (err)
    console.log(err);
  else {
    console.log("File written successfully\n");
    console.log("The written has the following contents:");
    console.log(fs.readFileSync("books.txt", "utf8"));
  }
});
```

**输出:**

```
File written successfully

The written has the following contents:
This is a file containing a collection of books.
```

**例 2:**

```
// Node.js program to demonstrate the
// fs.writeFile() method

// Import the filesystem module
const fs = require('fs');

let data = "This is a file containing a collection of movies.";

fs.writeFile("movies.txt", data,
  {
    encoding: "utf8",
    flag: "w",
    mode: 0o666
  },
  (err) => {
    if (err)
      console.log(err);
    else {
      console.log("File written successfully\n");
      console.log("The written has the following contents:");
      console.log(fs.readFileSync("movies.txt", "utf8"));
    }
});
```

**输出:**

```
File written successfully

The written has the following contents:
This is a file containing a collection of movies.
```

**参考:**T2【https://nodejs . org/API/fs . html # fs _ fs _ write file _ file _ data _ options _ callback