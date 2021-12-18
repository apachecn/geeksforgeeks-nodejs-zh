# 如何在 Node.js 中操作带有承诺的基于回调的 fs.opendir()方法？

> 原文:[https://www . geesforgeks . org/操作方法-基于回调的-fs-opendir-带节点承诺的方法-js/](https://www.geeksforgeeks.org/how-to-operate-callback-based-fs-opendir-method-with-promises-in-node-js/)

**fs.opendir()** 方法是在 Node.js 的 File System 模块中定义的，File System 模块基本上就是和用户电脑的硬盘进行交互。用于异步打开目录的方法。
fs . opendir()方法是基于回调的。使用回调方法导致回调嵌套或回调地狱问题的可能性很大。因此，为了避免这种情况，我们几乎总是喜欢使用基于承诺的方法。使用一些额外的 node.js 方法，我们可以用 promise 方式操作一个基于回调的方法。承诺通过' fs '解决。对象，该对象本身包含用于访问和关闭目录的其他功能。如果承诺被拒绝，它将被拒绝，并带有一个错误对象。
**语法:**

```js
fs.opendir(path, options)
```

**注意:**不需要回调，因为我们是用承诺的方式操作的。
**参数:**如上所述接受两个参数路径和选项。选项是可选参数。

*   **路径:**它是一个字符串、缓冲区或 Url，用于指定必须打开的目录的路径。
*   **选项:**它是一个可选参数，以某种方式影响输出，并相应地将其提供给函数调用或不提供。
    *   **编码:**指定编码技术，默认为‘UTF8’
    *   **bufferSize:** 它是一个数字，指定从目录读取时内部缓冲的目录条目数。bufferSize 值高，可确保良好的性能，但会导致更多的内存使用。

**返回:**如果方法使用承诺操作，它将返回一个用“fs”解析的承诺。对象，该对象本身包含用于访问和关闭目录的其他功能。如果承诺被拒绝，它将被拒绝，并带有一个错误对象。
**【迪尔】对象方法:**

*   **dir.close():** 它异步关闭目录的资源，因此后续尝试读取将导致错误。将返回一个承诺，该承诺将在资源关闭后得到解决。
*   **dir.closeSync()** :它同步关闭目录的资源，因此后续尝试读取将导致错误。
*   **目录路径**:返回目录的路径。
*   **dir.read()** :异步读取下一个目录条目。读取完成后，将返回一个承诺，该承诺将使用 fs 进行解析。Dirent，如果不再读取目录，则为 null。

**方法:**基于回调的 fs.opendir()方法。为了用承诺来操作它，首先，我们使用在实用程序模块中定义的 promisify()方法将其转换为基于承诺的方法。
T3】示例 1:文件名:index.js

## java 描述语言

```js
// Importing File System and Utilities module
const fs = require('fs')
const util = require('util')

// Convert callback based methods
// to promise based methods
const openDir = util.promisify(fs.opendir)

openDir('./testDirectory')
    .then(dir => {
        console.log('Directory is opened')

        // Path to the directory
        console.log(`Path to the directory:
                            ${dir.path}`)

        // Closing directory
        return dir.close()
    })

    .then(() => {
        console.log('Directory closed')

        console.log('\nFurther attempt to'
            + ' read sub-directories:\n')

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