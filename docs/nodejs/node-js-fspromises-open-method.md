# Node.js fsPromises.open()方法

> 原文:[https://www . geesforgeks . org/node-js-fspromises-open-method/](https://www.geeksforgeeks.org/node-js-fspromises-open-method/)

**fsPromises.open()** 方法用于异步打开一个文件，该文件返回一个 *Promise* ，解析后产生一个*文件句柄*对象。

**语法:**

```js
fsPromises.open( filename, flags, mode)
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **File name:** It is a string, buffer or web address that holds the name or the entire path of the file to be read (if stored in another location).
*   **Flag:** It is a string or a number, which gives the operation of which file must be opened. "r" by default.
*   **mode:** is a string or an integer. Set the file mode, namely r: read, w: write and r+: read and write. It is set to read and write by default.

**返回值:**返回承诺。

下面的例子说明了 Node.js 中的 **fsPromises.open()** 方法:

**例:**

```js
// Node.js program to demonstrate the     
// fsPromises.open() Method 

// Include the fs module 
var fs = require('fs'); 
var fsPromises = fs.promises;

// Open file Demo.txt in read mode 
fsPromises.open('Demo.txt', 'r')
.then((result)=>{
    console.log(result);
})
.catch((error)=>{
    console.log(error);
});
```

**输出:**

```js
FileHandle { [Symbol(handle)]: FileHandle { fd: 3 } }
```

**说明:**文件打开，标志设置为读取模式。打开文件后，调用函数读取文件内容并存储在内存中。

**注意:** *模式*设置文件模式(权限和粘性位)，但前提是文件是创建的。

部分字符(< >:/\ |？*)保留在 Windows 下，如命名*文件、路径、*和*命名空间所记录的。*