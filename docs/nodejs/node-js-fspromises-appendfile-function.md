# node . js fspromises . appendfile()函数

> 原文:[https://www . geesforgeks . org/node-js-fspromiss-append file-function/](https://www.geeksforgeeks.org/node-js-fspromises-appendfile-function/)

**fsPromises.appendFile()** 方法用于将给定数据异步追加到文件中。如果新文件不存在，则会创建一个新文件。options 参数可用于修改操作的行为。

**语法:**

```js
fsPromises.appendFile( path, data, options )
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **Path:** It is a string, buffer, web address or number, which indicates the name of the source file or the file descriptor to be attached.
*   **Data:** is a character string or buffer that indicates the data that must be appended.
*   **Option:** is a string or object that can be used to specify optional parameters that affect output. It has three optional parameters:
    *   **Code:** is a string that specifies the file code. The default value is utf8.
    *   **Mode:** An integer that specifies the file mode. The default value is "0fso666".
    *   **Flag:** It is a string that specifies the flag to be used when attaching to a file. The default value is "A".

**返回值:**返回*承诺。*

**示例:**本示例使用名为“example_file”的示例 txt 文件，其中包含 *Hello* 文本。

**文件名:index.js**

```js
// Node.js program to demonstrate the 
// fsPromises.appendFile() method 

// Import the filesystem module 
const fs = require('fs'); 
const fsPromises = fs.promises;

// Get the file contents before the append operation  
console.log("\nFile Contents of file before append:", 
fs.readFileSync("example_file.txt", "utf8")); 

fsPromises.appendFile("example_file.txt", "GeeksforGeeks")
.then(function(){
     console.log("\nFile Contents of file after append:", 
     fs.readFileSync("example_file.txt", "utf8"))
})
.catch( function (err) { console.log(err); });
```

**注意:**用下面的命令运行 *index.js* 文件:

```js
node index.js
```

**输出:**

```js
File Contents of file before append: Hello
File Contents of file after append: HelloGeeksforGeeks
```

**注意:**如果选项是字符串，则指定编码。该路径可以被指定为一个*文件句柄*，该文件句柄已经被打开以进行附加(使用 **fsPromises.open()** )。