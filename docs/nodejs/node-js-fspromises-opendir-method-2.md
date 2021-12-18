# Node.js fsPromises.opendir()方法

> 原文:[https://www . geesforgeks . org/node-js-fspromises-opendir-method-2/](https://www.geeksforgeeks.org/node-js-fspromises-opendir-method-2/)

**fsPromises.opendir()** 方法是在 Node.js 的 File System 模块中定义的，File System 模块基本上就是和用户电脑的硬盘进行交互。方法用于异步打开目录。
**fspromise . opendir()**方法返回已解决或已拒绝的承诺，从而避免了在 fs.opendir()中可能出现的回调嵌套或回调地狱问题。承诺通过' fs '解决。对象，该对象本身包含用于访问和关闭目录的其他功能。如果承诺被拒绝，它将被拒绝，并带有一个错误对象。
**语法:**

```js
fs.promises.opendir(path, options)
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **路径:**它是一个字符串、缓冲区或 Url，用于指定必须打开的目录的路径。
*   **选项:**它是一个可选参数，以某种方式影响输出，并相应地将其提供给函数调用或不提供。
    *   **编码:**指定编码技术，默认为‘UTF8’
    *   **bufferSize:** 它是一个数字，指定从目录读取时内部缓冲的目录条目数。bufferSize 值高，可确保良好的性能，但会导致更多的内存使用。

**返回值:**这个方法返回一个用‘fs’解析的承诺。对象，该对象本身包含用于访问和关闭目录的其他功能。如果承诺被拒绝，它将被拒绝，并带有一个错误对象。
**【迪尔】对象方法:**

*   **dir.close()方法:**它异步关闭目录的资源，因此后续尝试读取将导致错误。将返回一个承诺，该承诺将在资源关闭后得到解决。
*   **dir.closeSync()方法:**它同步关闭目录的资源，因此后续尝试读取将导致错误。
*   **目录路径:**返回目录的路径。
*   **dir.read()方法:**异步读取下一个目录条目。读取完成后，将返回一个承诺，该承诺将使用 fs 进行解析。Dirent，如果不再读取目录，则为 null。

**例 1:**

## java 描述语言

```js
// Node.js program to demonstrate the  
// fsPromises.opendir() Method

// Importing File System module
const fs = require('fs')

fs.promises.opendir('./test1')
    .then(dir => {
        console.log('Directory is opened')

        // Path to the directory
        console.log(
        `Path to the directory: ${dir.path}`)

        // Closing directory
        return dir.close()
    })

    .then(() => {
        console.log('Directory closed')

        console.log('\nFurther attempt to'
            + ' read sub-directories\n')

        // Further attempt to access the
        // directory results in error
        return dir.read()
    })

    .then(dirent => {

        // Does not execute since directory
        // is closed catch block runs instead
        console.log(dirent)
    })
    .catch(err => {
        console.log('Error, Something went wrong!')
    })
```