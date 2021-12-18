# Node.js fsPromises.writeFile()方法

> 原文:[https://www . geesforgeks . org/node-js-fspromiss-write file-method/](https://www.geeksforgeeks.org/node-js-fspromises-writefile-method/)

**fsPromises.writeFile()** 方法用于将指定的数据异步写入文件。默认情况下，如果文件存在，它将被替换。“选项”参数可用于修改方法的功能。

成功之后，承诺将会毫无争议地实现。

**语法:**

```js
fsPromises.writeFile( file, data, options )
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **File:** It is a string, Buffer, URL or file description integer, indicating the file path that must be written. Using the file descriptor will make it behave like the fsPromises.write () method.
*   **Data:** is the string, Buffer, TypedArray or DataView to be written into the file.
*   **Option:** is a string or object that can be used to specify optional parameters that affect output. It has three optional parameters:
    *   **Code:** is a string value that specifies the file code. The default value is utf8.
    *   **Mode:** An integer value that specifies the file mode. The default value is 0o666.
    *   **Flag:** It is a string value that specifies the flag used when writing to the file. The default value is "w".

**返回值:**该方法返回一个承诺。

下面的例子说明了 Node.js 中的**方法:**

**例 1:**

```js
// Node.js program to demonstrate the 
// fsPromises.writeFile() method 

// Import the filesystem module 
const fs = require('fs');
const fsPromises = require('fs').promises;
let data = "This is a file containing"
        + " a collection of movies.";

(async function main() {
    try {
        await fsPromises.writeFile(
                "movies.txt", data)

        console.log("File written successfully");
        console.log("The written file has"
            + " the following contents:");

        console.log("" + 
            fs.readFileSync("./movies.txt"));

    } catch (err) {
        console.error(err);
    }
})();
```

**输出:**

```js
File written successfully
The written file has the following contents:     
This is a file containing a collection of movies.

```

**例 2:**

```js
// Node.js program to demonstrate the 
// fsPromises.writeFile() method 

// Import the filesystem module 
const fs = require('fs');
const fsPromises = require('fs').promises;
let data = "This is a file containing"
        + " a collection of books.";

(async function main() {
    try {

        await fsPromises.writeFile(
                "books.txt", data, {
            encoding: "utf8",
            flag: "w",
            mode: 0o666
        });

        console.log("File written successfully\n");
        console.log("The written has the "
                + "following contents:");

        console.log("" + 
            fs.readFileSync("books.txt"));
    }
    catch (err) {
        console.error(err);
    }
})();
```

**输出:**

```js
File written successfully

The written has the following contents:
This is a file containing a collection of books.

```

**参考:**T2【https://nodejs . org/API/fs . html # fs _ fspromises _ write file _ file _ data _ options