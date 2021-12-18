# Node.js filehandle.readFile()方法

> 原文:[https://www . geesforgeks . org/node-js-file handle-read file-method/](https://www.geeksforgeeks.org/node-js-filehandle-readfile-method/)

**filehandle.readFile()方法**用于异步读取文件内容。此方法将整个文件读入缓冲区。它异步读取文件的全部内容。

**语法:**

```js
filehandle.readFile( options )
```

**参数:**该方法如上所述接受单个参数，如下所述:

*   **Option:** Code of the saved file. Its default value is "utf8". It is an object or a string.
    *   **Code:** is a string or empty. Default: blank

**返回值:**返回一个*承诺。*

*   *Commitment* will be solved by the contents of the document. If the encoding is not specified with options.encoding, the data will be returned as a buffer object. Otherwise, the data will be a string.
*   If the option is a string, specify the encoding.
*   **The file handle** must support reading.

**示例:**读取文件‘gfg . txt’的文件内容

**注意:**“gfg . txt”应出现在目录中，并带有以下文本:

```js
GeeksforGeeks - A computer science portal for geeks
```

**文件名:app.js**

```js
// Node.js program to demonstrate the   
// fsPromises.truncate() Method

// Import the filesystem module 
const fs = require('fs');
const fsPromises = fs.promises;

// Using the async function to
// ReadFile using filehandle
async function doReadFile() {
    let filehandle = null;
    try {

        // Using the filehandle method
        filehandle = 
        await fsPromises.open('GFG.txt', 'r+');

        var data = 
        await filehandle.readFile("utf8");

        console.log(data);
    } catch (e) {
        console.log("Error", e);
    }
}

doReadFile().catch((error) => {
    console.log("Error", error)
});
```

使用以下命令运行 **app.js** 文件:

```js
node app.js
```

**输出:**

```js
GeeksforGeeks - A computer science portal for geeks
```

**参考:**T2】https://nodejs . org/dist/latest-v 14 . x/docs/API/fs . html # fs _ file handle _ readfile _ options