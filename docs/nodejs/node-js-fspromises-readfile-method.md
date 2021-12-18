# Node.js fsPromises.readFile()方法

> 原文:[https://www . geesforgeks . org/node-js-fspromises-read file-method/](https://www.geeksforgeeks.org/node-js-fspromises-readfile-method/)

使用 **fsPromises.readFile()** 方法读取文件。这个方法将整个文件读入缓冲区。要加载 fs 模块，我们使用 require()方法。它*异步*读取文件的全部内容。

**语法:**

```js
fsPromises.readFile( path, options )
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **Path:** It saves the name of the file to be read. If it is stored in another location, it saves the whole path. It is a string, buffer, web address or file name.
*   **Option** : Save the file code. Its default value is "utf8". It is an object or a string.
    *   **Code:** is a string or empty. Default: blank
    *   **Flag:** A string supporting the file system flag. Default value: "r".

**返回值:**返回承诺。

*   Promise to solve it with the contents of the document. If no encoding is specified (using options.encoding), the data will be returned as a buffer object. Otherwise, the data will be a string.
*   If the option is a string, it specifies the encoding.
*   When the path is a directory, the behavior of **fspromises.readfile ()** is platform specific. On *MAC OS, Linux and Windows,* promise will be rejected with errors. On FreeBSD, a representation of the contents of the directory will be returned.

下面的例子说明了 Node.js 中的 **fsPromises.readFile()** 方法:

创建一个演示文本文件，就像，我们已经创建了 **GFG.txt** 与以下文本:

```js
Greetings from GeeksforGeeks
```

**文件名:**

```js
// Node.js program to demonstrate 
// the fsPromises.readFile() method 

// Include fs module 
var fs = require('fs'); 
const fsPromises = require('fs').promises;

// Use fsPromises.readFile() method
// to read the file 
fs.promises.readFile("./GFG_Test.txt")
.then(function(result) {
  console.log(""+result);
})
.catch(function(error) {
   console.log(error);
})
```

**运行该程序的步骤:**从根目录运行以下命令，如下所示:

```js
node index.js
```

**输出:**

```js
Greetings from GeeksforGeeks
```

**参考:**[https://nodejs . org/API/fs . html # fs _ fspromises _ readfile _ path _ options](https://nodejs.org/api/fs.html#fs_fspromises_readfile_path_options)