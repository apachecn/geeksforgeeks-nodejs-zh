# Node.js fs.readFile()方法

> 原文:[https://www.geeksforgeeks.org/node-js-fs-readfile-method/](https://www.geeksforgeeks.org/node-js-fs-readfile-method/)

**fs.readFile()方法**是一种用于读取文件的内置方法。这个方法将整个文件读入缓冲区。要加载 fs 模块，我们使用 **require()** 方法。例如:var fs = require(' fs ')；

**语法:**

```js
fs.readFile( filename, encoding, callback_function )
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **文件名:**保存要读取的文件的名称，如果存储在其他位置，则保存整个路径。
*   **编码:**保存文件的编码。其默认值为**‘utf8’**。
*   **回调 _ 函数:**是读取文件后调用的回调函数。它需要两个参数:
    *   **错误:**如果出现任何错误。
    *   **数据:**文件内容。

**返回值:**返回文件中存储的内容/数据或错误(如有)。
以下示例说明了 Node.js 中的 fs.readFile()方法:
**示例 1:**

## java 描述语言

```js
// Node.js program to demonstrate
// the fs.readFile() method

// Include fs module
var fs = require('fs');

// Use fs.readFile() method to read the file
fs.readFile('Demo.txt', 'utf8', function(err, data){

    // Display the file content
    console.log(data);
});

console.log('readFile called');
```