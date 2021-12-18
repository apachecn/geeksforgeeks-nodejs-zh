# Node.js fsPromises.truncate()方法

> 原文:[https://www . geesforgeks . org/node-js-fspromiss-truncate-method/](https://www.geeksforgeeks.org/node-js-fspromises-truncate-method/)

node.js 中的 **fsPromises.truncate()** 方法用于更改文件的大小，即增加或减少文件大小。这个方法通过 len 字节改变文件在路径上的长度。如果 len 表示的长度比文件的当前长度短，文件将被截断到该长度。如果大于文件长度，则通过附加空字节(x00)来填充，直到达到 len。

然后，它解决了*承诺*没有争论成功。路径必须是*字符串*或*缓冲区。*

**语法:**

```js
fsPromises.truncate( path, len )
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **路径:**保存目标文件的路径。它可以是字符串、缓冲区或 url。
*   **len:** 保存文件的长度，之后文件会被截断。它接受整数输入，并且不是强制条件，因为它默认设置为 0。

**返回值:**此方法返回承诺。

**示例:**此示例说明了 Node.js 中 **fsPromises.truncate()** 方法的工作原理:

在当前根目录下创建一个 **Hello.txt** 文件，包含如下示例文本:

```js
Greetings from GeeksforGeeks
```

**文件名:index.js**

## java 描述语言

```js
// Node.js program to demonstrate the 
// fsPromises.truncate() method 

// Include the fs module 
var fs = require('fs'); 
var fsPromises = fs.promises;

fsPromises.truncate('Hello.txt', 0) 
.then(function() {
    console.log("File Content Deleted");
})
.catch(function(error) {
    console.log("Error",error);
});
```

**运行该程序的步骤:**使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
File Content Deleted
```

**参考:**T2T4】